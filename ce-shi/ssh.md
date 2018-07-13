# ssh

```
# apt-get update
# apt-get install ssh
# systemctl enable ssh
```

## 允许 SSH Root 访问

```
# vi /etc/ssh/sshd_config

PermitRootLogin yes

# service ssh restart
```



