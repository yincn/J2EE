# 官方介绍
https://github.com/alibaba/canal

# 配置参数说明
canal.properties (version: 1.1.6)
| Param                                                    | Default                                                      | Remark                                                       |
| -------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| canal.ip                                                 |                                                              | canal server bind local ip                                   |
| canal.port                                               | 11111                                                        | canal server socket port                                     |
| canal.register.ip                                        |                                                              | register ip to zookeeper                                     |
| canal.metrics.pull.port                                  | 11112                                                        | canal metrics port                                           |
| canal.user                                               | canal                                                        | Canal user                                                   |
| canal.passwd                                             | E3619321C1A937C46A0D8BD1DAC39F93B27D4458d                    | canal password                                               |
| canal admi config                                        |                                                              |                                                              |
| canal.admin.port                                         | 11110                                                        | canal admin port                                             |
| canal.admin.user                                         | admin                                                        | canal admin user                                             |
| admin auto register                                      |                                                              |                                                              |
| canal.admin.register.auto                                | true                                                         |                                                              |
| canal.admin.register.cluster                             |                                                              |                                                              |
| canal.admin.register.name                                |                                                              |                                                              |
| canal.zkServers                                          |                                                              |                                                              |
| canal.zookeeper.flush.period                             | 1000                                                         | flush data to zk                                             |
| canal.withoutNetty                                       | false                                                        |                                                              |
| canal.serverMode                                         | tcp                                                          | # tcp, kafka, rocketMQ, rabbitMQ, pulsarMQ                   |
| canal.file.data.dir                                      | ${canal.conf.dir}                                            | flush meta cursor/parse position to file                     |
| canal.file.flush.period                                  | 1000                                                         |                                                              |
| canal.instance.memory.buffer.size                        | 16384                                                        |                                                              |
| canal.instance.memory.buffer.memunit                     | 1024                                                         | memory store RingBuffer used memory unit size , default 1kb  |
| canal.instance.memory.batch.mode                         | MEMSIZE                                                      | meory store gets mode used MEMSIZE or ITEMSIZE               |
| canal.instance.memory.rawEntry                           | true                                                         |                                                              |
| detecing config                                          |                                                              |                                                              |
| canal.instance.detecting.enable                          | false                                                        |                                                              |
| canal.instance.detecting.sql                             | insert into retl.xdual values(1,now()) on duplicate key update x=now() |                                                              |
| canal.instance.detecting.sql                             | select 1                                                     |                                                              |
| canal.instance.detecting.interval.time                   | 3                                                            |                                                              |
| canal.instance.detecting.retry.threshold                 | 3                                                            |                                                              |
| canal.instance.detecting.heartbeatHaEnable               | false                                                        |                                                              |
| canal.instance.transaction.size                          | 1024                                                         | support maximum transaction size, more than the size of the transaction will be cut into multiple transactions delivery |
| canal.instance.fallbackIntervalInSeconds                 | 60                                                           | mysql fallback connected to new master should fallback times |
| network config                                           |                                                              |                                                              |
| canal.instance.network.receiveBufferSize                 | 16384                                                        |                                                              |
| canal.instance.network.sendBufferSize                    | 16384                                                        |                                                              |
| canal.instance.network.soTimeout                         | 30                                                           |                                                              |
| binlog filter config                                     |                                                              |                                                              |
| canal.instance.filter.druid.ddl                          | flase                                                        |                                                              |
| canal.instance.filter.query.dcl                          | false                                                        | 是否忽略DCL的query语句，比如grant/create user等              |
| canal.instance.filter.query.dml                          | true                                                         | 是否忽略DML的query语句，比如insert/update/delete table.(mysql5.6的ROW模式可以包含statement模式的query记录) |
| canal.instance.filter.dml.insert                         | false                                                        |                                                              |
| canal.instance.filter.dml.update                         | false                                                        |                                                              |
| canal.instance.filter.dml.delete                         | false                                                        |                                                              |
| canal.instance.filter.query.ddl                          | false                                                        | 是否忽略DDL的query语句，比如create table/alater table/drop table/rename table/create index/drop index. (目前支持的ddl类型主要为table级别的操作，create databases/trigger/procedure暂时划分为dcl类型) |
| canal.instance.filter.table.error = false                | false                                                        |                                                              |
| canal.instance.filter.rows                               | false                                                        |                                                              |
| canal.instance.filter.transaction.entry                  | false                                                        |                                                              |
| binlog format/image check                                |                                                              |                                                              |
| canal.instance.binlog.formatcanal.instance.binlog.format | ROW,STATEMENT,MIXED                                          |                                                              |
| canal.instance.binlog.image                              | FULL,MINIMAL,NOBLOB                                          |                                                              |
| binlog ddl isolation                                     |                                                              |                                                              |
| canal.instance.get.ddl.isolation                         | false                                                        | ddl语句是否隔离发送，开启隔离可保证每次只返回发送一条ddl数据，不和其他dml语句混合返回.(otter ddl同步使用) |
| parallel parser config                                   |                                                              |                                                              |
| canal.instance.parser.parallel                           | true                                                         |                                                              |
| canal.instance.parser.parallelThreadSize                 | 16                                                           |                                                              |
| canal.instance.parser.parallelBufferSize                 | 256                                                          |                                                              |
| destinations                                             |                                                              |                                                              |
| canal.destinations                                       | example                                                      |                                                              |
| canal.conf.dir                                           | ../conf                                                      |                                                              |
| canal.auto.scan                                          | true                                                         |                                                              |
| canal.auto.scan.interval                                 | 5                                                            |                                                              |
| canal.auto.reset.latest.pos.mode                         | false                                                        |                                                              |
| canal.instance.tsdb.spring.xml                           | classpath:spring/tsdb/mysql-tsdb.xml                         |                                                              |
| canal.instance.global.mode                               | spring                                                       |                                                              |
| canal.instance.global.lazy                               | false                                                        |                                                              |
| canal.instance.global.manager.address                    | ${canal.admin.manager}                                       |                                                              |
| canal.instance.global.spring.xml                         | classpath:spring/file-instance.xml                           |                                                              |
| canal.instance.global.spring.xml                         | classpath:spring/default-instance.xml                        |                                                              |
| RabbitMQ config                                          |                                                              |                                                              |
| rabbitmq.host                                            | 127.0.0.1                                                    |                                                              |
| rabbitmq.virtual.host                                    | /                                                            |                                                              |
| rabbitmq.exchange                                        | canal.exchange                                               |                                                              |
| rabbitmq.username                                        | admin                                                        |                                                              |
| rabbitmq.password                                        | 123456                                                       |                                                              |
| rabbitmq.deliveryMode                                    | 2                                                            |                                                              |                                                            |

