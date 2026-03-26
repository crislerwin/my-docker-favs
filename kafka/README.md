# Kafka + Kafka UI

Apache Kafka with a web-based UI for managing topics, messages, and clusters.

## Quick Start

```bash
cd kafka
docker compose up -d
```

## Services

| Service | Port | Description |
|---------|------|-------------|
| Zookeeper | 2181 | Kafka coordination |
| Kafka | 9092 | Message broker |
| Kafka UI | 8080 | Web management UI |

## Access

- **Kafka UI**: http://localhost:8080
- **Kafka Bootstrap**: localhost:9092

## Create a Topic

```bash
# Using Kafka CLI
docker exec -it kafka kafka-topics.sh --create --topic my-topic --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1

# List topics
docker exec -it kafka kafka-topics.sh --list --bootstrap-server localhost:9092
```

## Produce/Consume Messages

```bash
# Produce
docker exec -it kafka kafka-console-producer.sh --topic my-topic --bootstrap-server localhost:9092

# Consume
docker exec -it kafka kafka-console-consumer.sh --topic my-topic --from-beginning --bootstrap-server localhost:9092
```

## Configuration

Edit `.env` to customize:
- `KAFKA_ADVERTISED_LISTENERS` — Change if accessing from another machine
- `KAFKA_AUTO_CREATE_TOPICS` — Enable/disable auto topic creation

## Data Persistence

Data stored in `./data/`:
- `./data/zookeeper/` — Zookeeper data
- `./data/kafka/` — Kafka logs and data

## Documentation

- [Kafka Docs](https://kafka.apache.org/documentation/)
- [Kafka UI Docs](https://docs.kafka-ui.provectus.io/)
