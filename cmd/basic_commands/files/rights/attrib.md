# EXAMPLE
```
attrib [+R|-R] [+A|-A] [+S|-S] [+H|-H] [Datei/Ordner] [/S] [/D]
```

# FLAGS
| Flag | Bedeutung                 |
| ---- | ------------------------- |
| `+R` | Schreibgeschützt setzen   |
| `-R` | Schreibschutz entfernen   |
| `+H` | Verstecken                |
| `-H` | Sichtbar machen           |
| `+S` | Als Systemdatei markieren |
| `-S` | Systemattribut entfernen  |
| `+A` | Archivbit setzen          |

| Option | Bedeutung                  |
| ------ | -------------------------- |
| `/S`   | Rekursiv: alle Unterordner |
| `/D`   | Auch Ordner bearbeiten     |
