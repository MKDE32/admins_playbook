# PS V2
```
Get-WindowsOptionalFeature -Online -FeatureName MicrosoftWindowsPowerShellV2
Disable-WindowsOptionalFeature -Online -FeatureName MicrosoftWindowsPowerShellV2Root -NoRestart
```
# WIN SCRIPTHOST
```
reg add "HKLM\SOFTWARE\Microsoft\Windows Script Host\Settings" /v Enabled /t REG_DWORD /d 0 /f
```
# FAX
```
dism /online /Disable-Feature /FeatureName:FaxServicesClientPackage /NoRestart
```
# XPS
```
dism /online /Disable-Feature /FeatureName:Xps-Services /NoRestart
dism /online /Disable-Feature /FeatureName:Xps-Viewer /NoRestart
```
# OLD PRINTING FEATURES
```
dism /online /Disable-Feature /FeatureName:Printing-Foundation-Features /NoRestart
dism /online /Disable-Feature /FeatureName:Printing-XPSServices-Features /NoRestart
```
