# FSCK
```
sudo fsck /dev/sda
```
`-p` prevent from showing minor errors

# E2FSCK
```
sudo e2fsck /dev/sda
```
- for ext, ext 2, ext 3, ext 4

# ADD FSCK TO BOOT SEQUENCE
## Debian based
- Edit the rcS file: $ sudo vi /etc/default/rcS
- Add the following command to the rcS file: FSCKFIX=yes
## CentOS
- Create or edit a file named autofsck: $ sudo vi /etc/sysconfig/autofsck
- Add the following command to the autofsck file: AUTOFSCK_DEF_CHECK=yes










