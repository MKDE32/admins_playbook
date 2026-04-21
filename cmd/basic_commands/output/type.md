# CMD `type` Cheatsheet (Admin & IT-Security)

## 🔹 Basics
```
type file.txt
```
→ Inhalt anzeigen

type *.log
→ mehrere Dateien (Wildcard)

type file1.txt file2.txt
→ mehrere Dateien hintereinander ausgeben

## 🔹 Umleitung (wichtig!)

type file.txt > out.txt
→ überschreiben

type file.txt >> out.txt
→ anhängen

type file1.txt file2.txt > combined.txt
→ Dateien zusammenführen

## 🔹 Pipes (sehr nützlich)

type file.txt | more
→ seitenweise anzeigen

type file.txt | find "error"
→ einfache Suche

type file.txt | findstr "error warn"
→ mehrere Begriffe (besser als find)

type file.txt | sort
→ Ausgabe sortieren

## 🔹 Log-Analyse (Security/Admin)

type logfile.log | findstr /i "error failed denied"
→ typische Fehler/Angriffe filtern

type logfile.log | findstr /i /c:"login failed"
→ exakte Phrase suchen

type *.log | findstr /i "password"
→ mehrere Logs durchsuchen

## 🔹 Kombi mit for (mächtig)

for %f in (*.log) do type "%f"
→ alle Logs einzeln ausgeben

for %f in (*.log) do type "%f" | findstr /i "error"
→ alle Logs nach Fehlern durchsuchen

## 🔹 Leere Datei erstellen

type nul > empty.txt

## 🔹 Quick Debug Tricks

type file.txt | clip
→ Inhalt in Zwischenablage kopieren

type file.txt | find /c "error"
→ zählt Treffer

type file.txt | more +50
→ ab Zeile 50 anzeigen

## ⚠️ Einschränkungen

* keine Navigation (kein Scrollen)
* große Dateien = unübersichtlich
* zeigt Binärdaten als „Müll“

## 🧠 Tipp

Für große Dateien besser:
more file.txt
oder:
type file.txt | more

## 🔚 Fazit

type = schnell, simpel, perfekt für:

* Logs prüfen
* Dateien kombinieren
* Pipelines bauen


