# Centos下docker部署

* Docker 要求 CentOS 系统的内核版本高于 3.10 ，查看本页面的前提条件来验证你的CentOS 版本是否支持 Docker

```
uname -r
```

* 使用`root`权限登录 Centos。确保 yum 包更新到最新。

```
sudo yum update
```

* 卸载旧版本\(如果安装过旧版本的话\)

```
sudo yum remove docker  docker-common docker-selinux docker-engine
```

* 安装需要的软件包， yum-util 提供yum-config-manager功能，另外两个是devicemapper驱动依赖的

```
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

* 设置yum源

```
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

* 可以查看所有仓库中所有docker版本，并选择特定版本安装

```
yum list docker-ce --showduplicates | sort -r
```

* 选择版本安装

```
sudo yum install docker-ce-17.03.2
```



