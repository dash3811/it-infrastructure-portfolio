# Network Architecture

## Overview

The network is designed to separate trusted devices, IoT devices, and infrastructure services using VLAN segmentation and firewall rules. DNS, DHCP, VPN, and remote access are managed to support reliable access while limiting unnecessary exposure.

## Network Goals

- Separate trusted clients from IoT and lab services
- Improve security through segmentation
- Support stable DHCP and DNS resolution
- Provide controlled remote access
- Reduce unnecessary broadcast traffic
- Make troubleshooting easier by organizing devices logically

## VLAN Layout

Use sanitized examples only.

| VLAN | Purpose | Example Subnet |
|---|---|---|
| VLAN 10 | Default | 10.0.10.0/24 |
| VLAN 20 | IoT / Smart devices | 10.0.20.0/24 |
| VLAN 30 | Guest Network | 10.0.99.0/24 |

## Services

| Service | Purpose |
|---|---|
| DHCP | Assigns client IP addresses |
| DNS | Resolves local and external hostnames |
| Pi-hole | DNS filtering |
| Unbound | Recursive DNS resolution |
| VPN | Remote access |
| Cloudflare | External DNS / access layer |
| Nginx Proxy Manager | Reverse proxy and SSL management |

## Firewall Strategy

General firewall strategy:

- Allow trusted devices to access required infrastructure services
- Restrict IoT devices from initiating connections to trusted devices
- Allow IoT devices only to required services such as DNS, NTP, and Home Assistant
- Limit externally exposed services
- Use VPN or reverse proxy where appropriate
- Avoid exposing admin interfaces directly to the internet

## Sanitized Firewall Rule Examples

```text
Allow Trusted VLAN -> Server VLAN for approved services
Allow IoT VLAN -> DNS server on port 53
Allow IoT VLAN -> Home Assistant on required port
Block IoT VLAN -> Trusted VLAN
Block Internet -> internal services unless proxied/VPN protected
```
