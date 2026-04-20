# STANDART TROUBLESHOOTING PROCEDURE
```
netsh winsock reset (Resets Winsock catalog)
netsh int ip reset (Resets TCP/IP stack)
ipconfig /release (Releases current IP address)
ipconfig /renew (Renews IP address)
ipconfig /flushdns (Clears DNS cache)
```





# RESET NETWORK ADAPTER
```
netsh winsock reset
netsh int ip reset
```


# ENABLE7DISABLE NETWORK ADAPTER
```
netsh interface show interface
netsh interface set interface "Ethernet" admin=disable
netsh interface set interface "Ethernet" admin=enable
```


# RENEW IP ADRESS
```
ipconfig /release
ipconfig /renew
```


# EMPTY DNS CACHE
```
ipconfig /flushdns
```


# IF NOTHING HELPS
```
devmgmt.msc          delete network adapter
```



