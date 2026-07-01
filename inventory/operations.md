# operations.md

Last Updated: 2026-06-28



## Purpose

Tracks all active and planned services, security posture, known risks,

and operational findings for the homelab.

This file is the operational source of truth.

Audit findings are incorporated directly rather than stored separately.



---



# Active Services



| Service | Host | Status | Criticality |

|---------|------|--------|-------------|

| SSH | skaliserver | Active | High |

| Minecraft Server | skaliserver | Active | Medium |

| Copyparty | skaliserver | Active | Low |



---



# Service Details



## SSH

| Property | Value |

|----------|-------|

| Purpose | Remote server administration |

| Port | 22 |

| Access | Internal network only |

| Authentication | Key-based only — password authentication disabled |

| Root login | Disabled — root account locked |

| Brute-force protection | Fail2ban active |

| Firewall rule | Present |



---



## Minecraft Server

| Property | Value |

|----------|-------|

| Purpose | Primary user-facing service |

| Port | TCP 25565 |

| Access | Public internet via router port forward |

| Typical load | 2–6 players |

| Backups | Not configured |



---



## Copyparty

| Property | Value |

|----------|-------|

| Purpose | File transfer and sharing |

| Port | TCP 3923 |

| Access | LAN + Cloudflare Tunnel |

| Backups | Not configured |



---



# Firewall Configuration (UFW)



| Property | Value |

|----------|-------|

| Status | Active |

| Default incoming | Deny |

| Default outgoing | Allow |

| Explicit allow rules | SSH (22), Minecraft (25565) |



### Notes

- Copyparty is accessible via Cloudflare Tunnel — no direct port forward required

- No SSH port forwarding configured on the router — SSH remains internal only



---



# Security Posture



## Current Baseline Assessment

Security posture exceeds typical beginner homelab deployments.

Primary weakness is recoverability, not access controls.



## Confirmed Controls

| Control | Status |

|---------|--------|

| SSH key authentication | Enforced |

| Password authentication | Disabled |

| Root account | Locked |

| Firewall | Active, default-deny inbound |

| Fail2ban | Active, protecting SSH |

| Public attack surface | Minimal — Minecraft port forward + Cloudflare Tunnel only |

| SSH exposed to internet | No |



---



# Backup Status



| Target | Status |

|--------|--------|

| Minecraft world data | No backup |

| System configuration | No backup |

| Service configuration | No backup |

| Automated backup system | Not configured |



### Risk Assessment

**Critical.** A single SSD failure results in total loss of all services,

world data, and configuration. This is the highest-priority unresolved

risk in the project.



---



# Known Risks



| Risk | Impact | Likelihood | Priority |

|------|--------|------------|----------|

| No backup system | Critical | Medium | Critical |

| SSD failure (single point) | High | Medium | High |

| RAM at maximum capacity on production server | Medium | Low | Low |

| No monitoring or alerting | Medium | — | Medium |

| USB-to-Ethernet adapter failure | High | Low | Medium |

| Firmware significantly outdated (2009) | Low | Low | Low |



### Notes

- Production server CPU does not support virtualization

- RAM cannot be expanded beyond current 8 GB on production server

- USB-to-Ethernet is the sole network path — no failover available



---



# Planned Services



| Service | Purpose | Priority |

|---------|---------|---------|

| VPN Server | Secure remote administration | High |

| Monitoring Stack | Observability and alerting | High |

| Reverse Proxy | Unified service routing | High |

| Docker Environment | Containerized service deployment | High |

| Backup System | Recoverability | Critical |



---



# Audit Log



## Hardware Audit — 2026-06-14

- CPU documentation corrected: T6600 → P7350

- RAM and storage utilization confirmed as low

- Firmware version noted: V1.09 (2009-05-11) — old but no immediate issues



## Network Audit — 2026-06-14

- Active interface confirmed: enx00e04c68aceb (USB-to-Ethernet)

- Firewall verified active with correct default-deny policy

- Cloudflare Tunnel operational and verified

- Service inventory updated to include Copyparty



## Security Audit — 2026-06-14

- SSH keys enforced, passwords disabled, root locked — all confirmed

- Fail2ban active and protecting SSH

- No backup strategy identified — flagged as critical risk



## Storage Audit — 2026-06-14

- LVM layout confirmed and documented

- 345 GB unallocated in volume group — available for future use

- No backup system present — confirmed critical risk



---



# Lessons Learned



- Audits should verify assumptions — documentation can drift from reality

- Listening services should be periodically audited and exposure verified

- Recoverability must be treated as a first-class concern, not an afterthought

- LVM was a good choice — provides flexibility for future storage growth



---



# Review History



| Date | Notes |

|------|-------|

| 2026-06-14 | Initial inventories and audits completed |

| 2026-06-28 | Consolidated into operations.md |
