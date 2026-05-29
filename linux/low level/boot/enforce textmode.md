# enforce textmode

in boot menue / grub push `e`

replace:
```
quiet splash
```
through:
```
systemd.unit=multi-user.target
```


`F10` or `Ctrl + X`
