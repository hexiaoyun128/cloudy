### postgresql性能监控pgbadger

* 安装

```
git clone https://github.com/darold/pgbadger.git
```

#### postgres设置

* `postgresql.conf`中的修改

logging\_collector = off改为logging\_collector = on

log\_min\_duration\_statement = -1改为log\_min\_duration\_statement = 0

* 重启postgres 服务



