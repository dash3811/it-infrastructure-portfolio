# Infrastructure Overview

## Summary

This environment is a self-hosted infrastructure lab designed to simulate practical systems administration responsibilities. It uses virtualization, containerization, network segmentation, storage management, reverse proxies, DNS, monitoring, and automation.

## Goals

- Build hands-on experience with real infrastructure technologies
- Practice troubleshooting Linux, Docker, networking, and service availability issues
- Maintain secure remote access to self-hosted applications
- Document infrastructure in a professional, repeatable way
- Demonstrate practical systems administration experience to employers

## Core Components

| Area | Technologies |
|---|---|
| Virtualization | Proxmox VE |
| Storage | Synology NAS |
| Operating Systems | Ubuntu, Debian |
| Containers | Docker, Docker Compose |
| Networking | UniFi, VLANs, DNS, DHCP, VPN, firewall rules |
| Remote Access | Cloudflare, Nginx Proxy Manager, SSL certificates |
| Automation | Home Assistant, YAML |
| Monitoring | Grafana, VictoriaMetrics |
| DNS Filtering | Pi-hole, Unbound |

## Environment Scale

- 20+ Docker containers
- 2 virtual machines
- 3 VLANs
- 44 connected smart devices

## Responsibilities Demonstrated

- Deploying and maintaining Linux-based services
- Managing Docker containers and compose stacks
- Configuring reverse proxies and SSL certificates
- Segmenting networks using VLANs
- Managing DNS, DHCP, VPN, and firewall rules
- Maintaining Synology-based storage
- Creating Home Assistant automations
- Monitoring service health and performance
- Troubleshooting infrastructure issues using root-cause analysis

## Sanitized Architecture

A sanitized diagram should be placed in:

```text
diagrams/network-diagram-sanitized.png
```

Do not include real IP addresses, public domains, device names, serial numbers, or camera views.
