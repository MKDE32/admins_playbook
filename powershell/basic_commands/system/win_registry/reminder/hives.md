# REGISTRY HIVES
| Hive        | Drive Location                         | Description                          | Notes |
|-------------|----------------------------------------|--------------------------------------|-------|
| HKLM        | %SystemRoot%\System32\Config\           | Machine-wide settings                | All users, system config |
| HKCU        | %UserProfile%\NTUSER.DAT               | Current user settings                | Subset of HKU |
| HKU         | %SystemRoot%\System32\Config\ + users  | All user profiles                    | Includes HKCU |
| HKCR        | (Merged view: HKLM + HKCU)             | File associations & COM objects      | Virtual hive |
| HKCC        | (From HKLM\SYSTEM\CurrentControlSet)   | Current hardware profile             | Dynamic data |
| HKPD        | (Legacy / virtual)                     | Performance data                     | Rarely used |

