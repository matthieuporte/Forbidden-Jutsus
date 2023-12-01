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

### Uuencoding

Uuencoding, short for Unix-to-Unix encoding, is a method of encoding binary data so that it can be transmitted over text-based protocols.
It is very used by the HTTP protocol.

[Encoding_formats.pdf](https://repository.root-me.org/Cryptographie/EN%20-%20Encodings%20format.pdf)


### Base64

A string that looks like this `ZnJhbms6ZmllZGxlcg==` has great odds to be in base64, notice the `==` at the end.

### Chiffre de Vigenere 

#todo


### Crack wifi hotspot

I can guide you through the process in theory, but please remember that attempting to access someone else's network or retrieve passwords without explicit permission is illegal and unethical. If you're performing this exercise on your own network for educational purposes or you have permission to do so, here's a general example of how you might use airodump-ng:

1. **Open Terminal:**
   Open a terminal window on your computer.

2. **Check Available Wireless Interfaces:**
   Run the command:
   ```
   sudo airmon-ng
   ```
   This will display the available wireless interfaces. Note the name of your wireless interface (e.g., wlan0).

3. **Put Wireless Interface into Monitor Mode:**
   Use the following command to put your wireless interface into monitor mode:
   ```
   sudo airmon-ng start <your_wireless_interface>
   ```
   Replace `<your_wireless_interface>` with the name of your wireless interface (e.g., wlan0).

4. **Start Airodump-ng to Capture Data:**
   Run airodump-ng to capture data from nearby networks:
   ```
   sudo airodump-ng <your_wireless_interface>
   ```
   This command will display a list of nearby Wi-Fi networks along with their details.

5. **Filter for Your Network:**
   Find your network's BSSID (the MAC address of your Wi-Fi access point) and channel from the list.

6. **Capture Packets for Your Network:**
   Run airodump-ng targeting your network specifically:
   ```
   sudo airodump-ng -w output --bssid <your_BSSID> -c <your_channel> <your_wireless_interface>
   ```
   Replace `<your_BSSID>` and `<your_channel>` with your network's BSSID and channel, respectively.

7. **Capture Handshake:**
   Wait for a device to connect to your network. When a device connects, airodump-ng will capture the WPA handshake (if using WPA/WPA2 encryption).

8. **Stop Airodump-ng:**
   After capturing the handshake, stop airodump-ng by pressing `Ctrl + C`.

9. **Check Captured Handshake:**
   The captured handshake will be saved in the file specified (e.g., `output.cap`). You can use tools like hashcat or aircrack-ng to attempt to crack the captured handshake to obtain the password hash.

Remember, this exercise should only be conducted on your own network or with explicit permission from the network owner. Unauthorized access to networks is illegal and unethical.

https://www.aircrack-ng.org/doku.php?id=cracking_wpa