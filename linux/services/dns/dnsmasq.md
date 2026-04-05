# INSTALL
```
sudo apt install dnsmasq
```

# FLAGS
`-d` debugmode (foreground)  
`-q` queries logging  
`-H WHATEVER.txt` adding hostfile, format: `IPADDR DNSADR`
`-C /etc/dhcp.conf` using this conf dat

# DHCP.CONF
/etc/dhcp.conf  
`interface=WHATEVER`  
`bind-interfaces`  
`domain=EXAMPLE`  
`dhcp-option=option:router,IPADDR`  
`dhcp-option=option:dns-server,IPADDR`  
`dhcp-range=FROM,TO,12h` here 12 hours leasing time








