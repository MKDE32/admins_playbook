## Installation (Debian / Ubuntu / Kali)
```
sudo apt update
sudo apt install openvpn
```

## Verbindung starten
```
sudo openvpn --config file.ovpn
```

# mit Credentials (falls benötigt)
```
sudo openvpn --config file.ovpn --auth-user-pass
```

## Verbindung im Hintergrund
```
sudo openvpn --config file.ovpn --daemon
```

## Verbindung stoppen
```
sudo killall openvpn
```

## Status / Logs ansehen
```
ps aux | grep openvpn
journalctl -u openvpn
tail -f /var/log/syslog
```

## Netzwerk prüfen
```
ip a
ip route
```

# prüfen ob VPN Interface da ist (z. B. tun0)
```
ip a | grep tun
```

## Traffic testen
```
ping 10.x.x.x
curl ifconfig.me
```

## DNS prüfen
```
cat /etc/resolv.conf
```

## Häufige Probleme

# keine Route ins VPN
```
sudo ip route add <target-netz> via <gateway>
```

# DNS Problem
```
sudo systemctl restart systemd-resolved
```

# Permission Fehler bei .ovpn
```
chmod 600 file.ovpn
```

## Typischer Workflow (Pentest)
```
sudo openvpn --config vpn.ovpn
ip a
ip route
ping <target>
```

# dann Tools starten (nmap, etc.)

## Wichtige Hinweise

# root nötig für Netzwerkinterfaces

# .ovpn Dateien enthalten oft sensitive Daten

# Logs helfen IMMER bei Problemen
