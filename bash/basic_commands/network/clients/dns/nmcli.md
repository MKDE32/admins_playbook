# dns server change
methode funktioniert eher bei desktop systemen
## overview
```
nmcli connection show
```
## show dns server
```
nmcli dev show | grep DNS
```
## change dns server
```
nmcli connection modify <NAME> ipv4.dns "1.1.1.1 8.8.8.8"
nmcli connection modify <NAME> ipv4.ignore-auto-dns yes
nmcli connection up <NAME>
```

# add proxy dns server
```
nmcli connection modify <NAME> proxy.method manual
nmcli connection modify <NAME> proxy.http 192.168.1.100:8080
nmcli connection modify <NAME> proxy.https 192.168.1.100:8080
nmcli connection up <NAME>
```







