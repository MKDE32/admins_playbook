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
## OVERWRITE
- `--sanact=0x2`
  - overwriting every nand cell
  - thorough
  - exhausting for the ssd

## BLOCK ERASE
- `--sanact=0x3`
  - deletes flash blocks
  - faster than overwriting
  - thorough


## CRYPTO ERASE
- `--sanact=0x4`
  - deletes decryption key
  - very fast
  - very safe
  - only possible if hardware (sed) encrypted
  - thorough

# LOGICAL LEVEL ERASE
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















