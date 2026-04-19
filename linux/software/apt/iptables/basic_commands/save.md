Saving and restoring iptables rules

Standardmäßig speichert iptables die Regeln nicht.
Regeln dauerhaft speichern:

🔹 Paket installieren
sudo apt install iptables-persistent -y
Save current IPv4 rules?  YES
Save current IPv6 rules?  YES



🔹 Manuell speichern (jederzeit)
sudo netfilter-persistent save



🔹 Nach Reboot laden (automatisch)
sudo systemctl enable netfilter-persistent



IPv4
  Debian/Ubuntu: iptables-save > /etc/iptables/rules.v4

  Debian/Ubuntu: iptables-restore < /etc/iptables/rules.v4



IPv6
  Debian/Ubuntu: ip6tables-save > /etc/iptables/rules.v6
