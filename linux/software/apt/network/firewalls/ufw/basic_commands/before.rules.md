The rules for ICMP ping is mentioned in the file before.rules. The file is present in the location /etc/ufw/before.rules.
 Therefore, before making any changes our Support Engineers usually take a backup of the file.

 ```
 cp /etc/ufw/before.rules /etc/ufw/before.rules_backup_date 
 ```

 Now we open the file and we need to change the below rules.
 
```
nano /etc/ufw/before.rules 
```

# ok icmp codes for INPUT
```
-A ufw-before-input -p icmp --icmp-type destination-unreachable -j ACCEPT
-A ufw-before-input -p icmp --icmp-type source-quench -j ACCEPT
-A ufw-before-input -p icmp --icmp-type time-exceeded -j ACCEPT
-A ufw-before-input -p icmp --icmp-type parameter-problem -j ACCEPT
-A ufw-before-input -p icmp --icmp-type echo-request -j ACCEPT
 ```
 insert one drop rule at the top:
 
# ok icmp codes for INPUT
```
-A ufw-before-input -p icmp --icmp-type echo-request -j DROP
-A ufw-before-input -p icmp --icmp-type destination-unreachable -j ACCEPT
-A ufw-before-input -p icmp --icmp-type source-quench -j ACCEPT
-A ufw-before-input -p icmp --icmp-type time-exceeded -j ACCEPT
-A ufw-before-input -p icmp --icmp-type parameter-problem -j ACCEPT
-A ufw-before-input -p icmp --icmp-type echo-request -j ACCEPT
```
