```
Get-NetIPAddress -ifIndex 25
```
- Retrieves the IP configurations of each adapter. Similar to IPConfig.

```
Set-NetIPAddress -InterfaceIndex 25 -IPAddress 10.10.100.54 -PrefixLength 24
```
- Modifies the configuration of a network adapter.

```
New-NetIPAddress
```
- Creates and configures an IP address.
