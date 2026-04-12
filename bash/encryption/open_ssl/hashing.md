# HASHING
```
openssl dgst -sha256 -sign private_key.pem -out secret.txt.sha256 secret.txt
```

# VERIFYING
```
openssl dgst -sha256 -verify public_key.pem -signature secret.txt.sha256 secret.txt
```



