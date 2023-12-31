### What is my Hash ?

If you don't know what is the hash you're looking at you can use `hash-identifier` to find out.

### DCC

```shell
hashcat -m1100 "15a57c279ebdfea574ad1ff91eb6ef0c:Administrator" rockyou.txt
```

DCC2 : $DCC2$10240#Administrator#23d97555681813db79b2ade4b4a6ff25

### MT

online tools : [rainbowtables.it64.com/](http://rainbowtables.it64.com/)

### NT

```shell
hashcat -m 1000 "b4f79698831d92b61f886438e36c0c52" rockyou.txt -O
```

### Md5

Md5 is a strong (not perfect) hash function. The idea is that it is impossible to get the original string back, what you can do however is to try to bruteforce the password by trying many things and comparing the hashes.

Here's how to hash a string with md5 : 
```shell
echo -n "Password1" | md5sum | tr -d " -"
```

Here's how to brute force it using hashcat :

```shell
hashcat -m 0 -a 3 hashes "?l?l?l?l" -O
```

`-m` is to specify the hash function, `hashes`is the hash file containing the hash password we need to decipher and "?l?l?l?l" is the pattern we're trying to match (here it's four letters).
Alternatively you can use a dictionary instead of a pattern such as `rockyou.txt`.

>[!tip] Online cracking
>Some website do just this and try many weak password. A good one is [gromweb.com](https://md5.gromweb.com/)

### Uuencoding

Uuencoding, short for Unix-to-Unix encoding, is a method of encoding binary data so that it can be transmitted over text-based protocols.
It is very used by the HTTP protocol.

[Encoding_formats.pdf](https://repository.root-me.org/Cryptographie/EN%20-%20Encodings%20format.pdf)


### Base64

A string that looks like this `ZnJhbms6ZmllZGxlcg==` has great odds to be in base64, notice the `==` at the end.

### Chiffre de Vigenere 

#todo

### Sha-2

Some websites lets you bruteforce SHA-2 password such as :  

