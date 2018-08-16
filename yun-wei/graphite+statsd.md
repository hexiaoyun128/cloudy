## Graphite+StatsD监控

* Docker 部署

```
docker run -d\
 --name graphite\
 --restart=always\
 -p 8000:80\
 -p 8001-8002:2003-2004\
 -p 8003-8004:2023-2024\
 -p 8006:8125/udp\
 -p 8007:8126\
 -v /mnt/docker/graphite/var/log:/var/log\
 -v /mnt/docker/graphite/storage:/opt/graphite/storage\
 graphiteapp/graphite-statsd:1.1.3
```

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

| Host | Container | Service |
| :--- | :--- | :--- |
| 8000 | 80 | [nginx](https://www.nginx.com/resources/admin-guide/) |
| 8001 | 2003 | [carbon receiver - plaintext](http://graphite.readthedocs.io/en/latest/feeding-carbon.html#the-plaintext-protocol) |
| 8002 | 2004 | [carbon receiver - pickle](http://graphite.readthedocs.io/en/latest/feeding-carbon.html#the-pickle-protocol) |
| 8003 | 2023 | [carbon aggregator - plaintext](http://graphite.readthedocs.io/en/latest/carbon-daemons.html#carbon-aggregator-py) |
| 8004 | 2024 | [carbon aggregator - pickle](http://graphite.readthedocs.io/en/latest/carbon-daemons.html#carbon-aggregator-py) |
|  | 8080 | Graphite internal gunicorn port \(without Nginx proxying\). |
| 8006 | 8125 | [statsd](https://github.com/etsy/statsd/blob/master/docs/server.md) |
| 8007 | 8126 | [statsd admin](https://github.com/etsy/statsd/blob/v0.7.2/docs/admin_interface.md) |



