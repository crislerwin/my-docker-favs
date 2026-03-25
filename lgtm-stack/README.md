# LGTM Stack (Standalone Docker)

A standalone LGTM (Loki, Grafana, Tempo, Mimir) observability stack that runs anywhere with Docker.

## Quick Start

```bash
docker compose up -d
```

Then open http://localhost:3000
- Username: `admin`
- Password: `admin`

## Services

| Service | Port | Description |
|---------|------|-------------|
| Grafana | 3000 | Dashboards and visualization |
| Loki | 3100 | Log aggregation API |
| Tempo | - | Distributed tracing |
| Mimir | - | Metrics storage |
| Alloy | - | Docker log scraper |

## Send Logs

Push logs directly to Loki:
```bash
curl -X POST http://localhost:3100/loki/api/v1/push \
  -H "Content-Type: application/json" \
  -d '{"streams":[{"stream":{"app":"myapp"},"values":[["'$(date +%s%N)'","test log"]]}]}'
```

## Query Logs

In Grafana Explore, use LogQL:
- All logs: `{source="host-docker"}`
- By container: `{container="my-container"}`

## Data

Stored in `./data/` — delete to reset.

## Komodo DinD

Uncomment the `alloy-komodo` service in `docker-compose.yml` if using Komodo.

## Stop

```bash
docker compose down
```
