# REMOTE ASSISTENCE
```
netsh advfirewall firewall set rule group="Remote Assistance" new enable=No
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Remote Assistance" /v fAllowToGetHelp /t REG_DWORD /d 0 /f
```
# QUICK ASSIST
```
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows\Windows Chat" /v "ChatIcon" /t REG_DWORD /d 3 /f
```
# RDP
```
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 1 /f
netsh advfirewall firewall set rule group="remote desktop" new enable=No
```
# DCOM
```
sc stop RemoteRegistry
sc config RemoteRegistry start= disabled
```
# WINRM
```
sc stop WinRM
sc config WinRM start= disabled
```
