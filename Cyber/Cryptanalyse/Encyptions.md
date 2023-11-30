

### Md5

Md5 is a strong (not perfect) hash function. The idea is that it is impossible to get the original string back, what you can do however is to try to bruteforce the password by trying many things and comparing the hashes.

Here's how to hash a string with md5 : 
```shell
echo -n "Password1" | md5sum | tr -d " -"
```

Here's how to brute force it using hashcat :

```shell
hashcat -m 0 -a 3 hashes rockyou.txt -O
```

`-m` is to specify the hash function, `hashes`is the hash file containing the hash password we need to decipher and `rockyou.txt` is the password dictionnary.

### Uuencoding

Uuencoding, short for Unix-to-Unix encoding, is a method of encoding binary data so that it can be transmitted over text-based protocols.
It is very used by the HTTP protocol.

[Encoding_formats.pdf](https://repository.root-me.org/Cryptographie/EN%20-%20Encodings%20format.pdf)


### Base64

A string that looks like this `ZnJhbms6ZmllZGxlcg==` has great odds to be in base64, notice the `==` at the end.