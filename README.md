# 监控面板

所有配置文件都在对应服务的`config`目录，所有的持久化数据都在对应服务的`data`目录中  
grafana与所有数据源均可互通

## grafana

| HOSTNAME | PORT | USER  | PASSWORD |
| ------   | ---- | ----- | -------- |
| grafana  | 3000 | admin | admin    |

如提示权限问题请执行如下命令

```bash
cd grafana/
./set_privilege.sh
```

------------

## 数据源

### influxdb1

| HOSTNAME  | DB_NAME | PORT | USER | PASSWORD |
| ------    | ------- | ---- | ---- | -------- |
| influxdb1 | monitor | 8086 | root | root     |

配置文件`datasource/influxdb1/config/influxdb.conf`  

### influxdb2

| HOSTNAME  | ORG_NAME | BUCKET_NAME | PORT | USER  | PASSWORD  |
| ------    | -------- | ----------- | ---- | ----- | --------- |
| influxdb2 | monitor  | monitor     | 8086 | admin | 12345678  |

配置文件`datasource/influxdb2/config/config.yml`

### mongodb

| HOSTNAME | DB_NAME | PORT  | USER  | PASSWORD |
| -------- | ------- | ----- | ----- | -------- |
| mongodb  | mongo   | 27017 | mongo | mongo    |

### mysql

| HOSTNAME | DB_NAME | PORT | USER | PASSWORD |
| -------- | ------- | ---- | ---- | -------- |
| mysql    | monitor | 3306 | root | root     |

### postgresql

| HOSTNAME   | DB_NAME | PORT | USER     | PASSWORD |
| ---------- | ------- | ---- | -------- | -------- |
| postgresql | monitor | 5432 | postgres | root     |

### prometheus

prometheus 分为三个组件，其相关配置如下表

| 服务名称      | 服务端口 | 访问URL               |
| ------------ | ------- | ------------------------ |
| prometheus   | 9090    | http://prometheus:9090   |
| alertmanager | 9093    | http://alertmanager:9093 |
| pushgateway  | 9091    | http://pushgateway:9091  |

如提示权限问题请执行如下命令

```bash
cd datasource/prometheus/
./set_privilege.sh
```

### redis

| HOSTNAME | PORT |
| -------- | ---- |
| redis    | 6379 |

配置文件`datasource/redis/config/redis.conf`
