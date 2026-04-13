# ATA SECURE ERASE
```
sudo hdparm --user-master u --security-set-pass pass /dev/sdX
```
```
sudo hdparm --user-master u --security-erase pass /dev/sdX
```

# MANUFACTURER TOOLS
- Samsung Magician
- Crucial Storage Executive
- Intel Memory and Storage Tool

# NVME TOOLS
```
sudo apt update
sudo apt install nvme-cli
```

```
nvme format /dev/nvme0n1
```









