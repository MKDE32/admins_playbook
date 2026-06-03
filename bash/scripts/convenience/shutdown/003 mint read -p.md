```
#!/bin/bash

xfce4-terminal -e "bash -c 'echo In wie vielen Minuten soll der Rechner herunterfahren?; read -p \"Minuten: \" minuten; shutdown -h +\$minuten; read'"
```
