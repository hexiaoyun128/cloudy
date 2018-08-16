## Graphite+StatsD监控

Docker 部署

```
docker run -d\
 --name graphite\
 --restart=always\
 -p 8000:80\
 -p 8001-8002:2003-2004\
 -p 8003-8004:2023-2024\
 -p 8006:8125/udp\
 -p 8007:8126\
 -v /mnt/docker/graphite/conf/opt/graphite/conf:/opt/graphite/conf\
 -v /mnt/docker/graphite/conf/opt/statsd:/opt/statsd\
 -v /mnt/docker/graphite/conf/etc/nginx:/etc/nginx\
 -v /mnt/docker/graphite/conf/etc/logrotate.d:/etc/logrotate.d\
 -v /mnt/docker/graphite/var/log:/var/log\
 -v /mnt/docker/graphite/storage:/opt/graphite/storage\
 graphiteapp/graphite-statsd:1.1.3
```

配置文件[https://github.com/hopsoft/docker-graphite-statsd](https://github.com/hopsoft/docker-graphite-statsd) 本地：[/docker/docker-graphite-statsd/conf](/docker/docker-graphite-statsd/conf)



