# NVME SECURE ERASE
```
sudo apt update & sudo apt install nvme-cli
```

```
sudo nvme list
```

```
sudo nvme format /dev/nvme0n1 --ses=1
```
