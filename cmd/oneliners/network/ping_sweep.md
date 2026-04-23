```cmd
for /L %i in (1 1 254) do ping 172.16.5.%i -n 2 -w 250 | find "Reply"
```
