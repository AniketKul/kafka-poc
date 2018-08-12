# kafka-poc
A Kafka Cluster with 2 Brokers/Servers/Nodes.

#Run Zookeeper
(Kafka depends on zookeeper for maintaining state, knowing which brokers exist, who is the controller, who is the leader, which topics are there etc.)

```
1] cd kafka_2.12-1.1.1
2] bin/zookeeper-server-start.sh config/zookeeper.properties
```

#Start Kafka Servers/Brokers:

##Run Broker 1

```
1] cd kafka_2.12-1.1.1
2] vim config/server2.properties and make sure that broker.id=0 and port=9092
3] bin/kafka-server-start.sh config/server.properties
```

##Run Broker 2

```
1] cd kafka_2.12-1.1.1
2] cp config/server.properties config/server2.properties
3] vim config/server2.properties and set broker.id=1 and port=9091
4] bin/kafka-server-start.sh config/server2.properties
```

#Check if brokers are running or not:

In terminal, do ```ps ef | grep kafka```
and check if you see config/zookeeper.properties, config/server.properties and config/server2.properties in the terminal.

#Creating a topic:
