# SETTING UP WINRM
```
winrm quickconfig
Test-WSMan -ComputerName "10.129.224.248"
Test-WSMan -ComputerName "10.129.224.248" -Authentication Negotiate
Enter-PSSession -ComputerName 10.129.224.248 -Credential htb-student -Authentication Negotiate
```
