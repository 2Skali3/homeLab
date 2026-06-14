# Network Inventory

## Date
2026-06-14 Sunday

## Purpose

This document describes the public-facing network architecture of the homelab.

Sensitive operational details are maintained separately.

---

# Internet Connectivity

## Domain

Managed through Cloudflare.

## Public Services

| Service | Exposure Method |
|----------|----------|
| Minecraft Server | Port Forwarding |
| Copyparty | Cloudflare Tunnel |

---

# Network Edge

## Cloudflare

Responsibilities:

- DNS Management
- Tunnel Connectivity
- External Access Layer

---

## Home Router

Responsibilities:

- Internet Gateway
- Internal Network Connectivity
- Firewall Management

---

# Production Environment

Production services operate on a dedicated Ubuntu Server.

---

# Administrative Access

Administrative services are intended to remain private whenever practical.

Examples:

- SSH
- Monitoring
- Dashboards

---

# Future Services

- VPN
- Reverse Proxy
- Monitoring Stack
- Containerized Services

---

# Review History

| Date | Notes |
|--------|--------|
| 2026-06 | Initial public inventory created |