# 常见问题
```
2022-10-06 18:08:18.155 [destination = example , address = localhost/127.0.0.1:3306 , EventParser] WARN AbstractEventParser.java:190 - ---> begin to find start position, it will be long time for reset or first position
2022-10-06 18:08:18.304 [destination = example , address = localhost/127.0.0.1:3306 , EventParser] ERROR AbstractEventParser.java:298 - dump address localhost/127.0.0.1:3306 has an error, retrying. caused by 
com.google.common.util.concurrent.UncheckedExecutionException: com.alibaba.fastjson2.JSONException: read field error : clientDatas
	at com.google.common.cache.LocalCache$Segment.get(LocalCache.java:2218) ~[guava-22.0.jar:na]
	at com.google.common.cache.LocalCache.get(LocalCache.java:4147) ~[guava-22.0.jar:na]
	at com.google.common.cache.LocalCache.getOrLoad(LocalCache.java:4151) ~[guava-22.0.jar:na]
	at com.google.common.cache.LocalCache$LocalLoadingCache.get(LocalCache.java:5140) ~[guava-22.0.jar:na]
	at com.google.common.collect.MigrateMap$MigrateConcurrentMap.get(MigrateMap.java:68) ~[classes/:na]
	at com.alibaba.otter.canal.meta.MemoryMetaManager.listAllSubscribeInfo(MemoryMetaManager.java:72) ~[classes/:na]
	at com.alibaba.otter.canal.parse.index.MetaLogPositionManager.getLatestIndexBy(MetaLogPositionManager.java:52) ~[classes/:na]
	at com.alibaba.otter.canal.parse.index.FailbackLogPositionManager.getLatestIndexBy(FailbackLogPositionManager.java:68) ~[classes/:na]
	at com.alibaba.otter.canal.parse.inbound.mysql.MysqlEventParser.findStartPositionInternal(MysqlEventParser.java:415) ~[classes/:na]
	at com.alibaba.otter.canal.parse.inbound.mysql.MysqlEventParser.findStartPosition(MysqlEventParser.java:357) ~[classes/:na]
	at com.alibaba.otter.canal.parse.inbound.AbstractEventParser$1.run(AbstractEventParser.java:191) ~[classes/:na]
	at java.lang.Thread.run(Thread.java:750) [na:1.8.0_321]
```
解决办法：删除 meta.dat 文件，重新启动 canal server
