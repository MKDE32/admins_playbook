# NetDom Cheat Sheet (Windows Domain Admin)

## 🖥️ Computer & Domain Management
netdom join %COMPUTERNAME% /domain:example.com /userd:admin /passwordd:*  
netdom remove %COMPUTERNAME% /domain:example.com /userd:admin /passwordd:*  
netdom renamecomputer OLDNAME /newname:NEWNAME /domain:example.com /userd:admin /passwordd:*  

## 🔐 Secure Channel
netdom verify %COMPUTERNAME% /domain:example.com  
netdom reset %COMPUTERNAME% /domain:example.com /userd:admin /passwordd:*  

## 🌐 Domain Trusts
netdom trust example.com /domain:otherdomain.com /verify  
netdom trust example.com /domain:otherdomain.com /reset /usero:admin /passwordo:*  

## 🔎 Queries
netdom query dc  
netdom query workstation  
netdom query user  

## ⚙️ Key Switches
/domain:        target domain  
/userd:         domain user  
/passwordd:     domain password  
/usero:         other domain user (trusts)  
/passwordo:     other domain password (trusts)  
*               prompt for password  
/verify         check trust/secure channel  
/reset          repair trust/secure channel  

## ⚠️ Notes
- Run CMD as Administrator  
- Prefer * instead of plaintext passwords  
- Legacy tool but still used in Active Directory environments  
- Modern alternative: PowerShell Test-ComputerSecureChannel
