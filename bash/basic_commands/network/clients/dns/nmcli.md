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
nmcli connection show
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.ignore-auto-dns yes
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.dns "127.0.0.1"
sudo nmcli connection down "FRITZ!Box 6670 LM"
sudo nmcli connection up "FRITZ!Box 6670 LM"
```

# using gui dns again
```
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.ignore-auto-dns no
sudo nmcli connection down "FRITZ!Box 6670 LM"
sudo nmcli connection up "FRITZ!Box 6670 LM"
```
