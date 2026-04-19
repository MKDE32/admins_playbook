sudo apt-get install fail2ban

sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local

JAIL.LOCAL:
[DEFAULT]
ignoreip = 127.0.0.1/8 ::1  
[sshd]
enabled = true
filter = sshd
logpath  = /var/log/auth.log
maxretry = 10
findtime = 5m
bantime = 30m
(IPTABLES ODER UFW:)
action   = iptables[name=SSH, port=22, protocol=tcp]
banaction = ufw

befehle:
service fail2ban restart
fail2ban-client -d
fail2ban-client status
fail2ban-client status sshd
fail2ban-client get sshd bantime
fail2ban-client get sshd maxretry
fail2ban-client get sshd findtime
