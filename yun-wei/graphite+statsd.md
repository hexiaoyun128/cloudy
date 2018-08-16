## Graphite+StatsD监控

Docker 部署

```
docker run -d\
 --name graphite\
 --restart=always\
 -p 80:80\
 -p 2003-2004:2003-2004\
 -p 2023-2024:2023-2024\
 -p 8125:8125/udp\
 -p 8126:8126\
 -v /mnt/docker/graphite/graphite/configs:/opt/graphite/conf\
 -v /mnt/docker/graphite/graphite/data:/opt/graphite/storage\
 -v /mnt/docker/graphite/statsd:/opt/statsd\
 -v /mnt/docker/graphite/graphite/webapp/:/opt/graphite/webapp/graphite/functions/custom\
 -v /mnt/docker/graphite/nginx:/etc/nginx\
 -v /mnt/docker/graphite/etc/logrotate.d:/etc/logrotate.d\
 -v /mnt/docker/graphite/var/log:/var/log\
 graphiteapp/graphite-statsd
```



