# Gitlab Docker部署

```
docker run -dit  \ 
  -p 9044:443 -p 9003:80 -p 9023:22 --hostname 119.29.180.24\ 
  -v $(pwd)/docker_gitlab/config:/etc/gitlab \ 
  -v $(pwd)/docker_gitlab/logs:/var/log/gitlab \ 
  -v $(pwd)/docker_gitlab/data:/var/opt/gitlab \ 
  --name gitlab --restart always gitlab/gitlab-ce:10.5.5-ce.0
```

## 浏览器打开

[http://119.29.180.24:9003](http://119.29.180.24:9003)

