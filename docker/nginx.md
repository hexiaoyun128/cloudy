# Nginx部署

```
 docker run -dit --name gachainv2-wallet  -p 8600:80 -p 8643:443 -v /mnt/docker/gachainv2-wallet/web:/usr/share/nginx/html:rw -v /mnt/docker/gachainv2-wallet/logs:/var/log/nginx/:rw --restart=always nginx:1.13
```



