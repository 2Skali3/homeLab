# homeLab

A security-focused homelab built and documented as a long-term engineering
and learning project.

The goal is not simply to deploy services — it is to develop a genuine
understanding of Linux, networking, Docker, security, monitoring, and
infrastructure as code while producing work that is maintainable,
reproducible, and portfolio-quality.

---

## Current Status

**Phase 0 — homeLab Foundation** (in progress)

Production server running on Ubuntu Server 24.04 LTS, hosting a Minecraft
server and a file sharing service. SSH hardened, firewall configured,
Cloudflare Tunnel operational.

Phase 1 focus: backup and recovery — the highest-priority unresolved
infrastructure risk.

---

## Structure

| Path | Purpose |
|------|---------|
| `inventory/` | Source of truth — hardware, services, project definition |
| `docs/architecture/` | Architecture overviews and diagrams |
| `docs/audits/` | Point-in-time audit reports |
| `docs/decisions/` | Architecture Decision Records (ADRs) |
| `docs/backups/` | Backup strategy and restore testing |
| `docs/risks/` | Risk register |
| `docs/runbooks/` | Operational procedures |
| `docs/learning/` | Notes, lessons learned, content handoffs |

---

## Core Principles

- Security over convenience
- Understanding over shortcuts
- Documentation before complexity
- Modular, replaceable components
- Open-source wherever practical

---

## Author

2Skali3 — Computer Science student building toward DevOps and DevSecOps roles.
