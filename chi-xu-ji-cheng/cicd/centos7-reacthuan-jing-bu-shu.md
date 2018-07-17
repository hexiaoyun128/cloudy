# Centos7 React环境部署

以下为root用户操作

```
# wget https://nodejs.org/dist/v8.11.3/node-v8.11.3-linux-x64.tar.xz
# tar xf node-v8.11.3-linux-x64.tar.xz -C /usr/local
# mv /usr/local/node-v8.11.3-linux-x64 /usr/local/nodejs-v8

```

### 验证nodejs的bin包是否在可以正常运行

```
# cd /usr/local/nodejs-v8/bin
# ./node -v
```

### 将nodejs的路劲加入path

```
# vi /etc/profile
PATH=$PATH:/usr/local/nodejs-v8/bin
```

### 使配置生效

```
# source /etc/profile
```

### 验证

```
# node -v
# npm -v
```



