# EXAMPLE
```
sudo tcpdump -i INTERFACE ip and host example.com
```
```
sudo tcpdump -i eth0 -vn host 8.8.8.8 and port 53 &
```



# FLAGS
## COMMON
`tcpdump -i any` set interface  
`-n` shows no dns  
`-nn` shows no dns and no portname  
`-v` verbose  
`-X` shows hex + ascii  
`-A` shows ascii only  
`-w file.pcap` write to file  
`-r file.pcap` read from file  

## FILTER
`host IPADDR`  
`src IPADDR`  
`dst IPADDR`  
`port PORT`  
`net IPADDR/CIDR`
