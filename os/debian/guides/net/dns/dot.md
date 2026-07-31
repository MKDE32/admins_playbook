# set global
```
sudo nano /etc/systemd/resolved.conf
```
>DNS=8.8.8.8 1.1.1.1
>DNSOverTLS=yes

```
sudo systemctl restart systemd-resolved  
resolvectl status
```




# set wlan
```
nmcli connection show
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.ignore-auto-dns yes
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.dns "1.1.1.1 9.9.9.9"
sudo nmcli connection modify "FRITZ!Box 6670 LM" ipv4.dns-priority -42
sudo nmcli connection down "FRITZ!Box 6670 LM"
sudo nmcli connection up "FRITZ!Box 6670 LM"
sudo systemctl restart systemd-resolved
```



# test dnssec
```
dig @1.1.1.1 cloudflare.com +dnssec
```
>flags: ... ad ...;

oder

```
dig @1.1.1.1 dnssec-failed.org
```
>status: SERVFAIL
EDE: 9 (DNSKEY Missing): (no SEP matching the DS found for dnssec-failed.org.)




# test dot

```
sudo wireshark
```
```
sudo resolvectl flush-caches
resolvectl query google.com
```











