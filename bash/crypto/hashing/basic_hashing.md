# MD5
```
md5sum file.txt > file.txt.md5
```
```
md5sum -c file.txt.md5
```

# SHA 1
```
shasum file.txt > file.txt.sha1
```
```
shasum -c file.txt.sha1
```

# SHA 256
## CALCULATE HASH
```
shasum -a 256 file.txt
```

## SAVE HASH
```
shasum -a 256 file.txt > file.txt.sha256
```

## INTEGRITYCHECK
```
shasum -c file.txt.sha256
```

## CALCULATE HASH
```
sha256sum Windows.iso
```

