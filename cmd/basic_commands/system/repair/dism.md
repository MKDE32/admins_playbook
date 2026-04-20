# EXAMPLES
```
DISM /Online /Cleanup-image /ScanHealth
```
scans for problems in win componentstore

```
DISM /Online /Cleanup-image /RestoreHealth
```
repairs with win update


# FLAGS
`/Online /Cleanup-image /RestoreHealth` repairs with win update

`/Online /Cleanup-image /RestoreHealth /Source:wim:D:\sources\install.wim:1 /LimitAccess` restores with install.wim

`/Online /Cleanup-image /RestoreHealth /Source:esd:D:\sources\install.esd:1 /LimitAccess` restores with install.esd



# INFO
Wenn Sie diesen Befehl ausführen, verwendet DISM Windows Update, um die Dateien bereitzustellen, die zum Beheben von Beschädigungen erforderlich sind.  
Wenn ihr Windows Updateclient jedoch bereits beschädigt ist, verwenden Sie eine ausgeführte Windows Installation als Reparaturquelle.  
Funktioniert nur wenn das Image die selbe Build Nummer ???oder???höher??? wie die Installation hat auch 32/64 bit muss stimmen.  
anschließend können die Systemdateien mit sfc /scannow repariert werden  
