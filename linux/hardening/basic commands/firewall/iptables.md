

```
sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
sudo iptables -P OUTPUT ACCEPT
```

# LOOPBACK ACCEPT
```
sudo iptables -A INPUT -i lo -j ACCEPT
```

sudo iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT

sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 3389 -j ACCEPT

sudo iptables -L -v -n



# PERSISTENCE OFFLINE
```
sudo sh -c "iptables-save > /etc/iptables.rules"
```
```
sudo nano /etc/systemd/system/iptables-restore.service
```
>[Unit]  
Description=Restore iptables rules  
Before=network-pre.target  
Wants=network-pre.target  
[Service]  
Type=oneshot  
ExecStart=/sbin/iptables-restore < /etc/iptables.rules  
[Install]  
WantedBy=multi-user.target

```
sudo systemctl enable iptables-restore
```


# PERSISTENCE ONLINE
```
sudo apt install iptables-persistent
sudo netfilter-persistent save
```
























