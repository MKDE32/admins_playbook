```
$ErrorActionPreference = "SilentlyContinue"
    Install-windowsfeature -name AD-Domain-Services -IncludeManagementTools
    Invoke-Command -ScriptBlock {net user administrator "Adminpw95"}
    Import-Module ADDSDeployment
    Install-ADDSForest -CreateDnsDelegation:$false -DatabasePath "C:\Windows\NTDS" -DomainMode "WinThreshold" -DomainName "example.com" -DomainNetbiosName "ADEXAMPLE" -ForestMode "WinThreshold" -InstallDns:$true -LogPath "C:\Windows\NTDS" -NoRebootOnCompletion:$false -SysvolPath "C:\Windows\SYSVOL" -SafeModeAdministratorPassword $(ConvertTo-SecureString -String "SafeModepw84" -AsPlainText -Force)-Force:$true
```
