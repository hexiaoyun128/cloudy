# Nginx部署

* docker部署

```
 docker run -dit\
  --name gachainv2-wallet\
  -p 8600:80\
  -p 8643:443\
  -v /mnt/docker/gachainv2-wallet/web:/usr/share/nginx/html:rw\
  -v /mnt/docker/gachainv2-wallet/logs:/var/log/nginx/:rw\
  --restart=always nginx:1.13
```

* 自定义docker

获得conf文件

```
docker run --name tmp-nginx-container -d nginx:1.15.2
docker cp tmp-nginx-container:/etc/nginx/nginx.conf /host/path/nginx.conf
docker rm -f tmp-nginx-container
```



