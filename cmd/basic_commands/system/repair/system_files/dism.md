# IDENTIFY DRIVE
## SHOW VOLUME (IF NEEDED)
```
diskpart
```
```
list volume
```
## ASSIGN DRIVE LETTER (IF NEEDED)
```
select volume 1
assign letter=S
exit
```





# RESTORE COMPONENT STORE
## REPAIR WITH WIN UPDATE
```
DISM /Online /Cleanup-Image /ScanHealth
DISM /Online /Cleanup-image /RestoreHealth
```





## REPAIR WITH INSTALLATION MEDIUM
### REPAIR USING .WIM OR .ESD
```
DISM /Online /Cleanup-Image /RestoreHealth /Source:wim:D:\sources\install.wim:1 /LimitAccess
DISM /Online /Cleanup-Image /RestoreHealth /Source:esd:D:\sources\install.esd:1 /LimitAccess
```



## REPAIR COMPLETELY OFFLINE
```
DISM /Image:C:\ /Cleanup-Image /ScanHealth
DISM /Image:C:\ /Cleanup-Image /RestoreHealth
```





# REPAIR SYSTEM FILES
## SFC
```
sfc /scannow
```

## SFC FROM RECOVERYMEDIUM
```
sfc /offbootdir=C:\ /offwindir=C:\windows /scannow
```





# INFO
- DISM repairs the “source” → SFC repairs the “files”
- Replace D: with your installation media drive
- Index :1 may vary depending on Windows edition
- Source must match:
  - Same Windows version/build or newer
  - Same architecture (x64 / x86 / ARM)











