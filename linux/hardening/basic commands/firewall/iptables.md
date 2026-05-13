sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
sudo iptables -P OUTPUT ACCEPT

sudo iptables -A INPUT -i lo -j ACCEPT

sudo iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT

sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 3389 -j ACCEPT

sudo iptables -L -v -n

```
sudo apt install iptables-persistent
sudo netfilter-persistent save

sudo sh -c "iptables-save > /etc/iptables.rules"
```
























