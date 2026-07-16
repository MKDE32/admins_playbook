# change nameserver
```
sudo nano /etc/network/interfaces
```

```
iface eth0 inet static
    address 192.168.1.100
    netmask 255.255.255.0
    gateway 192.168.1.1
    dns-nameservers 1.1.1.1 8.8.8.8
```

```
sudo systemctl restart networking
```




























