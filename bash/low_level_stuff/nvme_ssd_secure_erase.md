# CONTROLER LEVEL ERASE (very thorough)
## STATUS
```
sudo nvme sanitize-log /dev/nvme0n1
```

## EXAMPLE
```
sudo nvme sanitize /dev/nvme0n1 --sanact=0x3
```

## FLAGS
### BLOCK ERASE
- `--sanact=0x2`
  - deletes flash blocks at controler level
  - faster than overwriting
  - deletes controler based mapping too
  - thats why very thorough

### OVERWRITE
- `--sanact=0x3`
  - overwriting nand cell
  - exhausting for the ssd
  - may not hit every nand cell

### CRYPTO ERASE
- `--sanact=0x4`
  - deletes decryption key
  - very fast
  - only possible if hardware (sed) encrypted
  - standart

# LOGICAL LEVEL ERASE
## INSTALL
```
sudo apt update & sudo apt install nvme-cli
```
## EXAMPLE
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















