# USING HDPARM
```
sudo hdparm --user-master u --security-set-pass pass /dev/sdX
```

```
sudo hdparm --user-master u --security-erase pass /dev/sdX
```

# TROUBLESHOOTING
## FROZEN STATE
- You cannot bypass frozen state with force
- It’s enforced at hardware level
- totally normal behavior
- try this:
```
sudo hdparm -I /dev/sdX
```
> Security:
>     frozen

```
systemctl suspend
```

```
sudo hdparm -I /dev/sdX
```
> not frozen






    
# NVME SECURE ERASE
```
sudo apt update & sudo apt install nvme-cli
```

```
sudo nvme list
```

```
sudo nvme format /dev/nvme0n1 --ses=1
```

# MANUFACTURER TOOLS
- Samsung Magician
- Crucial Storage Executive
- Intel Memory and Storage Tool







