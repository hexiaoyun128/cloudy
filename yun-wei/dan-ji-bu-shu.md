# 单机部署

```
# mkdir /data
# tar xf bkce_src-4.0.15.tgz -C /data
# tar xf install_ce-master-1.1.44.tgz -C /data
```

## YUM 源

```
# yum install wget -y
# mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
# cd /etc/yum.repos.d/
# wget https://mirrors.163.com/.help/CentOS7-Base-163.repo
# yum clean all
# yum makecache
```

## Hosts修改

```
# vi /ets/hosts
192.168.1.8 hechihan.com
```

## 证书获得

证书获得地址：[http://bk.tencent.com/download/\#ssl](http://bk.tencent.com/download/#ssl),解压到 src/cert 目录下

```
# tar xf ssl_certificate.tar -C /data/src/cert/
```

# 配置参数

```
# vi  /data/install/globals.env  
export BK_DOMAIN="hechihan.com"            # 蓝鲸根域名(不含主机名)
```

其他参数根据实际情况修改

# 安装

```
# cd /data/install
# ./install_minibk
```

# 安装过程问题以及解决

* 问题1

```
./functions: line 180: rsync: command not found
```

解决

```
# yum install rsync -y
```



