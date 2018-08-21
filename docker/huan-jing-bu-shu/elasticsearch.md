Docker部署

```
docker run -d  -e transport.host=0.0.0.0 -v /mnt/docker_container/elasticsearch/config:/usr/share/elasticsearch/config  -v /mnt/docker_container/elasticsearch/esdata:/usr/share/elasticsearch/data elasticsearch:5.6.10
```



