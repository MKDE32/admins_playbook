
```
# Profil anlegen falls fehlt
if (!(Test-Path $PROFILE)) {
    New-Item -Type File -Path $PROFILE -Force | Out-Null
}

# Funktion hinzufügen (falls noch nicht drin)
if (-not (Select-String -Path $PROFILE -Pattern "function dsk" -Quiet)) {
    Add-Content $PROFILE 'function dsk { Set-Location ([Environment]::GetFolderPath("Desktop")) }'
}

# Profil neu laden
. $PROFILE
```
