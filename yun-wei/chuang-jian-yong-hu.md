* 创建用户

```
adduser gachaintest
passwd gachaintest
Jenkins123.
```

* 授权

```
[root@molis-beijing ~]# sudoers
-bash: sudoers: command not found
[root@molis-beijing ~]# whereis sudoers
sudoers: /etc/sudoers /etc/sudoers.d /usr/share/man/man5/sudoers.5.gz
[root@molis-beijing ~]# ls -l /etc/sudoers
-r--r----- 1 root root 3938 Jun 27 02:07 /etc/sudoers
[root@molis-beijing ~]# chmod -v u+w /etc/sudoers
mode of ‘/etc/sudoers’ changed from 0440 (r--r-----) to 0640 (rw-r-----)
```

* 增加sudoer用户

```
[root@molis-beijing ~]# vim /etc/sudoers
```

```
 91 ## Allow root to run any commands anywhere 
 92 root    ALL=(ALL)       ALL
 93 gachaintest ALL=(ALL) ALL
```

* 恢复文件原有的权限

```
[root@molis-beijing ~]# chmod -v u-w /etc/sudoers
mode of ‘/etc/sudoers’ changed from 0640 (rw-r-----) to 0440 (r--r-----)
```



