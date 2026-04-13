# OVERVIEW
## INSTALL
```
sudo apt update & sudo apt install nvme-cli
```
## LIST NVME DEVICES
```
sudo nvme list
```

## STATUS
```
sudo nvme sanitize-log /dev/nvme0n1
```





# CONTROLER LEVEL ERASE (very thorough)
## EXAMPLE
```
sudo nvme sanitize /dev/nvme0n1 --sanact=0x2
```

## FLAGS
### BLOCK ERASE
- `--sanact=0x2`
  - deletes flash blocks directly
  - faster than overwriting
  - more thorough than overwrite

### OVERWRITE
- `--sanact=0x3`
  - abstraction layers exist

### CRYPTO ERASE
- `--sanact=0x4`
  - deletes only the decryption key
  - very fast
  - only possible if hardware (sed) encrypted





# LOGICAL LEVEL ERASE (faster)

## EXAMPLE
```
sudo nvme format /dev/nvme0n1 --ses=2
```

## FLAGS
`--ses=1` 
 - `0` normal namespace level erase
 - `1` crypto erase (only possible if device has a hardware encryption)
 - `2` advanced namespace level erase















