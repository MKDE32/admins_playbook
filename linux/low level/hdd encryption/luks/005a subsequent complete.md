
```
lsblk
```
>NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
>sda      8:0    0 232,9G  0 disk 
>├─sda1   8:1    0     1M  0 part 
>├─sda2   8:2    0   513M  0 part /boot/efi
>└─sda3   8:3    0 232,4G  0 part /
>sr0     11:0    1  1024M  0 rom  







# install luks
```
sudo apt update
sudo apt install cryptsetup
```



# check file system
```
sudo e2fsck -f /dev/sda3
```



# check version
```
cryptsetup --version
```
version2 is needed



# encryption
```
sudo cryptsetup reencrypt \
  --encrypt \
  --type luks2 \
  /dev/sda3
```


# open container
```
sudo cryptsetup open /dev/sda3 cryptroot
```


# mount
```
sudo mount /dev/mapper/cryptroot /mnt
sudo mount /dev/sda2 /mnt/boot/efi
```
```
sudo mount --bind /dev /mnt/dev
sudo mount --bind /proc /mnt/proc
sudo mount --bind /sys /mnt/sys
```
if necessary


# note uuid
```
sudo blkid /dev/sda3
```


# crypttab
```
sudo nano /mnt/etc/crypttab
cryptroot UUID=DEINE-LUKS-UUID none luks
```

# chroot
```
sudo chroot /mnt
```


# update initram
```
update-initramfs -u -k all
```

# update grub
```
update-grub
grep GRUB_ENABLE_CRYPTODISK /etc/default/grub
```
>GRUB_ENABLE_CRYPTODISK=y

if not available try `update-grub` again.



# restart
```
grub-install
exit
sudo reboot
```








