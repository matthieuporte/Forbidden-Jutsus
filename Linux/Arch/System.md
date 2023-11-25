
## Internet

#### nmcli

*List networks*
```bash
nmcli device wifi list
```

*connect to*
```bash
nmcli device wifi connect "$SSID" password "$PASSWORD"
```

## Bluetooth

```shell
systemctl start bluetooth.service  
pulseaudio -k  
bluetoothctl  
-> power on  
-> agent on  
-> default-agent  
-> scan on  
-> pair [mac adress]  
-> connect [mac adress]  
```
set device as active in pavucontrol


## Printing

#### Show printing queue

```bash
lpq -a
```

#### Remove from printing queue

```bash
lprm id
```

#### Show connected printers

```bash
lpstat -p
```

#### Get info about printer

```bash
lpinfo -v
```

- output
    
    ```bash
    network ipps
    network https
    network socket
    file cups-brf:/
    network lpd
    network http
    network beh
    network ipp
    direct hp:/usb/HP_LaserJet_M14-M17?serial=VNC5J80180
    file cups-pdf:/
    direct usb://HP/LaserJet%20M14-M17?serial=VNC5J80180
    network smb
    direct hpfax
    ```
    
    The `direct usb` part is the URI.
    

#### Connect a printer

```bash
lpadmin -p PRINTERNAME -E -v UsbURI
```

- example :
    
    ```shell
    lpadmin -p HP_LaserJet_M14-M17 -E -v \
    usb://HP/LaserJet%20M14-M17?serial=VNC5J80180
    ```




## Hardware 

### Disable sleep on laptop lid close

Edit `/etc/systemd/logind.conf` and make sure you have

```
HandleLidSwitch=ignore
```

which will make it ignore the lid being closed.

Then, you'll want to reload `logind.conf` to make your changes go into effect (thanks to Ehtesh Choudhury for pointing this out in the comments):

```
systemctl restart systemd-logind
```