
```
systemctl status systemd-resolved
sudo nano /etc/systemd/resolved.conf
```
>[Resolve]  
DNS=1.1.1.1#cloudflare-dns.com  
DNSOverTLS=yes  
FallbackDNS=  
Domains=~.  
DNSSEC=yes

```
sudo systemctl restart systemd-resolved
```














