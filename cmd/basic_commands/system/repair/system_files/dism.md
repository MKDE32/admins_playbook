# IDENTIFY DRIVE IF NEEDED
```
diskpart
```
```
list volume
exit
```


# RESTORE COMPONENT STORE
## SCAN FOR CORRUPTION
```
DISM /Online /Cleanup-Image /ScanHealth
```

## ONLINE REPAIR
```
DISM /Online /Cleanup-image /RestoreHealth
```

## OFFLINE REPAIR .WIM
```
DISM /Online /Cleanup-Image /RestoreHealth /Source:wim:D:\sources\install.wim:1 /LimitAccess
```

## OFFLINE REPAIR .ESD
```
DISM /Online /Cleanup-Image /RestoreHealth /Source:esd:D:\sources\install.esd:1 /LimitAccess
```
- Replace D: with your installation media drive
- Index :1 may vary depending on Windows edition
- Source must match:
  - Same Windows version/build or newer
  - Same architecture (x64 / x86 / ARM)






# EXAMPLES
```
DISM /Online /Cleanup-image /ScanHealth
```
scans for problems in win componentstore




# FLAGS
`/Online /Cleanup-image /RestoreHealth` repairs with win update

`/Online /Cleanup-image /RestoreHealth /Source:wim:D:\sources\install.wim:1 /LimitAccess` restores with install.wim

`/Online /Cleanup-image /RestoreHealth /Source:esd:D:\sources\install.esd:1 /LimitAccess` restores with install.esd



# INFO
Wenn Sie diesen Befehl ausführen, verwendet DISM Windows Update, um die Dateien bereitzustellen, die zum Beheben von Beschädigungen erforderlich sind.  
Wenn ihr Windows Updateclient jedoch bereits beschädigt ist, verwenden Sie eine ausgeführte Windows Installation als Reparaturquelle.  
Funktioniert nur wenn das Image die selbe Build Nummer ???oder???höher??? wie die Installation hat auch 32/64 bit muss stimmen.  
anschließend können die Systemdateien mit sfc /scannow repariert werden  









start diskpart
diskpart

show volume letter
list volume

repair system files
sfc /offbootdir=C:\ /offwindir=C:\windows /scannow
offbootdir is the system-reserved-partition, if the command doesnt work and offbootdir has no volume letter get it a volume letter
diskpart
select volume 1
assign letter=S
exit

if not possible to repair try the following and repeat sfc..
DISM /Image:C:\ /Cleanup-Image /scanhealth
DISM /Image:C:\ /Cleanup-Image /RestoreHealth












