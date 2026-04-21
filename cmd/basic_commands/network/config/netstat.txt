# EXAMPLES
netstat -ano
-> MOST USED ADMIN COMMAND
-> All connections + numeric + PID

netstat -abno
-> Full detail: executable + connections + PID
-> (Admin required, very noisy)

netstat -ano | findstr :80
-> Filter specific port (example HTTP)

netstat -ano | findstr LISTENING
-> Show only listening ports

netstat -ano | findstr ESTABLISHED
-> Show active connections





# FLAGS

netstat
-> Shows active connections (basic view)

netstat -a
-> All connections + listening ports

netstat -n
-> Shows addresses and ports in numeric form (no DNS)

netstat -o
-> Shows PID (process ID) for each connection

netstat -b
-> Shows executable involved (requires admin)

netstat -e
-> Ethernet statistics

netstat -s
-> Protocol statistics (TCP/UDP/ICMP)

netstat -r
-> Routing table (same as route print)





# INFO
- netstat -b requires admin rights
- malware often hides via random ports
- always correlate PID with tasklist
- ESTABLISHED connections show active communication
- LISTENING ports may indicate services or backdoors
