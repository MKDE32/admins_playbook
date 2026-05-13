```
sudo apt install dnscrypt-proxy
```

`/etc/dnscrypt-proxy/dnscrypt-proxy.toml`


>server_names = ['cloudflare']  
fallback_resolver = ''  
require_dnssec = true  
require_nolog = true  
require_nofilter = true


127.0.0.1



```
sudo ufw deny out 53
sudo ufw deny out 853
```

























