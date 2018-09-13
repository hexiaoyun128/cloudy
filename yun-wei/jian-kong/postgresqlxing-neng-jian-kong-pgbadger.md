### postgresql性能监控pgbadger

* 安装

```
git clone https://github.com/darold/pgbadger.git
```

#### postgres设置

* `postgresql.conf`中的修改

```
logging_collector = off 改为 logging_collector = on
log_min_duration_statement = -1 改为 log_min_duration_statement = 0
```

* 重启postgres 服务



