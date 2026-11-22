# TaskFlow Monitoring

## Components

- Prometheus: Metrics collection
- Grafana: Metrics visualization
- Node Exporter: Linux host monitoring
- cAdvisor: Docker container monitoring

## Configuration

- docker-compose.yml: Monitoring services
- prometheus/prometheus.yml: Prometheus scrape configuration
- .env.example: Example environment variables

## Deployment

Copy the example environment file:

    cp .env.example .env

Set a strong Grafana password in `.env`.

Start monitoring:

    docker compose up -d

Check containers:

    docker compose ps

## Access

- Prometheus: http://127.0.0.1:9090
- Grafana: http://127.0.0.1:3000

Both services are bound to localhost on the server.

Use an SSH tunnel for remote access.

## Data Persistence

Grafana and Prometheus data are stored in Docker named volumes.

Do not remove these volumes when updating monitoring services.

## Security

Never commit `.env` or credentials to GitHub.
