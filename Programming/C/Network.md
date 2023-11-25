
## Internet protocol stack

The Internet protocol stack, often referred to as the **TCP/IP** stack, is a conceptual framework that standardizes the functions of communication protocols used for internet-like networks. 

The Internet protocol stack consists of four main layers:

>[!abstract]- 1 Link Layer
> - The link layer is the lowest layer in the TCP/IP model.
> - This layer deals with the physical connection to the network and is responsible for transmitting raw bits over a physical medium.
> - It includes protocols such as Ethernet, Wi-Fi, and PPP (Point-to-Point Protocol).

>[!abstract]- 2 Internet Layer
>  - The internet layer derives its name from its function facilitating internetworking.
> - It is responsible for addressing and routing packets between devices across different networks.
  > - The primary protocol at this layer is the Internet Protocol (IP), which provides a unique address to each device on the network (IPv4 or IPv6).

>[!abstract]- 3 Transport Layer
> - The Transport Layer ensures end-to-end communication between devices and is responsible for error detection, correction, and flow control.
  > - Two prominent transport layer protocols are [Transmission Control Protocol (TCP)](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) and [User Datagram Protocol (UDP)](https://en.wikipedia.org/wiki/User_Datagram_Protocol). TCP provides reliable, connection-oriented communication, while UDP offers a connectionless and lightweight alternative.
  > - Together, TCP and UDP comprise essentially all traffic on the Internet and are the only protocols implemented in every major operating system.

>[!abstract]- 4 Application Layer
> - The Application Layer is where user applications and network services interact with the network.
> - It includes various protocols for specific applications, such as [HTTP (Hypertext Transfer Protocol)](https://en.wikipedia.org/wiki/HTTP) for web browsing, [FTP (File Transfer Protocol)](https://en.wikipedia.org/wiki/File_Transfer_Protocol) for file transfer, [SMTP (Simple Mail Transfer Protocol)](https://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) for email, and more.
  > - This layer represents the interface between the network and the software applications that utilize network services.

![[NetworkProtocolStack.png]]

Each layer in the Internet protocol stack relies on the services provided by the layer immediately below it.

---

### Ports

A port is a logical endpoint for communication. They are used by every TCP/UDP communication.

 - A port is identified by a 16-bit unsigned number, resulting in a range of 0 to 65535.
 - A connection is identified by the double pair ` (IP1,port1),(IP2,port2)) `
 - Port numbers from 0 to 1023 are well-known or system ports and are reserved for specific, standardized services. For example, HTTP typically uses port 80, and HTTPS uses port 443.

---

## Network programming

### client side

The [getaddrinfo(3)](https://manpages.debian.org/stretch/manpages-dev/getaddrinfo.3.en.html) function in C is used for resolving domain names into IP addresses and obtaining information about network services.


**getaddrinfo**() returns one or more _addrinfo_ structures, each of which contains an Internet address that can be specified in a call to [bind(2)](https://manpages.debian.org/stretch/manpages-dev/bind.2.en.html) or [connect(2)](https://manpages.debian.org/stretch/manpages-dev/connect.2.en.html).

>[!info]- The _addrinfo_ structure
>```c
>struct addrinfo { 
>	int ai_flags; 
>	int ai_family; 
>	int ai_socktype; 
>	int ai_protocol; 
>	socklen_t ai_addrlen; 
>	struct sockaddr *ai_addr; 
>	char *ai_canonname; 
>	struct addrinfo *ai_next; 
>};
>```

Our function will take a `char* url` as a parameter.

First we need to set up hints to filter results :
```c
// Create the 'hints' structure.
struct addrinfo hints;

// Initialize all the fields to zero.
memset(&hints, 0, sizeof(hints));

// Specify the criteria
hints.ai_family = AF_INET;       // IPv4
hints.ai_socktype = SOCK_STREAM; // TCP
```

>[!info]- Differents criterias
>Here are some examples of other possible criterias
> 1) **ai_family**
>AF_INET: IPv4 only 
>AF_INET6: IPv6 only
>AF_UNSPEC: Either IPv4 or IPv6
>2) **ai_socktype**
>SOCK_STREAM: TCP
>SOCK_DGRAM: UDP
>0: Either TCP or UDP

We parse the url (separate the host and the path)

```c
char* host;
char* path;

parse_url(url,&host,&path);
```

Now we will try to obtain the necessary network information calling `getaddrinfo`.

```c
struct addrinfo *result;
int status = getaddrinfo(host, "80", &hints, &result);

if (status != 0)
{
	printf("error: %s\n", gai_strerror(status));
	exit(EXIT_FAILURE);
}
```

For each `addrinfo` in the results we try establish a connection :

```c
int sock;
struct addrinfo *p;
for (p = result; p != NULL; p = p->ai_next) {
	sock = socket(p->ai_family,p->ai_socktype,p->ai_protocol);
	if (sock == -1){
		continue;
	}
	int connection = connect(sock,p->ai_addr,p->ai_addrlen);
	if (connection == -1){
		close(sock);
	} else {
		//If the connection is successful we stop the loop to keep 
		//the file descriptor of the socket
		break;	
	}
}
```

If `p` is `NULL` it means that no connection was established, otherwise we can write our request to the socket. 

```c
if (p == NULL){
	errx(1,"print_page: no connection established");
}

// writes the request in the socket
write_request(sock,host,path);

// we can free the list of adress now
freeaddrinfo(result);
```

Now we can give back to the STDOUT the answer from the server :

```c
int r;
while ((r = read(sock,buffer,BUFFER_SIZE)) > 0){
	write(STDOUT_FILENO,buffer,r);
};
```

Note that the following line both sets a value to r and returns it
```c
(r = read(sock,buffer,BUFFER_SIZE)) > 0
```

We must not foget to close the file descriptor of the socket and free the array used.

```c
close(sock);
free(path);
free(host);
```

---

### Server side (One Connection at a Time)

---

### Server side (Multiple Connections)

---