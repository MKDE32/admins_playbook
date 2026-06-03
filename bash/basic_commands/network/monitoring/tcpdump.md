# EXAMPLES
## CAPTURE IN BACKGROUND
```
sudo tcpdump -i eth0 -vn host 8.8.8.8 and port 53 &
```

## WRITE DOWN JOB-ID
```
jobs -l
```

## EXECUTE YOUR APP NOW
`curl whatever.site`

## GET TCPDUMP IN FOREGROUND AGAIN
```
fg % [job-id]
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
