# PUBLIC NETWORK
```
netsh interface show interface
netsh interface set interface "Ethernet" new interface=Public
netsh interface set interface "Wi-Fi" new interface=Public
```
# DNS OVER HTTPS
```
Einstellungen öffnen
Netzwerk & Internet
Deinen Adapter auswählen:
WLAN oder
Ethernet
Bei der aktiven Verbindung auf Hardwareeigenschaften bzw. Eigenschaften klicken
Abschnitt DNS-Serverzuweisung → Bearbeiten
Von „Automatisch“ auf Manuell
IPv4 aktivieren
DNS eintragen, z. B.:
Bevorzugt: 1.1.1.1
Alternativ: 1.0.0.1
Darunter:
Bevorzugte DNS-Verschlüsselung → Nur verschlüsselt (DNS over HTTPS)
```
# SMB V1
```
reg query "HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" /v SMB1
reg query "HKLM\SYSTEM\CurrentControlSet\Services\mrxsmb10" /v Start
reg add "HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" /v SMB1 /t REG_DWORD /d 0 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Services\mrxsmb10" /v Start /t REG_DWORD /d 4 /f
```
# SMB SIGNING
```
reg query "HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters"
reg add "HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters" /v RequireSecuritySignature /t REG_DWORD /d 1 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters" /v RequireSecuritySignature /t REG_DWORD /d 1 /f
```
# SMB
```
sc stop LanmanServer
sc config LanmanServer start= disabled
```
# LLMNR
```
reg query "HKLM\Software\Policies\Microsoft\Windows NT\DNSClient" /v EnableMulticast
reg add "HKLM\Software\Policies\Microsoft\Windows NT\DNSClient" /v EnableMulticast /t REG_DWORD /d 0 /f
```
# NETBIOS OVER TCP
```
wmic nicconfig get TcpipNetbiosOptions
wmic nicconfig where TcpipNetbiosOptions!=NULL call SetTcpipNetbios 2
```
# NETWORK PRINTING
```
netsh advfirewall firewall set rule group="File and Printer Sharing" new enable=No
```
# UPNP
```
sc stop upnphost
sc config upnphost start= disabled
netsh advfirewall firewall add rule name="Block UPnP SSDP" dir=in action=block protocol=UDP localport=1900
```
# WPAD
```
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v AutoDetect /t REG_DWORD /d 0 /f
```
# TLS
```
reg add "HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server" /v Enabled /t REG_DWORD /d 0 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client" /v Enabled /t REG_DWORD /d 0 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server" /v Enabled /t REG_DWORD /d 0 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client" /v Enabled /t REG_DWORD /d 0 /f
```

# IP V6
```
netsh interface teredo set state disabled
netsh interface 6to4 set state disabled
netsh interface isatap set state disabled
netsh advfirewall firewall add rule name="Block IPv6 Inbound" dir=in action=block protocol=ANY remoteip=::/0
netsh advfirewall firewall add rule name="Block IPv6 Outbound" dir=out action=block protocol=ANY remoteip=::/0
```
# NTLM
```
reg query "HKLM\SYSTEM\CurrentControlSet\Control\Lsa" /v LmCompatibilityLevel
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Lsa" /v LmCompatibilityLevel /t REG_DWORD /d 5 /f
```
# WEBDAV
```
sc stop WebClient
sc config WebClient start= disabled
```
# NETWORK DISCOVERY
```
netsh advfirewall firewall set rule group="Network Discovery" new enable=No
```
















