```
$ErrorActionPreference = "SilentlyContinue"
    Set-Variable -Name "serverName" -Value ([System.Net.Dns]::GetHostName())
    Add-ADPrincipalGroupMembership -Identity:"CN=qwiklabs,CN=Users,DC=example,DC=com" -MemberOf:"CN=Domain Admins,CN=Users,DC=example,DC=com" -Server:$serverName".example.com"
    New-ADGroup -Description:"All developers in the company" -GroupCategory:"Security" -GroupScope:"Global" -Name:"Developers" -Path:"CN=Users,DC=example,DC=com" -SamAccountName:"Developers" -Server:$serverName".example.com"
    New-ADGroup -Description:"Developers that write Java code" -GroupCategory:"Security" -GroupScope:"Global" -Name:"Java Developers" -Path:"CN=Users,DC=example,DC=com" -SamAccountName:"Java Developers" -Server:$serverName".example.com"
    New-ADUser -DisplayName:"Kristi" -GivenName:"Kristi" -Name:"Kristi" -Path:"CN=Users,DC=example,DC=com" -SamAccountName:"kristi" -Server:$serverName".example.com" -Type:"user"
    Set-ADAccountControl -AccountNotDelegated:$false -AllowReversiblePasswordEncryption:$false -CannotChangePassword:$false -DoesNotRequirePreAuth:$false -Identity:"CN=Kristi,CN=Users,DC=example,DC=com" -PasswordNeverExpires:$false -Server:$serverName".example.com" -UseDESKeyOnly:$false
    Set-ADUser -ChangePasswordAtLogon:$true -Identity:"CN=Kristi,CN=Users,DC=example,DC=com" -Server:$serverName".example.com" -SmartcardLogonRequired:$false
    Invoke-Command -ScriptBlock {net user Kristi "FooBerBez25"}
    Set-ADObject -Identity:"CN=Kristi,CN=Users,DC=example,DC=com" -Replace:@{"userAccountControl"="8389120"} -Server:$serverName".example.com"
    Add-ADPrincipalGroupMembership -Identity:"CN=Java Developers,CN=Users,DC=example,DC=com" -MemberOf:"CN=Developers,CN=Users,DC=example,DC=com" -Server:$serverName".example.com"
    Add-ADPrincipalGroupMembership -Identity:"CN=Kristi,CN=Users,DC=example,DC=com" -MemberOf:"CN=Java Developers,CN=Users,DC=example,DC=com" -Server:$serverName".example.com"
    New-ADOrganizationalUnit -Name:"Developers" -Path:"DC=example,DC=com" -ProtectedFromAccidentalDeletion:$true -Server:$serverName".example.com"
    New-ADUser -DisplayName:"Alosha" -GivenName:"Alosha" -Name:"Alosha" -Path:"CN=Users,DC=example,DC=com" -SamAccountName:"alosha" -Server:$serverName".example.com" -Type:"user"
    Add-ADPrincipalGroupMembership -Identity:"CN=Alosha,CN=Users,DC=example,DC=com" -MemberOf:"CN=Java Developers,CN=Users,DC=example,DC=com" -Server:$serverName".example.com"
    Set-ADAccountControl -AccountNotDelegated:$false -AllowReversiblePasswordEncryption:$false -CannotChangePassword:$false -DoesNotRequirePreAuth:$false -Identity:"CN=Alosha,CN=Users,DC=example,DC=com" -PasswordNeverExpires:$false -Server:$serverName".example.com" -UseDESKeyOnly:$false
    Set-ADUser -ChangePasswordAtLogon:$true -Identity:"CN=Alosha,CN=Users,DC=example,DC=com" -Server:$serverName".example.com" -SmartcardLogonRequired:$false
    Invoke-Command -ScriptBlock {net user Alosha "FooBarBaz25"}
    Set-ADObject -Identity:"CN=Alosha,CN=Users,DC=example,DC=com" -Replace:@{"userAccountControl"="8389120"} -Server:$serverName".example.com"
```
