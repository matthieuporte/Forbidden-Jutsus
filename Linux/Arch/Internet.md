
### Troubleshooting

```shell
ip link
sudo systemctl start NetworkManager
sudo systemctl enable NetworkManager
nmcli general status
sudo systemctl restart NetworkManager
```

Check profiles in :

```shell
cat /etc/netctl/your-profile
```

### nmcli

*List networks*
```bash
nmcli device wifi list
```

*connect to*
```bash
nmcli device wifi connect "$SSID" password "$PASSWORD"
```


### Connect to IONIS wifi : 

```
Description='EPITA IONIS profile'
Interface=wlp2s0
ESSID='IONIS'
Connection=wireless
Security=wpa-configsection
IP=dhcp
WPAConfigSection=(
    'ssid="IONIS"'
    'key_mgmt=WPA-EAP'
    'eap=PEAP'
    'identity="name.surname@epita.fr"'
    'password="PASSWORD"'
)
```