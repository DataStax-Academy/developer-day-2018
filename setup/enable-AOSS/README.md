## Enable Always-On SQL

Certain Developer Day notebooks make use of the Always-On SQL service in DataStax Enterprise, which needs to be manually enabled in the **dse.yaml** configuration file. The location of the file may vary depending on how DSE was installed.

### Binary tarball

The **dse.yaml** can be found at `[installation_location]/resources/dse/conf/dse.yaml`

### Package install

The **dse.yaml** can be found at `/etc/dse/dse.yaml`.

### Making the change

Set enabled to true and uncomment the AlwaysOn SQL options in dse.yaml.

From: 
```
# AlwaysOn SQL options
# alwayson_sql_options:
#     enabled: false
#     thrift_port: 10000
#     web_ui_port: 9077
#     reserve_port_wait_time_ms: 100
#     alwayson_sql_status_check_wait_time_ms: 500
#     workpool: alwayson_sql
#     log_dsefs_dir: /spark/log/alwayson_sql
#     auth_user: alwayson_sql
#     runner_max_errors: 10
```

To: 
```
# AlwaysOn SQL options
alwayson_sql_options:
    enabled: true
#     thrift_port: 10000
#     web_ui_port: 9077
#     reserve_port_wait_time_ms: 100
#     alwayson_sql_status_check_wait_time_ms: 500
#     workpool: alwayson_sql
#     log_dsefs_dir: /spark/log/alwayson_sql
#     auth_user: alwayson_sql
#     runner_max_errors: 10
```

Afterwards, restart DataStax Enterprise to have the changes take effect.
