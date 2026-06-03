# IMPORT PUBLIC KEY OFFLINE / ONLINE
```
gpg --import key.asc
gpg --keyserver hkps://keyserver.ubuntu.com --recv-keys <KEYID>
```

# COMPARE FINGERPRINT
```
gpg --fingerprint 0x46181433FBB75451
```

# CHECK SIGNATURE
```
gpg --verify SHA256SUMS.gpg SHA256SUMS
```

# CHECK ISO
```
sha256sum -c SHA256SUMS
```
