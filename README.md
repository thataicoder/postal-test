# Postal Docker Setup

This repository contains a basic configuration for running [Postal](https://github.com/postalserver/postal) using Docker Compose.

## Requirements
- Docker
- Docker Compose

## Configuration
1. Copy the example configuration files if needed.
2. Adjust the values in `.env` to suit your environment. The following variables are used:
   - `POSTAL_DB_HOST`, `POSTAL_DB_PORT`, `POSTAL_DB_USER`, `POSTAL_DB_PASS`, `POSTAL_DB_NAME`
   - `POSTAL_MESSAGE_DB_HOST`, `POSTAL_MESSAGE_DB_PORT`, `POSTAL_MESSAGE_DB_USER`, `POSTAL_MESSAGE_DB_PASS`, `POSTAL_MESSAGE_DB_PREFIX`
   - `POSTAL_RABBITMQ_HOST`, `POSTAL_RABBITMQ_PORT`, `POSTAL_RABBITMQ_USER`, `POSTAL_RABBITMQ_PASS`, `POSTAL_RABBITMQ_VHOST`
   - `POSTAL_SECRET_KEY`
3. The `config/postal.yml` file reads these variables using ERB syntax.

## Running
Start the containers with:

```bash
docker-compose up -d
```

The web interface will be available on port `5000` and SMTP will listen on port `25`.

## Notes
Certain files such as `config/postal.yml` and `config/signing.key` are ignored by Git to avoid committing sensitive information.
