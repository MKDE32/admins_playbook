```
docker volume ls

docker volume inspect nextcloud_nextcloud_data

docker volume inspect nextcloud_db_data
```
# backup
```
docker compose exec -T db pg_dump \
  -U nextcloud \
  -d nextcloud \
  > backups/nextcloud-db.sql

ls -lh backups/nextcloud-db.sql
```

# restore

```
cat backups/nextcloud-db.sql | docker compose exec -T db psql \
  -U nextcloud \
  -d nextcloud
```















