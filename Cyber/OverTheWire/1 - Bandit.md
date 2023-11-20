### Find specific file

_finds all readable files of 1033bytes that are actual files (not exe)_

```bash
find -readable -size 1033c -type f
```

_to find in vim :_

```bash
/searchPattern
```

### Piping and redirecting

_output the result of a command in a file_

```bash
command > myoutput //replaces
command >> myoutput //adds at the end
```

_use a file as parameter for a command_

```bash
command < myinput
```

_output the result of a program to another program_

```bash
command1 | command2 
ls | head -3 | tail -1
```

### Find in file

_command to file unique line or duplicates_

```bash
uniq -c (count) -i (ignore-case) -d (duplicate) -u (unique)
```

### ssh

_connect with a private ssh key_

```bash
ssh -i sshkey.private user@host -p 2220
```

⚠ the sshkey need to be readable only by you !

```bash
chmod 600 ~/.ssh/id_rsa
```

### OpenSSL

_connect over ssl encryption_

```bash
openssl s_client -connect host:port
```

_without encryption_

```bash
telnet host port
```

### Scan a network

```bash
nmap server
```

_with specific ports_

```bash
nmap server -p XXX-XXX
```

### Difference between two files

```bash
diff file1 file2
```

### Bypass .bashrc while connecting through ssh

_be careful weird stuff will happen !_

```bash
ssh -t username@hostname /bin/sh
```

### Multiple buffers in the term

```bash
tmux
```

then `ctrl+b` followed by a command :

`c` : creates a new buffer

`0-9` : navigate through buffers

### Create a client/server model with nc

_open a port_

```bash
nc -l port
```

_connect to the port_

```bash
nc -N localhost port
```

anything sent in one shell will be transmitted to the next one

### Writing a script

every shell script must start with a _shebang_ with the name of the shell (bash is bash, sh is sh):

```bash
#! /bin/bash

rm brute.input
for i in {0..999}
do
	echo the pin is : $(printf "%04d\\n" $i) >> brute.input
done
```

This scripts generates a file with 1000 pin codes

### Overwriting command with PATH and ssh


>[!info] All different shells are stored in `/etc/shells` The shells used by each users are in `/etc/passwd`


you can send a env variable through ssh like this :

```bash
ssh -o SendEnv=PATH -i sshkey user@host -p 2220
```

be careful though the env variable must be allowed in `cat /etc/ssh/sshd_config`

on the line

`AcceptEnv LANG LC_* WECHALL* OTW*`

you can see all the env variables with `env`

env variables can be set here `cat /etc/environment`
