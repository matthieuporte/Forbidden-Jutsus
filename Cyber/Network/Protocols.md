
[all RFC](https://www.rfc-editor.org/rfc/)


### Cisco 

Cisco lets you hash password with a method called Cisco7 and it looks like this :

```
username hub password 7 025017705B3907344E 
username admin privilege 15 password 7 10181A325528130F010D24
username guest password 7 124F163C42340B112F3830
```

It is called a Cisco7 hash and is easily breakable with tools such as [this website](https://www.frameip.com/decrypter-dechiffrer-cracker-password-cisco-7/)

### TTL 

In the TCP/IP protocol, TTL can mean Time To Live and it specifies the maximum time a packet is allowed to live or the maximum number of hops it can take in a network before being discarded.

### Get legal info about a domain

The website [whois.com](https://www.whois.com/whois) lets you access legal information about a server.


### DNS

ch11.challenge01.root-me.org:54011
a.root-servers.net

### LDAP

https://www.n00py.io/2020/02/exploiting-ldap-server-null-bind/

### POP

[RFC1939](https://www.rfc-editor.org/rfc/rfc1939.txt)

POP is a protocol to connect to a mail server, to do so you must pass an username and a password. It is not recommended to send your password as plain text though. Another method is to send it with APOP.

APOP does the same thing but with a md5 encryption.

Filter in wireshark with : tcp.port== 110

look for this server/client interaction : 

```
S: +OK POP3 server ready <1896.697170952@dbc.mtview.ca.us>
C: APOP mrose c4c9334bac560ecc979e58001b3e22fb
```

In this example, the shared  secret  is  the  string  `tanstaaf`.
Hence, the MD5 algorithm is applied to the string

> `<1896.697170952@dbc.mtview.ca.us>tanstaaf`

which produces a digest value of

> `c4c9334bac560ecc979e58001b3e22fb`


c.f. APOP : [RFC1939 page15](https://www.rfc-editor.org/rfc/rfc1939.html#page-15)
