# kafka-demo

This project creates 1 broker with a topic named Users.  
There are 2 partitions:

1. Names between A-M go in partition 1
2. Names between N-Z go in partition 2

## 1. Spin up zookeeper and kafka

`docker-compose -f docker-compose.yml up -d`

## 2. Create topic

This script creates a topic named "Users"  
`node topics.js`

## 3. Produce event

This script produces events to topic "Users"  
`node producer.js <message>`

## 4. Consume events

This script creates a consumer and continues running and subscribes to the Users topic.  
`node consumer.js`  
Can be ran again to create another consumer.  
Notice how the two consumers each read from one partition now.

# Inspecting Kafka

List topics  
`docker exec -it kafka /bin/kafka-topics --list --bootstrap-server localhost:9092`
