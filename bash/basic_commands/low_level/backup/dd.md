# PREPARING
```
lsblk -b
```
or
```
blockdev --getsize64 /dev/sdb
```
checking exact disksize

```
unmount /dev/sdd
```
usb unmount


# CLONING WITH DD
```
sudo dd if=/dev/sdd of=~/Desktop/image.img bs=8M status=progress
```
cloning drive to desktop

```
dd if=/dev/sdb1 of=partition.img
```
cloning a partition


# INFO
-dd copys byte by byte  
-dd copys empty space too  
-dd overwrites everything, be careful!!





