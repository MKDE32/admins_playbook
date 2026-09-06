```
sudo nano /etc/systemd/system/nextcloud-backup.service
```

```
[Unit]
Description=Nextcloud Backup
Requires=docker.service
After=docker.service

[Service]
Type=oneshot
ExecStart=/usr/local/sbin/nextcloud-backup
```



```
sudo nano /etc/systemd/system/nextcloud-backup.timer
```

```
[Unit]
Description=Daily Nextcloud Backup

[Timer]
OnCalendar=*-*-* 02:00:00
Persistent=true

[Install]
WantedBy=timers.target
```

