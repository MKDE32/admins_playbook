# IE
# DELETE IE
```
dism /online /Disable-Feature /FeatureName:Internet-Explorer-Optional-amd64 /NoRestart
```

# EDGE
# DEACTIVATE IE MODE
```
reg add "HKLM\SOFTWARE\Policies\Microsoft\Edge" /v InternetExplorerIntegrationLevel /t REG_DWORD /d 0 /f
```






