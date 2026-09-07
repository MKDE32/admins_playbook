# overview
```
resolvectl status
```

```
sudo systemctl enable --now
systemd-resolved.service
```



`sudo nano /etc/systemd/resolved.conf`
```
[Resolve]
DNS=9.9.9.9#dns.quad9.net
FallbackDNS=149.112.112.112#dns.quad9.net
DNSOverTLS=yes
DNSSEC=yes
Domain=~.
```


```
sudo systemctl restart systemd-networkd
sudo systemctl restart systemd-resolved
```











































