# MinIO - S3 Compatible Storage

MinIO is a high-performance, S3 compatible object store.

## Quick Start

```bash
cd minio
docker compose up -d
```

## Services

| Service | Port | Description |
|---------|------|-------------|
| MinIO S3 | 9000 | S3 API endpoint |
| MinIO Console | 9001 | Web UI |

## Access

- **MinIO Console**: http://localhost:9001
  - Username: `minioadmin`
  - Password: `minioadmin`
- **S3 Endpoint**: http://localhost:9000

## Using MinIO

Create buckets, upload files via the web console or use any S3-compatible tool:

```bash
# Using AWS CLI
aws configure --profile minio
# Set access key: minioadmin
# Set secret key: minioadmin

# Create bucket
aws --endpoint-url http://localhost:9000 s3 mb s3://mybucket --profile minio

# Upload file
aws --endpoint-url http://localhost:9000 s3 cp myfile.txt s3://mybucket/ --profile minio
```

## Documentation

- [MinIO Docs](https://min.io/docs/)
- [S3 API](https://docs.aws.amazon.com/s3/)
