```
cd ~/nextcloud
docker compose ps
```

```
nano ~/nextcloud/compose.yml
```

# compose.yaml
```
  collabora:
    image: collabora/code
    restart: unless-stopped
    environment:
      - username=admin
      - password=CHANGE_THIS_COLLABORA_PASSWORD
      - extra_params=--o:ssl.enable=false --o:ssl.termination=false
    ports:
      - "9980:9980"
    cap_add:
      - MKNOD
```

# start container
```
cd ~/nextcloud
docker compose up -d
docker compose ps
docker compose logs --tail=30 collabora
```

then install nextcloud office







