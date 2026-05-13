# INSTALL DNSCRYPT-PROXY
```
sudo apt install dnscrypt-proxy
sudo systemctl enable dnscrypt-proxy
sudo systemctl start dnscrypt-proxy
systemctl status dnscrypt-proxy
```


# CONFIGURE DNSCRYPT
```
sudo nano /etc/dnscrypt-proxy/dnscrypt-proxy.toml
```
>server_names = ['cloudflare']  
fallback_resolver = ''  
require_dnssec = true  
require_nolog = true  
require_nofilter = true
listen_addresses = ['127.0.0.1:53']



# SYSTEM DNS SETZEN
```
sudo systemctl disable systemd-resolved
sudo systemctl stop systemd-resolved
sudo rm /etc/resolv.conf
echo "nameserver 127.0.0.1" | sudo tee /etc/resolv.conf
```



# FIREWALL
ggf port 53 blocken



# TEST & LEAK TEST
```
dig example.com
curl https://1.1.1.1/help
```

















