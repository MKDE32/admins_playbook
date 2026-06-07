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
































