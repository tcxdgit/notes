###### 查看有哪些topic

`/opt/kafka/bin/kafka-topics.sh --zookeeper itoa-zookeeper-service1:2181 --list`

查看topic里的消息

`kafka-console-consumer.sh --bootstrap-server 192.168.88.128:30091,192.168.88.129:30092,192.168.88.130:30093 --topic snmp-data` 

或者

`kafka-console-consumer.sh --bootstrap-server itoa-kafka-service1:6667,itoa-kafka-service2:6667,itoa-kafka-service3:6667 --topic snmp-data` 

