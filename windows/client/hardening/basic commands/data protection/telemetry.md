```
Get-Service *diag* | Stop-Service
Get-Service *diag* | Set-Service -StartupType Disabled
```

```
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows\DataCollection" ^
/v AllowTelemetry /t REG_DWORD /d 0 /f
```















