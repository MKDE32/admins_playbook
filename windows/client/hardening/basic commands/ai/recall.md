2. Recall deaktivieren

Recall speichert Bildschirm-Snapshots lokal und indexiert sie KI-gestützt.



Admin-CMD:
```
dism /Online /Get-Features | findstr /i recall
dism /Online /Disable-Feature /FeatureName:Recall /NoRestart
```
Prüfen/deaktivieren via DISM
reboot










