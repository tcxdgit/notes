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





三步即可

1.   创建一张表 `package/itoa-3.0/metadata/customized-files/itoa_init/initVertica/SQL/DDL_vertica.sql ` 这个文件里面加，位置随意，例如表名A

2. 新建一个topic 文件位置 `app/platform/itoa-components/docker/itoa-job-initkafka/resources/initkafka.sh`，例如B


3. `app/platform/itoa-components/docker/itoa-kafka2vertica/resources/initVertica/kafka2vertica_scheduler/kafka2vertica_scheduler.sh `在该文件搜索关键字 srctopics_tgtables_A 在括号里加一行，格式B,A，流任务写入topic的格式      字段1@字段2@字段3@。也可选择srctopics_tgtables_B，此时流任务写入topic的格式  字段1|字段2|字段3|

4. `app/base/components/itoa-components/docker/itoa-verticacron/resources/initVertica/vsh/delete_vertica_data.sh` vertica自动清除脚本