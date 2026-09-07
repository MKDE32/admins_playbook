# overview
```
resolvectl status
```

```
sudo systemctl enable --now
systemd-resolved.service
```


# resolved.conf
`sudo nano /etc/systemd/resolved.conf`
```
[Resolve]
DNS=9.9.9.9#dns.quad9.net
FallbackDNS=149.112.112.112#dns.quad9.net
DNSOverTLS=yes
DNSSEC=yes
Domain=~.
```
# restart
```
sudo systemctl restart systemd-networkd
sudo systemctl restart systemd-resolved
```
# flush dns
```
sudo systemd-resolve --flush-caches
```
# test
```
resolvectl dns
resolvectl dnsovertls
```


































