# Redis + Redis Insight

Redis in-memory data store with Redis Insight web UI.

## Quick Start

```bash
cd redis
docker compose up -d
```

## Services

| Service | Port | Description |
|---------|------|-------------|
| Redis | 6379 | Cache/Database |
| Redis Insight | 5540 | Web UI |

## Access

- **Redis**: `redis://localhost:6379` (password: `password`)
- **Redis Insight**: http://localhost:5540

## Connect

```bash
# Using redis-cli
docker exec -it redis redis-cli -a password

# Key commands
> SET mykey "hello"
> GET mykey
> KEYS *
```

## Documentation

- [Redis Commands](https://redis.io/commands/)
- [Redis Insight](https://redis.io/docs/ui/insight/)
