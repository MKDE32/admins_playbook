# CONTROLER LEVEL ERASE (very thorough)
## STATUS
```
sudo nvme sanitize-log /dev/nvme0n1
```

## EXAMPLE
```
sudo nvme sanitize /dev/nvme0n1 --sanact=0x2
```

## FLAGS
### BLOCK ERASE
- `--sanact=0x2`
  - deletes flash blocks directly without any mapping
  - faster than overwriting
  - very thorough

### OVERWRITE
- `--sanact=0x3`
  - overwriting nand cells
  - exhausting for the ssd
  - may not hit every nand cell

### CRYPTO ERASE
- `--sanact=0x4`
  - deletes decryption key
  - very fast
  - only possible if hardware (sed) encrypted

# LOGICAL LEVEL ERASE (faster)
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
 - `0` normal namespace level erase
 - `1` crypto erase (only possible if device has a hardware encryption)
 - `2` advanced namespace level erase















