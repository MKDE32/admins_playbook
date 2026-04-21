# LOAD REGISTRY
```
reg load HKLM\OFFLINE C:\Windows\System32\Config\SYSTEM
```



# OPEN REGISTRY
```
regedit
```



# SHOW DRIVERS
```
dism /image:C:\ /get-drivers
```
or  
`HKLM\OFFLINE\ControlSet001\Services`



# DRIVER DISABLE
`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\<Treibername>`  
`Start = 4`

| Wert | Bedeutung                |
| ---- | ------------------------ |
| 0    | Boot (sehr früh geladen) |
| 1    | System                   |
| 2    | Automatic                |
| 3    | Manual                   |
| 4    | Disabled                 |











