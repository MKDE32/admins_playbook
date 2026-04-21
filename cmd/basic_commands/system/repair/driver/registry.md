reg load HKLM\OFFLINE C:\Windows\System32\Config\SYSTEM

regedit

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\<Treibername>


Start = 4 (disabled)
| Wert | Bedeutung                |
| ---- | ------------------------ |
| 0    | Boot (sehr früh geladen) |
| 1    | System                   |
| 2    | Automatic                |
| 3    | Manual                   |
| 4    | Disabled                 |











