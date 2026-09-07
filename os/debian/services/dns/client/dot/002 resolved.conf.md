# overview
```
resolvectl status
```

```
sudo systemctl enable --now
systemd-resolved.service
```



sudo nano /etc/systemd/resolved.conf
```
[Resolve]
DNS=
FallbackDNS=
DNSOverTLS=yes
DNSSEC=yes
Domain=~.
```




sudo systemctl restart systemd-resolved
resolvectl status











































