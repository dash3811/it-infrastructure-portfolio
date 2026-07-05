# Backup and Recovery

## Overview

Backup and recovery procedures are used to protect configuration files, application data, and infrastructure services.

## Goals

- Preserve critical configuration data
- Recover quickly from failed updates or service misconfiguration
- Maintain copies of Docker compose files and application folders
- Protect Home Assistant configuration and automations
- Reduce downtime after hardware, container, or storage issues

## Backup Targets

| Data | Backup Method | Notes |
|---|---|---|
| Docker Compose files | File backup / versioning | Do not publish secrets |
| Container config folders | NAS backup | Include only sanitized examples |
| Home Assistant config | Config backup | Redact tokens and device IDs |
| Proxmox VMs | Snapshots / backups | Document general approach |
| Synology data | NAS backup strategy | Do not publish personal paths |

## Recovery Checklist

1. Identify failed service or system
2. Review logs and recent changes
3. Stop affected services if needed
4. Restore known-good configuration
5. Validate service health
6. Document root cause and prevention
