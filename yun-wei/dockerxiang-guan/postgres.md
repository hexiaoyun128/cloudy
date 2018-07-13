# Docker运行PostgreSQL

```
docker run -dit --name gachainv2-postgres -p 5433:5432 -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=gachainv2 -e PGDATA=/mnt/docker_gachainv2/gachainv2-postgres --restart=always postgres:10.3
```







