# My Docker Favorites

A collection of my favorite Docker Compose stacks.

## Stacks

### alloy/
Standalone log collector that scrapes Docker containers and sends logs to any Loki instance.

```bash
cd alloy
# Configure Loki endpoint
echo "LOKI_ENDPOINT=http://your-loki:3100/loki/api/v1/push" > .env
docker compose up -d
```

### lgtm-stack/
Full Grafana observability stack — Loki, Grafana, Tempo, and Mimir.

```bash
cd lgtm-stack
docker compose up -d
# Open http://localhost:3000 (admin/admin)
```

## Combining Stacks

Run Alloy on the same machine as LGTM stack:

```bash
# Terminal 1
cd lgtm-stack && docker compose up -d

# Terminal 2  
cd alloy && LOKI_ENDPOINT=http://lgtm:3100/loki/api/v1/push docker compose up -d
```

Or on separate machines — just point Alloy to your Loki URL.
