# 

# spinnaker安装部署

## Halyard安装

#### Debian/Ubuntu and macOS

* 获得最新版本的Halyard

```
curl -O https://raw.githubusercontent.com/spinnaker/halyard/master/install/debian/InstallHalyard.sh
```

```
curl -O https://raw.githubusercontent.com/spinnaker/halyard/master/install/macos/InstallHalyard.sh
```

* 安装

```
sudo bash InstallHalyard.sh
```

* 检查是否安装成功

```
hal -v
```

若运行失败，将`hal`添加到环境变量中,查看日志`/var/log/spinnaker/halyard/halyard.log`

* 命令帮助

```
hal -h
```

* Halyard升级

```
sudo update-halyard
```

* 卸载Halyard

```
hal deploy clean
sudo ~/.hal/uninstall.sh
```



#### Docker部署



