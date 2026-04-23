# USING
```
ssh user@10.129.224.248
```



# START & STARTUPTYPE
```
Start-Service sshd
Set-Service -Name sshd -StartupType 'Automatic'
```



# INSTALLING CLIENT
```
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'
Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0
```



# INSTALLING SERVER
```
Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
```










