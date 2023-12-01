
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