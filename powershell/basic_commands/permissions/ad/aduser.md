# GET-ADUSER
## FILTER
```
Get-ADUser -Filter *
Get-ADUser -Filter {EmailAddress -like '*greenhorn.corp'}
Get-ADUser -Filter {GivenName -like 'helene'}
```
## IDENTITY
```
Get-ADUser -Identity luser
Get-ADUser -Identity luser -Properties * | Format-Table Name,Enabled,GivenName,Surname,Title,Office,Mail
```

# NEW-ADUSER
```
New-ADUser -Name "luser" -Surname "Tanaka" -GivenName "Mori" -Office "Security" -OtherAttributes @{'title'="Sensei";'mail'="MTanaka@greenhorn.corp"} -Accountpassword (Read-Host -AsSecureString "AccountPassword") -Enabled $true 
```


# SET-ADUSER
```
Set-ADUser -Identity luser -Description " whateverm"
```
