# ClickHouse + ClickHouse UI

ClickHouse is a fast open-source OLAP database for real-time analytics.

## Quick Start

```bash
cd clickhouse
docker compose up -d
```

## Services

| Service | Port | Description |
|---------|------|-------------|
| ClickHouse | 8123/9002 | Database (HTTP/Native) |
| ClickHouse UI | 8082 | Web UI |

## Access

- **ClickHouse HTTP**: http://localhost:8123
- **ClickHouse Native**: localhost:9002
- **ClickHouse UI**: http://localhost:8082

## Connect

```bash
# Using clickhouse-client
docker exec -it clickhouse clickhouse-client -u default --password password

# SQL commands
CREATE DATABASE mydb;
CREATE TABLE mydb.events (id UInt32, name String) ENGINE = MergeTree() ORDER BY id;
INSERT INTO mydb.events VALUES (1, 'test');
SELECT * FROM mydb.events;
```

## Documentation

- [ClickHouse Docs](https://clickhouse.com/docs/)
- [SQL Reference](https://clickhouse.com/docs/en/sql-reference/)
