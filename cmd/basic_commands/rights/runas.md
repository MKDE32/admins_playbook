# START AS OTHER USER
```
runas /user:DOMAIN\User cmd
runas /user:Administrator "notepad.exe"
```




# START APP WITH OTHER RIGHTS
```
set __compat_layer=runasinvoker
```
after that, start the app
`runasinvoker`  
`runasadmin`





