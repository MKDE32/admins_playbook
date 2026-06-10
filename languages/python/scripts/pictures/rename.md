#benennt Bilder in das Format <Jahr.Monat.Tag> <Name> <laufende Nummer> um.
#Voraussetzungen: pip install pillow
#Unter Windows keine Sonderzeichen!
#Vorher Backups machen!
#Bildbetrachter schließen!

```python
import os
import re
from datetime import datetime
from PIL import Image
from PIL.ExifTags import TAGS

ORDNER = os.path.dirname(os.path.abspath(__file__))

NAME = input("Name für die Fotos (z.B. Urlaub Italien): ").strip()

NAME = re.sub(r'[\\/:*?"<>|]', '_', NAME)

def get_datum(pfad):
    try:
        bild = Image.open(pfad)
        exif = bild._getexif()
        if exif:
            for tag, value in exif.items():
                if TAGS.get(tag) == "DateTimeOriginal":
                    return datetime.strptime(value, "%Y:%m:%d %H:%M:%S")
    except Exception:
        pass

    return datetime.fromtimestamp(os.path.getmtime(pfad))



dateien = [
    f for f in os.listdir(ORDNER)
    if f.lower().endswith((".jpg", ".jpeg", ".png"))
] 

dateien.sort()
laufnummer = 1

for datei in dateien:
    alt = os.path.join(ORDNER, datei)

    if alt == os.path.abspath(__file__):
        continue

    datum = get_datum(alt)
    datum_str = datum.strftime("%Y.%m.%d")

    name_neu = f"{datum_str} {NAME} {laufnummer:03d}{os.path.splitext(datei)[1]}"
    neu = os.path.join(ORDNER, name_neu)

    print(f"{datei} > {name_neu}")
    os.rename(alt, neu)

    laufnummer += 1
```
