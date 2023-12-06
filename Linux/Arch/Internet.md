
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

##### With `nmcli`
```shell
nmcli connection add type wifi con-name "IONIS" ssid "IONIS" wifi-sec.key-mgmt wpa-eap 802-1x.eap peap 802-1x.phase2-auth mschapv2 802-1x.identity "name.surname@epita.fr"

nmcli connection up IONIS --ask
```
Type your Bocal password when prompted, you should then be connected to the network. The configuration is now saved and can be opened quickly in other programs such as `nmtui`.

##### Manual configuration
Create a profile in 
`/etc/netctl`

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