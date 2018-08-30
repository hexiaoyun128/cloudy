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

* 查看初始默认密码

```
grep "password" /var/log/mysqld.log
```

* 进入数据库

```
mysql -uroot -p
```

* 修改密码

```
 ALTER USER 'root'@'localhost' IDENTIFIED BY 'new password';
```

* 修改连接IP 

```
mysql> use mysql
mysql> select t.host from user t where t.user='root';
+--------------+
|  host        |
+--------------+
|  localhost   |
+--------------+
mysql> update user set host='%' where user='root';
```

* 重启

```

```



