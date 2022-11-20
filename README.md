
# Start Kafka cluster
```
docker compose -f script/docker-compose.yml up -d
```

# Start Kafka cluster
```
mvn install
```

# Create topics
```
kafka-topics --bootstrap-server localhost:9092 --create --partitions 4 --replication-factor 1 --topic CustomerDetails-proto
kafka-topics --bootstrap-server localhost:9092 --create --partitions 4 --replication-factor 1 --topic EnabledCustomer-proto --config cleanup.policy=compact --config retention.ms=600000 --config segment.ms=600000
kafka-topics --bootstrap-server localhost:9092 --create --partitions 4 --replication-factor 1 --topic OrdersInput-proto
kafka-topics --bootstrap-server localhost:9092 --create --partitions 4 --replication-factor 1 --topic OrdersOutput-proto
```

# Run app
```
mvn spring-boot:run -f application/pom.xml
```

# Open browser
```
localhost:8080
```

# Stop kafka cluster
```
docker compose -f script/docker-compose.yml down
```
