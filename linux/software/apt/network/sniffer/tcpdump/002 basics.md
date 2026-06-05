# basic command
```
tcpdump -i eth0 port 80
```



# examples
| Goal                | Command                                |
| ------------------- | -------------------------------------- |
| Capture HTTP        | `tcpdump -i eth0 -nn port 80`          |
| Inspect web traffic | `tcpdump -i eth0 -A port 80`           |
| Monitor DNS         | `tcpdump -i eth0 -nn udp port 53`      |
| Capture everything  | `tcpdump -i eth0 -s 0 -w capture.pcap` |
| Detect SYN scans    | `tcpdump 'tcp[tcpflags] == tcp-syn'`   |
| Exclude SSH noise   | `tcpdump -i eth0 not port 22`          |
| Watch SMB traffic   | `tcpdump -i eth0 port 445`             |
| ICMP monitoring     | `tcpdump icmp`                         |
