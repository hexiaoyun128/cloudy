```
docker run  -dit --name gachain-postgres -p 5432:5432 -e POSTGRES_PASSWORD=GachainPostgres. -e PGDATA=/mnt/docker_container/gachain-postgres  --restart=always postgres:10.3 
```



