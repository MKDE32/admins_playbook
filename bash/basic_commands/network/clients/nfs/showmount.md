# Show NFS Shares
```
showmount -e 192.168.1.10
```



# Mounting NFS Share
```
mkdir target-NFS
mount -t nfs 10.129.14.128:/ ./target-NFS/ -o nolock
```
