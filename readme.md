# Kafka Basic Commands

## Start the Zookeper service
```bash
bin/zookeeper-server-start.sh config/zookeeper.properties
```

## Start kafka broker service
```bash
bin/kafka-server-start.sh config/server.properties
```

## Create a Topic
```bash
bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1
```

## Write on Topic
```bash
bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092
```

## Read from Topic
```bash
bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
```

# Run multiple kafka servers

## Create new config properties files
Example: create a config-2.properties file and edit the following properties
1. broker.id=2 Change the id (default should be 0)
2. listeners=PLAINTEXT://:9093 ==> Change the port number
3. log.dirs=/tmp/kafka-logs-2 ==> Change the folder name

## Run a new server
```bash
bin/kafka-server-start.sh config/server-2.properties
```