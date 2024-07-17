use save in redis cli and `docker cp redis-container:/data/dump.rdb ./dump.rdb` to backup

## restore
`docker cp ./dump.rdb redis-container:/data/dump.rdb docker compose restart`
