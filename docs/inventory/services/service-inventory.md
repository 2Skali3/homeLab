# Service Inventory

## Date

2026-06-14 Sunday

## Purpose

This document tracks all services currently deployed within the homelab environment.

Any newly deployed service should be added to this inventory.

---

## Active Services

| Service | Status | Location | Access Method | Purpose |
|----------|----------|----------|----------|----------|
| SSH | Active | Aspire 5738G | LAN / Administrative Access | Remote server administration |
| Minecraft Server | Active | Aspire 5738G | Public Internet | Multiplayer game server |
| Copyparty | Active | Aspire 5738G | LAN / Cloudflare Tunnel | File transfer and file sharing |

---

## Service Details

### SSH

#### Description

Secure remote administration of the production server.

#### Access

- SSH key authentication only
- Password authentication disabled
- Protected by Fail2ban
- Firewall rule present

#### Criticality

High

---

### Minecraft Server

#### Description

Primary user-facing service.

#### Access

- Publicly accessible
- Router port forwarding configured
- TCP Port: 25565

#### Criticality

Medium

---

### Copyparty

#### Description

File transfer and sharing service.

#### Access

- Listening on TCP 3923
- Available on local network
- Cloudflare Tunnel configured

#### Criticality

Low

---

## Planned Future Services

| Service | Status |
|----------|----------|
| VPN Server | Planned |
| Monitoring Stack | Planned |
| Reverse Proxy | Planned |
| Docker Services | Planned |

---

## Review History

| Date | Notes |
|--------|--------|
| 2026-06 | Initial inventory created during Phase 0 |