```
nmcli connection show
```

```
nmcli connection modify <NAME> ipv4.dns "1.1.1.1 8.8.8.8"
nmcli connection modify <NAME> ipv4.ignore-auto-dns yes
nmcli connection up <NAME>
```











