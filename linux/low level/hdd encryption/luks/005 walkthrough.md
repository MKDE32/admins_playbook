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








