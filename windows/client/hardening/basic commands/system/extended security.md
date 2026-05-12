# BITLOCKER
# ASLR
# MEMORY INTEGRETY
```
systeminfo | findstr /i "Virtualization"
reg add "HKLM\SYSTEM\CurrentControlSet\Control\DeviceGuard\Scenarios\HypervisorEnforcedCodeIntegrity" /v Enabled /t REG_DWORD /d 1 /f
```
# APPLOCKER
