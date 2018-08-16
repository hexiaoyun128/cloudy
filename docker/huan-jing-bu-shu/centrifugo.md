### Centrifugo消息推送

* Docker部署

```
mkdir /mnt/docker/centrifugo
cd /mnt/docker/centrifugo
vim config.json
```

输入下面的内容

```
{
  "secret": "gachain-secret",
  "web": true,
  "admin_password": "GachainCloudy2018",
  "admin_secret": "gachain-secret",
  "namespaces": [
    {
      "name": "public",
      "anonymous": true,
      "publish": true,
      "watch": true,
      "presence": true,
      "join_leave": true,
      "history_size": 10,
      "history_lifetime": 30,
      "recover": true
    }
  ]
}
```

```
docker run  --name centrifugo -dit --ulimit nofile=65536:65536 -v /mnt/docker/centrifugo:/centrifugo -p 7080:8000 centrifugo/centrifugo:1.8.0 centrifugo -c config.json
```





