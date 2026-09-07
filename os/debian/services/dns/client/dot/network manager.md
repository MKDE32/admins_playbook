# overview
```
nmcli connection show
```

# set resolver
```
sudo nmcli connection modify "CONNECTION" ipv4.dns "9.9.9.9#dns.quad9.net"
```

# ignore dns from dhcp
```
sudo nmcli connection modify "CONNECTION" ipv4.ignore-auto-dns yes
```





sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.dns-priority -42



sudo nmcli connection down "FRITZ!Box 6670 LM"
sudo nmcli connection up "FRITZ!Box 6670 LM"
sudo systemctl restart systemd-resolved
```











































