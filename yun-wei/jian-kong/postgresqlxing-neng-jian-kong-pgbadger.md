### postgresql性能监控pgbadger

* 安装

```
git clone https://github.com/darold/pgbadger.git
```



### POSTGRESQL配置 {#POSTGRESQL-CONFIGURATION}

您必须在启动之前在postgresql.conf中启用并设置一些配置指令。

您必须首先启用SQL查询日志记录才能解析：

```
        log_min_duration_statement = 0
```

这里将记录每个语句，在繁忙的服务器上，您可能希望将此值增加到仅记录持续时间较长的查询。请注意，如果将log\_statement设置为“all”，则不会通过log\_min\_duration\_statement指令记录任何内容。有关更多信息，请参阅下一章。

pgBadger支持在postgresql.conf文件的log\_line\_prefix指令中设置的任何自定义格式，只要它至少指定一个时间转义序列（％t，％m或％n）和与进程相关的转义序列（％p或％c） 。

例如，对于'stderr'日志格式，log\_line\_prefix必须至少为：

```
        log_line_prefix = '%t [%p]: '
```

日志行前缀可以添加用户，数据库名称，应用程序名称和客户端IP地址，如下所示：

```
        log_line_prefix = '%t [%p]: user=%u,db=%d,app=%a,client=%h '
```

或者对于syslog日志文件格式：

```
        log_line_prefix = 'user=%u,db=%d,app=%a,client=%h '
```

stderr输出的日志行前缀也可以是：

```
        log_line_prefix = '%t [%p]: [%l-1] db=%d,user=%u,app=%a,client=%h '
```

或者对于syslog输出：

```
        log_line_prefix = 'db=%d,user=%u,app=%a,client=%h '
```

注意：上面示例中的会话行\[％l-1\]仅用于具有与syslog相同的stderr格式，但它不是必需的。这意味着它没有在pgBadger统计/图表中使用。当log\_destination为stderr时，您可以安全地从log\_line\_prefix中删除它们。

您需要在postgresql.conf中启用其他参数以从日志文件中获取更多信息：

```
        log_checkpoints = on

        log_connections = on

        log_disconnections = on

        log_lock_waits = on

        log_temp_files = 0

        log_autovacuum_min_duration = 0

        log_error_verbosity = default
```

不要启用log\_statement，因为pgBadger不会解析其日志格式。

当然，您的日志消息应该是英语，而不支持语言环境：

```
        lc_messages='C'
```

但这不仅是pgBadger推荐的。

### log\_min\_duration\_statement vs log\_duration + log\_statement {#log_min_duration_statement-log_duration-and-log_statement}

如果希望查询统计信息包含实际查询字符串，则必须将log\_min\_duration\_statement设置为0或更多毫秒。

如果您只想报告持续时间和查询数量，并且不想要查询的所有详细信息，请将log\_min\_duration\_statement设置为-1以禁用它并在postgresql.conf文件中启用log\_duration。如果要添加最常见的请求报告，可以选择将log\_min\_duration\_statement设置为更高的值，也可以选择启用log\_statement。

启用log\_min\_duration\_statement将添加有关占用时间最长的最慢查询和查询的报告。请注意，如果将log\_statement设置为“all”，则不会使用log\_line\_prefix记录任何内容。

* 重启postgres 服务



