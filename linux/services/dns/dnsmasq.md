# INSTALL
```
sudo apt install dnsmasq
```

# FLAGS
`-d` debugmode (foreground)  
`-q` queries logging  
`-H WHATEVER.txt` adding hostfile, format: `IPADDR DNSADR`

# DHCP.CONF
/etc/dhcp.conf  
`interface=WHATEVER`  
`bind-interfaces`  
`domain=EXAMPLE`  
`dhcp-option=option:router,IPADDR`  
`dhcp-option=option:dns-server,IPADDR`  









