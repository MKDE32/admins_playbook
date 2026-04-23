# SEARCH FOR SERVICES
```
Get-Service | Select-Object -Property *
Get-Service | ft DisplayName,Status
get-service | Select-Object -Property DisplayName,Name,Status | Sort-Object DisplayName | fl
```



# SEARCH FOR SERVICE WITH -LIKE
```
Get-Service | where DisplayName -like '*Defender*'
Get-Service | where DisplayName -like '*Defender*' | Select-Object -Property *
Get-Service | where DisplayName -like '*Defender*' | ft DisplayName,ServiceName,Status
```



# SEARCH FOR SERVICE
```
get-service WinDefend
get-service spooler | Select-Object -Property Name, StartType, Status, DisplayName
```

