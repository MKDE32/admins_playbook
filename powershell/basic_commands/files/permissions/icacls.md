# OVERVIEW
```
icacls 'C:\Pictures\'
```



# GRANT
## EXAMPLES
```
icacls 'C:\Pictures\' /grant 'Everyone:(OI)(CI)(R)'
icacls .\ /grant Everyone:(OI)(CI)F /T
icacls C:\Ordner /grant:r Benutzer:(R,W) /T
```
## FLAGS
`/grant:r` substitute instead of add  
`/T` recursive



# REMOVE
```
icacls 'C:\Pictures\' /remove everyone
```



# INHERITANCE
## REMOVE
```
icacls .\ /inheritance:d
```



# OWNERSHIP
## SET
```
icacls C:\Ordner /setowner Benutzer /T
```



# RIGHTS
```
                N - no access
                F - full access
                M - modify access
                RX - read and execute access
                R - read-only access
                W - write-only access
                D - delete access


        a comma-separated list in parentheses of specific rights:
                DE - delete
                RC - read control
                WDAC - write DAC
                WO - write owner
                S - synchronize
                AS - access system security
                MA - maximum allowed
                GR - generic read
                GW - generic write
                GE - generic execute
                GA - generic all
                RD - read data/list directory
                WD - write data/add file
                AD - append data/add subdirectory
                REA - read extended attributes
                WEA - write extended attributes
                X - execute/traverse
                DC - delete child
                RA - read attributes
                WA - write attributes


        inheritance rights may precede either form and are applied
        only to directories:
                (OI) - object inherit
                (CI) - container inherit
                (IO) - inherit only
                (NP) - don't propagate inherit
                (I) - permission inherited from parent container
```
