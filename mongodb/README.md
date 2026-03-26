# MongoDB + Mongo Express

MongoDB database with Mongo Express web UI for management.

## Quick Start

```bash
cd mongodb
# Optional: create .env file
cp .env.example .env
docker compose up -d
```

## Services

| Service | Port | Description |
|---------|------|-------------|
| MongoDB | 27017 | Database |
| Mongo Express | 8081 | Web UI |

## Access

- **MongoDB**: `mongodb://admin:password@localhost:27017`
- **Mongo Express UI**: http://localhost:8081
  - Default login: `admin` / `password`

## Configuration

Copy `.env.example` to `.env` and customize credentials.

## Data Persistence

All data stored in `./data/` — back this up!

## Connect from Application

```javascript
// Node.js
const mongoose = require('mongoose');
mongoose.connect('mongodb://admin:password@localhost:27017/mydb');
```

```python
# Python
from pymongo import MongoClient
client = MongoClient('mongodb://admin:password@localhost:27017/')
db = client['mydb']
```

## Create Database & User

```bash
# Enter MongoDB shell
docker exec -it mongodb mongosh -u admin -p password --authenticationDatabase admin

# Inside mongosh:
use mydb
db.createUser({user: "myuser", pwd: "mypassword", roles: [{role: "readWrite", db: "mydb"}]})
```

## Documentation

- [MongoDB Docs](https://docs.mongodb.com/)
- [Mongo Express](https://github.com/mongo-express/mongo-express)
