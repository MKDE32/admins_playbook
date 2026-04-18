
ZEIGT ADB VERSION
```
adb version
```
HELP
```
adb --help
```
DEVICES
```
adb devices
```

NEUSTART IM RECOVERY MODUS
```
adb reboot recovery
```

NEUSTART IN DEN BOOTLOADER
```
adb reboot bootloader
```

APK VON PC INSTALLIEREN
```
adb install XXXXX.apk
```

APK MIT  -s SERIAL VON PC INSTALLIEREN
```
adb -s emulator--5554 install appname.apk
```
`-s` kann mit adb devices nachgeschaut werden, ist nötig im fall mehrerer devices

ÖFFNEN DER ADB SHELL
```
adb shell
```

ZEIGT ADB LOGS AN
```
adb logcat
```
In den Logs können zb bei einer unsicher programmierten App unter Umständen die Login Daten/Passwörter enthalten sein







