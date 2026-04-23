# DOMAIN INSTALL RSAT
# 1. RSAT installieren (Windows 10/11)
```
Get-WindowsCapability -Name RSAT* -Online | Add-WindowsCapability -Online
```

# Optional: nur AD Tools
```
Get-WindowsCapability -Name RSAT.ActiveDirectory* -Online | Add-WindowsCapability -Online
```

# 2. Installation prüfen
```
Get-WindowsCapability -Name RSAT.ActiveDirectory* -Online
```

# 3. AD-Modul prüfen
```
Get-Module -Name ActiveDirectory -ListAvailable
```

# 4. Modul laden
```
Import-Module ActiveDirectory
```

# 5. Voraussetzung: Domain Join prüfen
```
whoami
systeminfo | findstr /B /C:"Domain"
```

# 6. Test: AD erreichbar?
```
Get-ADDomain
Get-ADUser -Filter *
```

# 7. GUI Tools starten
`dsa.msc`        # Active Directory Users and Computers  
`gpmc.msc`       # Group Policy Management


# TROUBLESHOOTING

- Kein Domain Join
- DNS falsch
- Keine ad Berechtigung
- Verbindung zum fehlt
- Execution Policy blockiert


