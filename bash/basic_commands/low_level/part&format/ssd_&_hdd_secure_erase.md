# SECURE ERASE USING HDPARM
to force the firmware to low level erase u first need to set a password
```
sudo hdparm --user-master u --security-set-pass pass /dev/sdX
```
then erase it. the enhanced flag is more thorough
```
sudo hdparm --user-master u --security-erase-enhanced pass /dev/sdX
```

# TROUBLESHOOTING
## FROZEN STATE
- You cannot bypass frozen state with force
- It’s enforced at hardware level from the bios
- totally normal behavior
- try this:
```
sudo hdparm -I /dev/sdX
```
> frozen

```
systemctl suspend
```
wake up the computer again..

```
sudo hdparm -I /dev/sdX
```
> not frozen

# MANUFACTURER TOOLS
- Samsung Magician
  - provides a linux based bootable iso
- Intel Memory and Storage Tool
  - provides a linux version
- Crucial Storage Executive
  - windows only
- western digital/ san disk
  - mostly windows




