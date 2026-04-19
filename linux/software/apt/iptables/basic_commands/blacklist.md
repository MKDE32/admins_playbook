RDP-Bruteforce-Schutz mit iptables (pro IP)

🔹 Neue Chain anlegen



sudo iptables -N RDP_BRUTE



🔹 RDP-Verbindungen in die Chain leiten



sudo iptables -A INPUT -p tcp --dport 3389 -m conntrack --ctstate NEW -j RDP_BRUTE



🔹 WICHTIG: richtige Reihenfolge



# 1. ZUERST blockieren, wenn Limit erreicht
sudo iptables -A RDP_BRUTE -m recent --update --seconds 600 --hitcount 11 --name RDP -j DROP

# 2. DANN IP merken
sudo iptables -A RDP_BRUTE -m recent --set --name RDP

# 3. Alles andere erlauben
sudo iptables -A RDP_BRUTE -j ACCEPT


🔢 Ergebnis:
• 3 Versuche pro IP

• 4. Versuch innerhalb von 60s → DROP



🧪 2️⃣ Testen, ob es funktioniert

Regeln anzeigen



sudo iptables -L RDP_BRUTE -n --line-numbers



Live-Zähler beobachten



watch -n1 cat /proc/net/xt_recent/RDP


➡️ Beim 4. Verbindungsversuch siehst du den DROP.

💾 3️⃣ Regeln dauerhaft speichern

🔹 Paket installieren



sudo apt install iptables-persistent -y


Beim Dialog:



Save current IPv4 rules?  YES
Save current IPv6 rules?  YES



🔹 Manuell speichern (jederzeit)



sudo netfilter-persistent save



🔹 Nach Reboot laden (automatisch)



sudo systemctl enable netfilter-persistent
