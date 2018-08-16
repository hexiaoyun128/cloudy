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
user  nginx;
worker_processes  1;

error_log  /var/log/nginx/error.log warn;
pid        /var/run/nginx.pid;


events {
    worker_connections  1024;
}

location / {
     try_files $uri $uri/ @router;
     index index.html;
 }

location @router {
    rewrite ^.*$ /index.html last;
}

http {
    include       /etc/nginx/mime.types;
    default_type  application/octet-stream;

    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    keepalive_timeout  65;

    #gzip  on;

    include /etc/nginx/conf.d/*.conf;
}
```

新建`Dockerfile`文件,输入以下内容

```
FROM nginx:1.15.2
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]
```

编译

```
docker build -t react-nginx .
```

```
docker run -dit\
 --name gachain-nginx\
 -p 8080:80\
 -v /mnt/docker/gachain-nginx/web:/usr/share/nginx/html:rw\
 -v /mnt/docker/gachain-nginx/logs:/var/log/nginx/:rw\
 --restart=always react-nginx:8.16
```



