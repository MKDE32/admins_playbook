```
@echo off

set /p minuten=Nach wie vielen Minuten herunterfahren? 

set /a sekunden=%minuten%*60


shutdown -s -t %sekunden%
echo PC wird in %minuten% Minuten heruntergefahren.
timeout /t 10
```
