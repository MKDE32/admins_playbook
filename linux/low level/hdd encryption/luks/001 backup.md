```
sudo rsync -aAXHv \
  --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} \
  / \
  /pfad/zum/backup
```
```
sudo dd if=/dev/sda of=/backup/sda.img bs=64M status=progress
```










  
