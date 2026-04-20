as of Windows 8.1, Windows 10 und Windows Server 2012 R2

# EXAMPLES
```
DISM /Online /Cleanup-image /ScanHealth
```
Überprüft auf Probleme im Komponentenspeicher, ist gründlicher als `/CheckHealth`

```
DISM /Online /Cleanup-image /RestoreHealth
```
Repariert Probleme im Komponentenspeicher





















Wenn Sie diesen Befehl ausführen, verwendet DISM Windows Update, um die Dateien bereitzustellen, die zum Beheben von Beschädigungen erforderlich sind.
Wenn ihr Windows Updateclient jedoch bereits beschädigt ist, verwenden Sie eine ausgeführte Windows Installation als Reparaturquelle. 
Funktioniert nur wenn das Image die selbe Build Nummer ???oder???höher??? wie die Installation hat auch 32/64 bit muss stimmen.



bei einer install.wim
DISM /Online /Cleanup-Image /RestoreHealth /Source:wim:D:\sources\install.wim:1 /LimitAccess

bei einer install.esd
DISM /Online /Cleanup-Image /RestoreHealth /Source:esd:D:\sources\install.esd:1 /LimitAccess

anschließend können die Systemdateien mit sfc /scannow repariert werden
