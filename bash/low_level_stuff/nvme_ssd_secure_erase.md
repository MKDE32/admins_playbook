# CONTROLER LEVEL ERASE
## ???
```
sudo nvme sanitize /dev/nvme0n1
```

## STATUS
```
sudo nvme sanitize-log /dev/nvme0n1
```

## OVERWRITE
```
sudo nvme sanitize /dev/nvme0n1 --sanact=0x2
```
- overwriting every nand cell
- very thorough

## BLOCK ERASE
```
sudo nvme sanitize /dev/nvme0n1 --sanact=0x3
```



# NVME FORMAT
```
sudo apt update & sudo apt install nvme-cli
```

```
sudo nvme list
```

```
sudo nvme format /dev/nvme0n1 --ses=1
```

## FLAGS
`--ses=1` 
 - `0` normal
 - `1` crypto erase (only possible if device has a hardware encryption)
 - `2` user data erase















