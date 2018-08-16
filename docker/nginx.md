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

创建目录`nginx-react`,并将`nginx.conf`复制到该目录下，修改`nginx.conf文件`

```

```

新建`Dockerfile`文件,输入以下内容

```
FROM nginx：1.15.2
COPY nginx.conf /etc/nginx/nginx.conf
```



