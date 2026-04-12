

# GENERATING PRIVATE KEY
```
openssl genrsa -out private_key.pem 2048
```

# GENERATING PUBLIC KEY
```
openssl rsa -in private_key.pem -outform PEM -pubout -out public_key.pem
```

# ENCRYPT
```
openssl rsautl -encrypt -pubin -inkey public_key.pem -in secret.txt -out secret.enc
```

# DECRYPT
```
openssl rsautl -decrypt -inkey private_key.pem -in secret.enc
```








