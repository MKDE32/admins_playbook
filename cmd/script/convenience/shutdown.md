```
@echo off

set /p minuten=Nach wie vielen Minuten herunterfahren? 

set /a sekunden=%minuten%*60

echo PC wird in %minuten% Minuten heruntergefahren.
shutdown -s -t %sekunden%
```
