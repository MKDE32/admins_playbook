# overview
| Option            | Purpose                         |
| ----------------- | ------------------------------- |
|`-D`               | display interfaces|



# source / dest
| Option            | Purpose                         |
| ----------------- | ------------------------------- |
| `-i any`          | Capture all interfaces       |
| `-r file.pcap`    | Read PCAP file                  |
| `-w file.pcap`    | Save capture                    |



# filtering
| Option            | Purpose                         |
| ----------------- | ------------------------------- |
|`-n`               |no number to name converting|
| `-nn`             | Disable DNS and port resolution |
| `-v / -vv / -vvv` | verbosity              |
|`-e`               |ethernet header|
| `-c 100`          | Stop after 100 packets          |
| `-s 0`            | Capture full packets            |
|`-q`               |less protocol information|
|`-l`               |pipeing into tools like grep     |


# output format
| Option            | Purpose                         |
| ----------------- | ------------------------------- |
| `-X`              |  hex + ASCII                |
| `-A`              |  ASCII               |
|`-XX`              |like -Xe|
|`-S`               |absolute sequence number|


