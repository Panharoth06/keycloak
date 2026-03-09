# Keycloak Docker Compose

This project runs Keycloak with PostgreSQL using Docker Compose.

Project path examples in this README use:

```bash
/path/to/your/project
```

The recommended entrypoint is `run.sh`, which:

- checks that `docker` and `docker compose` are available
- validates that `.env.example` and `docker-compose.yml` exist
- copies `.env.example` to `.env`
- runs `docker compose up -d`

## Prerequisites

- Docker
- Docker Compose (`docker compose`)

## Quick Start

1. Move to your project directory:

```bash
cd /path/to/your/project
```

2. Review and update `.env.example` if needed.
3. Start the stack:

```bash
bash run.sh
```

Each time you run `run.sh`, it copies `.env.example` to `.env` before starting the containers.

After startup, open:

- Keycloak: `http://localhost:8080`
- Admin username: `admin`
- Admin password: `admin`

## Configure Environment

Edit `.env.example` to change:

- `KEYCLOAK_VERSION`
- `KEYCLOAK_HTTP_PORT`
- `KEYCLOAK_ADMIN`
- `KEYCLOAK_ADMIN_PASSWORD`
- `POSTGRES_VERSION`
- `POSTGRES_DB`
- `POSTGRES_USER`
- `POSTGRES_PASSWORD`

For any non-local use, change the default admin and database passwords in `.env.example` before starting the stack.

## Start Command

Start containers in detached mode:

```bash
bash run.sh
```

To manage the stack after startup, use `docker compose` directly from `/path/to/your/project`.

## Files

- `run.sh`: wrapper for Docker Compose commands
- `docker-compose.yml`: Keycloak + PostgreSQL services
- `.env.example`: sample environment values
- `.env`: local environment values used by Compose
