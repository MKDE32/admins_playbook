# GET
```
Get-LocalUser
Get-LocalUser administrator | get-member
Get-LocalUser administrator | Select-Object -Property *
Get-LocalUser * | Select-Object -Property Name,PasswordLastSet
Get-LocalUser * | Sort-Object -Property Name | Group-Object -property Enabled
```



# NEW
## BEST PRACTICE
```
$Password = Read-Host -AsSecureString
Set-LocalUser -Name "luser" -Password $Password -Description "whatever"
```
## NO PASSWORD
```
New-LocalUser -Name "luser" -NoPassword
```













