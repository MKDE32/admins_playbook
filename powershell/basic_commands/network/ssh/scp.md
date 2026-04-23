# EXAMPLES

Upload
```
scp file.txt admin@192.168.1.10:/tmp/
```

Download
```
scp admin@192.168.1.10:/tmp/file.txt .
```

Upload folder with key + port
```
scp -r -i C:\key.pem -P 2222 folder admin@host:/var/www/
```





# FLAGS

| Option | Description |
|--------|-------------|
| -r     | Recursive copy (directories) |
| -P     | Specify port (uppercase P!) |
| -i     | Identity file (private key) |
| -v     | Verbose output (debugging) |
| -C     | Enable compression |
| -q     | Quiet mode |
| -l     | Limit bandwidth (Kbit/s) |





# LOCAL TO REMOTE

Copy file:
scp file.txt user@host:/path/

Copy directory:
scp -r folder user@host:/path/





# REMOTE TO LOCAL

Copy file:
scp user@host:/path/file.txt .

Copy directory:
scp -r user@host:/path/folder .





# REMOTE TO REMOTE

scp user1@host1:/path/file user2@host2:/path/




  


