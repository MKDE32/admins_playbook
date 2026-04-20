# EXAMPLE
```
chkdsk C: /f /r
```

# FLAGS
`/f` logical file system repair

`/r` recovers bad sectors, recover readable files



  /F                  Behebt Fehler auf dem Datenträger.
  /R                  Sucht beschädigte Sektoren und stellt lesbare
                      Informationen wieder her
                      (bedingt /F, wenn /scan nicht angegeben wird).
  /I                  Nur NTFS: Führt eine gelockerte Überprüfung der
                      Indexeinträge aus.
  /C                  Nur NTFS: Überspringt das Überprüfen von Zyklen
                       innerhalb der Ordnerstruktur.
  /B                  Nur NTFS: Wertet fehlerhafte Cluster auf dem Volume
                      erneut aus (bedingt /R).
  /scan               Nur NTFS: Führt eine Onlineüberprüfung im Volume aus.
  /forceofflinefix    Nur NTFS: (Muss mit "/scan" verwendet werden.)
                      Umgeht die gesamte Onlinereparatur. Alle gefundenen
                      Fehler werden in die Warteschlange für die Offline-
                      reparatur eingereiht (d. h. "chkdsk /spotfix").
  /perf               Nur NTFS: (Muss mit "/scan" verwendet werden.)
                      Verwendet mehr Systemressourcen, um eine Überprüfung so
                      schnell wie möglich abzuschließen. Dies kann sich negativ
                      auf die Leistung anderer im System ausgeführter Tasks
                      auswirken.
  /spotfix            Nur NTFS: Repariert Beschädigungen auf dem Volume.
  /sdcleanup          Nur NTFS: Führt eine Garbage Collection für nicht
                      benötigte Sicherheitsbeschreibungsdaten aus (bedingt /F).
  /offlinescanandfix  Führt Offlineüberprüfung und Reparatur auf dem Volume aus.
  /freeorphanedchains Nur FAT/FAT32/exFAT: Gibt verwaiste Clusterketten frei,
                      anstatt ihren Inhalt wiederherzustellen.
  /markclean          Nur FAT/FAT32/exFAT: Markiert das Volume als fehlerfrei,
                      wenn keine Beschädigungen erkannt wurden, selbst wenn
                      "/F" nicht angegeben wurde.




  
