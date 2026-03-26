# PostgreSQL + pgAdmin

PostgreSQL database with pgAdmin web UI for management.

## Quick Start

```bash
cd postgres
docker compose up -d
```

## Services

| Service | Port | Description |
|---------|------|-------------|
| PostgreSQL | 5432 | Database |
| pgAdmin | 5050 | Web UI |

## Access

- **PostgreSQL**: `postgresql://admin:password@localhost:5432/mydb`
- **pgAdmin**: http://localhost:5050
  - Email: `admin@example.com`
  - Password: `password`

## Connect from Application

```javascript
// Node.js + pg
const { Client } = require('pg');
const client = new Client({
  host: 'localhost',
  port: 5432,
  user: 'admin',
  password: 'password',
  database: 'mydb'
});
```

```python
# Python + psycopg2
import psycopg2
conn = psycopg2.connect("dbname=mydb user=admin password=password host=localhost")
```

## Documentation

- [PostgreSQL Docs](https://www.postgresql.org/docs/)
- [pgAdmin Docs](https://www.pgadmin.org/docs/)
