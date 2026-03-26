# n8n - Workflow Automation

A powerful workflow automation tool that can connect to various services via APIs.

## Quick Start

```bash
cd n8n
# Create .env file (optional)
cp .env.example .env
# Start
docker compose up -d
```

Then open http://localhost:5678

## Environment Variables

Copy `.env.example` to `.env` and customize:

| Variable | Description | Default |
|----------|-------------|---------|
| `N8N_USER` | Basic auth username | admin |
| `N8N_PASSWORD` | Basic auth password | password |
| `N8N_HOST` | Hostname | localhost |
| `WEBHOOK_URL` | Webhook base URL | http://localhost:5678/ |
| `GENERIC_TIMEZONE` | Timezone | UTC |

## Data Persistence

All workflows and credentials are stored in `./data/` — back this up!

## First Run

1. Open http://localhost:5678
2. Login with your credentials (default: admin/password)
3. Create your first workflow!

## Documentation

- [n8n Docs](https://docs.n8n.io/)
- [Workflow examples](https://docs.n8n.io/workflows/)
