# INFO
```
Get-WinEvent -ListLog *
Get-WinEvent -ListLog Security
```


# QUERY FOR RECENT 5
```
Get-WinEvent -LogName 'Security' -MaxEvents 5 | Select-Object -ExpandProperty Message
```


# QUERY FOR EVENT ID
```
Get-WinEvent -FilterHashTable @{LogName='Security';ID='4625'} | Select-Object -ExpandProperty Message
Get-WinEvent -FilterHashtable @{LogName='Security';Id=4625;StartTime=[datetime]'2022-11-29 00:00:00';EndTime=[datetime]'2022-11-29 23:59:59'} | Select-Object TimeCreated,@{Name='Account';Expression={$_.Properties[5].Value}}
```


# QUERY FOR SEVERITY LEVEL
```
Get-WinEvent -FilterHashTable @{LogName='System';Level='1'} | select-object -ExpandProperty Message
```


















