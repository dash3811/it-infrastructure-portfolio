# Docker Stack

## Overview

Docker is used to host containerized services for automation, monitoring, media management, DNS filtering, reverse proxying, and infrastructure tools.

## Goals

- Keep services isolated and portable
- Use Docker Compose for repeatable deployments
- Store persistent data in mapped volumes
- Use reverse proxies for controlled web access
- Maintain backups of configuration and application data

## Example Service Categories

| Category | Example Services |
|---|---|
| Reverse Proxy | Nginx Proxy Manager |
| DNS / Filtering | Pi-hole, Unbound |
| Monitoring | Grafana, VictoriaMetrics |
| Automation | Home Assistant |
| Cameras / NVR | Frigate |
| Media Management | Sonarr, Radarr, Prowlarr, Bazarr, Readarr, Lidarr |
| Recipe Management | Mealie |

## Sanitized Docker Compose Example

See:

```text
examples/sanitized-docker-compose.yml
```

## Container Management Practices

- Use Docker Compose for service definitions
- Keep credentials in `.env` files that are not published
- Map persistent data to dedicated folders
- Document exposed ports and dependencies
- Restart services only after reviewing logs
- Keep backups of critical application data
- Avoid publishing real container names, domains, passwords, API keys, or tokens

## Troubleshooting Workflow

1. Check container status:
   ```bash
   docker ps
   ```

2. Review logs:
   ```bash
   docker logs container-name
   ```

3. Validate network connectivity:
   ```bash
   docker network ls
   docker inspect network-name
   ```

4. Confirm port availability:
   ```bash
   ss -tulpn
   ```

5. Restart only the affected service:
   ```bash
   docker compose restart service-name
   ```
