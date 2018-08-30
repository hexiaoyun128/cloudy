## Centos7安装mysql

* 安装

```
 wget -i -c http://dev.mysql.com/get/mysql57-community-release-el7-10.noarch.rpm
 yum -y install mysql57-community-release-el7-10.noarch.rpm
 yum -y install mysql-community-server
```

* 启动

```
 systemctl start  mysqld.service
```

* 状态查看

```
systemctl status mysqld.service
```



