# Helicone Infrastructure Stack

Core infrastructure services for [Helicone](https://helicone.ai/) - Open-source LLM observability platform.

## What's Included

| Service | Port | Description |
|---------|------|-------------|
| PostgreSQL | 5432 | Application database |
| ClickHouse | 8123/9000 | Analytics database |
| Redis | 6379 | Cache & session store |
| MinIO | 9000/9001 | S3-compatible object storage |
| MailHog | 1025/8025 | Email testing (optional) |

## Quick Start

```bash
cd helicone

# Copy environment file
cp .env.example .env

# Start services
docker compose up -d

# Check status
docker compose ps
```

## Access

- **PostgreSQL**: `postgresql://postgres:helicone@localhost:5432/helicone`
- **ClickHouse HTTP**: http://localhost:8123
- **Redis**: `redis://:helicone@localhost:6379`
- **MinIO Console**: http://localhost:9001 (minioadmin/minioadmin)
- **MailHog Web**: http://localhost:8025

## Environment Variables

Copy `.env.example` to `.env` and customize:

| Variable | Description | Default |
|----------|-------------|---------|
| `POSTGRES_PASSWORD` | PostgreSQL password | helicone |
| `POSTGRES_PORT` | PostgreSQL port | 5432 |
| `CLICKHOUSE_PASSWORD` | ClickHouse password | helicone |
| `CLICKHOUSE_HTTP_PORT` | ClickHouse HTTP port | 8123 |
| `REDIS_PASSWORD` | Redis password | helicone |
| `REDIS_PORT` | Redis port | 6379 |
| `MINIO_ROOT_USER` | MinIO access key | minioadmin |
| `MINIO_ROOT_PASSWORD` | MinIO secret key | minioadmin |

## Data Persistence

All data stored in Docker volumes:
- `postgres_data` - PostgreSQL data
- `clickhouse_data` - ClickHouse analytics
- `redis_data` - Redis cache
- `minio_data` - MinIO objects

## Use with Helicone

This stack provides the infrastructure. To run the full Helicone app:

1. Clone the [Helicone repo](https://github.com/Helicone/helicone)
2. Point it to these services
3. Or use their [official Docker setup](https://github.com/Helicone/helicone/tree/main/docker)

## Stop

```bash
docker compose down
# Remove data too:
docker compose down -v
```

## Documentation

- [Helicone Docs](https://docs.helicone.ai/)
- [Helicone GitHub](https://github.com/Helicone/helicone)
