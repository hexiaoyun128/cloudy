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

## 配置参数

```
# vi  /data/install/globals.env  
export BK_DOMAIN="hechihan.com"            # 蓝鲸根域名(不含主机名)
```

其他参数根据实际情况修改

## 安装

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

* 问题2

```
[192.168.1.9]20180713-075745 1401   install nginx failed
```

解决

```
# rpm -ivh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
# yum clean all
```

* 问题3

```
port 31001 start failed, please check
```

解决

```
# ./bkcec install cmdb
$ ./bkcec stop cmdb
# ./bkcec start cmdb 
```



## 浏览器打开

[http://paas.hechihan.com](http://paas.hechihan.com)

[http://cmdb.hechihan.com](http://cmdb.hechihan.com)

[http://job.hechihan.com](http://job.hechihan.com)

