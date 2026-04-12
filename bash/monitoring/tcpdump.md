# EXAMPLE
```
sudo tcpdump -i INTERFACE ip and host example.com
```

# FLAGS
## COMMON
`tcpdump -i any` set interface  
`-n` shows no dns  
`-nn` shows no dns and no portname  
`-X` shows hex + ascii  
`-A` shows ascii only  
`-w file.pcap` write to file  
`-r file.pcap` read from file  

## FILTER
`host IPADDR`
`src IPADDR`
`dst IPADDR`
`port`
`net 192.168.0.0/24`
