# EXAMPLES
ip.src == 192.168.1.10 && tcp.port == 443  
dns && !(ip.addr == 192.168.1.1)  
tcp.flags.syn == 1 && tcp.flags.ack == 0  



# LOGIC OPERATORS
`&&`  AND  
`||`  OR  
`!`   NOT  



# STRING SEARCH
frame contains "password"  
tcp contains "GET"  
data contains "admin"  



# LAYER 2
## ARP
arp  
arp.opcode == 1  
arp.opcode == 2  

## MAC
eth.addr == aa:bb:cc:dd:ee:ff  
eth.src == aa:bb:cc:dd:ee:ff  
eth.dst == aa:bb:cc:dd:ee:ff  

## FRAME
frame.len > 1000  
frame.time_delta > 1  
frame.number == 100  



# LAYER 3
## IP
ip.addr == 192.168.1.1  
ip.src == 192.168.1.1  
ip.dst == 192.168.1.1  
ip.addr == 192.168.1.0/24  
!(ip.addr == 192.168.1.1)  

## ICMP
icmp  
icmp.type == 8  
icmp.type == 0  



# LAYER 4
## PORT
tcp.port == 80  
tcp.srcport == 443  
tcp.dstport == 22  
udp.port == 53  

## TCP
tcp.flags.syn == 1  
tcp.flags.ack == 1  
tcp.flags.fin == 1  
tcp.analysis.retransmission  
tcp.analysis.lost_segment  
tcp.window_size < 1000  



# LAYER 5-7
## HTTP
http  
http.request  
http.response  
http.host == "example.com"  
http.request.method == "GET"  
http contains "login"  

## DNS
dns  
dns.query.name == "example.com"   
dns.flags.response == 0  
dns.flags.rcode != 0  

## TLS
tls  
tls.handshake  
tls.handshake.type == 1  
tls.handshake.extensions_server_name == "example.com"  























































