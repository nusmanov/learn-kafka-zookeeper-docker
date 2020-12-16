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


## create a new topic
Create a new topic _test-topic_
```
kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic test-topic
```

## simulation
Let us simulate the producer and consumer, where producer publishes a message, which is received by a consumer

#### producer - terminal window 1
kafka-producer.sh --broker-list localhost:9092 --topic test-topic

#### consumer - terminal window 2
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test-topic

#### create a message
Write in the producer terminal window _How are you?_ and ENTER.
Consumer should now receeive the message.