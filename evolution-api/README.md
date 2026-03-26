# Evolution API - WhatsApp Automation

Evolution API is a robust WhatsApp messaging solution for automation with TypeScript support, webhooks, and more.

## Quick Start

```bash
cd evolution-api
# Create .env file
cp .env.example .env
# Generate a secure API key and edit .env
docker compose up -d
```

## Access

- **API**: http://localhost:8080
- **API Documentation**: http://localhost:8080/docs

## Features

- WhatsApp Business API integration
- Webhook support for events
- Multi-instance support
- Send messages, media, buttons
- Manage contacts and groups

## Configuration

Copy `.env.example` to `.env` and set:
- `EVOLUTION_API_KEY` — Secure key for API authentication
- `SERVER_URL` — Your server public URL (for webhooks)

## Using with External Databases

By default uses SQLite. For production, use PostgreSQL and Redis:

```yaml
# Uncomment in docker-compose.yml
database:
  image: postgres:15
  ...

cache:
  image: redis:alpine
  ...
```

## API Usage

```bash
# Create instance
curl -X POST http://localhost:8080/instance/create \
  -H "apikey: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"instanceName": "my-instance", "qrcode": true}'

# Send message
curl -X POST http://localhost:8080/message/sendText/my-instance \
  -H "apikey: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"number": "1234567890", "text": "Hello from Evolution!"}'
```

## Documentation

- [Evolution API Docs](https://docs.evolution-api.com/)
- [GitHub](https://github.com/EvolutionAPI/evolution-api)
