IP.TXT:
>PING 192.168.178.10 (192.168.178.10) 56(84) bytes of data.
>64 bytes from 192.168.178.10: icmp_seq=1 ttl=64 time=2301 ms


```
cat ip.txt | grep "64 bytes" | cut -d " " -f 4 | tr -d ":"
```
>192.168.178.10
