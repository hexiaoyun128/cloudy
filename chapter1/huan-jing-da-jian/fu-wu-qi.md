Centos服务器环境搭建

```
wget https://dl.google.com/go/go1.10.3.linux-amd64.tar.gz
tar zxvf go1.10.3.linux-amd64.tar.gz -C /usr/local/
```

创建gopath目录，可以在任意目录下，下面操作为`/mnt`

```
mkdir -p /mnt/gopath
```

配置环境变量

```
vim /etc/profile
```

```
export GOROOT=/usr/local/go
export GOBIN=$GOROOT/bin
export PATH=$PATH:$GOBIN
export GOPATH=/mnt/gopath
```

```
source /etc/profile
```

安装结束，验证

```
go version
```



