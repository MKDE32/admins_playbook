# OVERVIEW
## QUERY
### SHOW RUNTIME STATUS
```
sc query windefend
```
### FLAGS
`type= service`


## QC
### SHOW CONFIG
```
sc qc wuauserv
```


## SDSHOW
### SHOW SECURITY DESCRIPTOR
```
sc sdshow wuauserv
```
### PROPERTIES
- `D:` - the proceeding characters are DACL permissions
- `AU:` - defines the security principal Authenticated Users
- `A;;` - access is allowed
- `CC` - SERVICE_QUERY_CONFIG is the full name, and it is a query to the service control manager (SCM) for the service configuration
- `LC` - SERVICE_QUERY_STATUS is the full name, and it is a query to the service control manager (SCM) for the current status of the service
- `SW` - SERVICE_ENUMERATE_DEPENDENTS is the full name, and it will enumerate a list of dependent services
- `RP` - SERVICE_START is the full name, and it will start the service
- `LO` - SERVICE_INTERROGATE is the full name, and it will query the service for its current status
- `RC` - READ_CONTROL is the full name, and it will query the security descriptor of the service





# CONFIGURING
## START / STOP
```
sc stop windefend
sc start Spooler
```

## START / STOP TYPE
```
sc config wuauserv start= disabled
sc config wuauserv start= auto
```

## BINARY PATH
```
sc config wuauserv binPath=C:\Winbows\Perfectlylegitprogram.exe
```
