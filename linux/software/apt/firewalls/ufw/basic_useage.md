# UFW Cheat Sheet (Admin Essentials)

## 🚀 Basics

### Enable / Disable
sudo ufw enable
sudo ufw disable

### Check status
sudo ufw status
sudo ufw status verbose
sudo ufw status numbered

---

## 🔐 Default Policies

### Set default policies
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw default deny forwarding

---

## ➕ Allow Rules

### Allow port
sudo ufw allow 22
sudo ufw allow 80/tcp
sudo ufw allow 53/udp

### Allow specific IP
sudo ufw allow from 192.168.1.100

### Allow IP to specific port
sudo ufw allow from 192.168.1.100 to any port 22

### Allow subnet
sudo ufw allow from 192.168.1.0/24

### Allow specific interface
sudo ufw allow in on eth0 to any port 80

---

## ❌ Deny Rules

### Deny port
sudo ufw deny 23

### Deny specific IP
sudo ufw deny from 10.10.10.10

### Reject instead of drop
sudo ufw reject from 10.10.10.10

---

## 🔁 Delete Rules

### Delete by rule
sudo ufw delete allow 22

### Delete by number
sudo ufw status numbered
sudo ufw delete <number>

---

## 📊 Logging

### Enable logging
sudo ufw logging on

### Set log level
sudo ufw logging low
sudo ufw logging medium
sudo ufw logging high

Logs:
- /var/log/ufw.log

---

## 🌐 Application Profiles

### List profiles
sudo ufw app list

### Show profile details
sudo ufw app info "Nginx Full"

### Allow by profile
sudo ufw allow "Nginx Full"

---

## 🔄 Reload / Reset

### Reload rules
sudo ufw reload

### Reset (WARNING: deletes all rules)
sudo ufw reset

---

## 🔀 Port Forwarding (Advanced)

### Enable in config
Edit:
 /etc/default/ufw
Set:
 DEFAULT_FORWARD_POLICY="ACCEPT"

### Example NAT (iptables backend)
# in /etc/ufw/before.rules
*nat
:POSTROUTING ACCEPT [0:0]
-A POSTROUTING -o eth0 -j MASQUERADE
COMMIT

---

## ⚙️ Common Commands

### Allow SSH (important before enabling firewall!)
sudo ufw allow ssh

### Allow HTTP/HTTPS
sudo ufw allow 80,443/tcp

### Deny all incoming except allowed
sudo ufw default deny incoming

### Allow outgoing DNS
sudo ufw allow out 53

---

## 🧠 Tips

- UFW is a frontend for iptables
- Rules are applied top → down
- Always allow SSH before enabling
- Use `status numbered` for easy rule management
- Combine with fail2ban for brute-force protection
