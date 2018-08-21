Docker部署

获得配置文件

```
docker run -d --name elastic -e transport.host=0.0.0.0   elasticsearch:5.6.10
docker cp elastic:/usr/share/elasticsearch/config ./
```

修改配置文件并放到对应的目录

```
docker run -d --name elastic -e transport.host=0.0.0.0 -v /mnt/docker_container/elasticsearch/config:/usr/share/elasticsearch/config  -v /mnt/docker_container/elasticsearch/esdata:/usr/share/elasticsearch/data elasticsearch:5.6.10
```



