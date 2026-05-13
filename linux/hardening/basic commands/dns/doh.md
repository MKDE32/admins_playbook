```
sudo apt install dnscrypt-proxy
sudo systemctl enable dnscrypt-proxy
sudo systemctl start dnscrypt-proxy
systemctl status dnscrypt-proxy
```

```
sudo nano /etc/dnscrypt-proxy/dnscrypt-proxy.toml
```


>server_names = ['cloudflare']  
fallback_resolver = ''  
require_dnssec = true  
require_nolog = true  
require_nofilter = true
listen_addresses = ['127.0.0.1:53']


```
sudo ufw deny out 53
sudo ufw deny out 853
```

























