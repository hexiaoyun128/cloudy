# Jenkins war包部署

## 下载地址

[http://ftp-nyc.osuosl.org/pub/jenkins/war-stable/2.121.1/jenkins.war](http://ftp-nyc.osuosl.org/pub/jenkins/war-stable/2.121.1/jenkins.war)

## 设置环境变量

```
# vi ~/.bash_profile

export JENKINS_HOME=/mnt/jenkins/workspace

# source ~/.bash_profile
```

jenkins的工作空间将会是`/mnt/jenkins/workspace`

## 后台运行

```
# java -jar /mnt/jenkins/jenkins.war --httpPort=9003 --daemon=true
# ps -ef|grep jenkins

root      3883     1 99 12:32 ?        00:00:15 java -Dcom.sun.akuma.Daemon=daemonized -jar /mnt/jenkins/jenkins.war --httpPort=9003 --daemon=true
```

## 查看root密码

```
# cat /mnt/jenkins/workspace/secrets/initialAdminPassword
```

## 浏览器登录

[http://ip:9003](http://ip:9003)

![](/chi-xu-ji-cheng/jenkins/images/jenkins-first.jpg)

管理员设置![](/chi-xu-ji-cheng/jenkins/images/jenkins-admin-user.jpg)URL设置

![](/chi-xu-ji-cheng/jenkins/images/jenkins-url-setting.jpg)

