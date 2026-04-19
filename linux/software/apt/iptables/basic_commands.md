# SHOW VERSION
```
iptables -V
```





# OVERVIEW
## EXAMPLES
```
iptables -L
```

## FLAGS
-L list all rules in the selected chain.  
-n avoid long reverse DNS lookups. Print ip and port instead domain and service  
-S print all rules in the selected chain  
-v verbose output  





# DROP IPV6
```
sudo ip6tables -t filter -A INPUT -j DROP
```





# STATE
```
sudo iptables -I INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
```
aktive / verwandte Verbindungen zulassen





# DROP / ACCEPT

```
sudo iptables -t filter -A INPUT -j DROP
```
block input

```
sudo iptables -I INPUT 1 -p tcp --dport 22 -j ACCEPT
```
accept ssh

```
sudo iptables -I INPUT 1 -p tcp --dport 22 -s 5.3.6.6 -j ACCEPT
```
accept ip adress





# SET STANDART POLICY
```
sudo iptables -P INPUT DROP
sudo iptables -P OUTPUT ACCEPT
```

















