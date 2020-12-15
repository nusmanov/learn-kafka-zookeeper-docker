# deploy Apache Kafka using Docker Compose

## build and run
```
docker-compose up -d
```

### copy the container name
```
docker ps
```

```
docker exec -it kafka-zookeeper-docker_kafka_1 bash
```


## create a new topic named test-topic
kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic test-topic



### producer - terminal window 1
kafka-producer.sh --broker-list localhost:9092 --topic test-topic

### consumer - terminal window 2
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test-topic

### Simulation
Write in the producer terminal window _How are you?_ and ENTER.
Consumer should now receeive the message.