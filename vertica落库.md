1. 创建topic

D:\trunk\72\health\app\platform\itoa-components\docker\itoa-job-initkafka\resources\initkafka.sh

找个地方添加即可，手动添加方法如下

./kafka-topics.sh --replication-factor 1 --partitions 3 --zookeeper itoa-zookeeper-service1:2181 --create --topic xxx

2. 创建表

D:\trunk\72\health\package\itoa-3.0\metadata\customized-files\itoa_init\initVertica\SQL\DDL_influxdb.sql

手动的话用dbeaver

3． 关联二者

D:\trunk\72\health\app\platform\itoa-components\docker\itoa-kafka2vertica\resources\initVertica\kafka2vertica_scheduler\kafka2vertica_scheduler.sh

手动改的话重启itoa-kafka2vertica容器