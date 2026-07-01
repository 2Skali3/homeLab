# project.md

Last Updated: 2026-06-28



## Purpose

Defines the goals, constraints, working philosophy, roadmap, conventions,

and repository structure for the homeLab project.

This file is the authoritative reference for any coordinator or execution

chat initialized in this project.



---



# Project Identity



## Name

homeLab



## Repository

github.com/2Skali3/homeLab



## Domain

skali.me



---



# Owner Profile



## Current Status

Computer Science student



## Target Roles

- DevOps Engineer

- DevSecOps Engineer



## Skill Levels

| Skill | Level |

|-------|-------|

| Linux | 6/10 |

| Networking | 5/10 |

| Security | 4/10 |

| Git | 5/10 |

| Docker | Beginner |



## Time Availability

5–10 hours per week.

Roadmap should optimize for sustainability over speed.



---



# Goals



## Primary Goals

All three goals carry equal weight:

1. Build a portfolio and résumé suitable for internship and job applications

2. Develop genuine, transferable technical skills

3. Run useful services at home



## Learning Goals

- Linux administration

- Networking

- Docker and containerization

- Self-hosting

- DevOps practices

- DevSecOps practices

- Monitoring and observability

- Security

- Infrastructure as Code

- Documentation and operational thinking



## Career Goals

Build projects demonstrable in interviews while developing skills in:

- Infrastructure as Code

- Containerization

- Linux administration

- Networking

- Monitoring and observability

- Security practices

- Service deployment and maintenance



---



# Core Philosophy



## Learning First

Prefer approaches that teach transferable skills.

Understanding is more important than convenience.

Explain reasoning before commands.

No black-box solutions.



## Security First

Prefer security over convenience whenever practical.

Administrative services should remain VPN-only whenever possible.

Minimize public attack surface.



## Modular Architecture

Design everything so components are loosely coupled, services are

replaceable, migrations are straightforward, and hardware upgrades

require minimal redesign.



## Documentation First

Every meaningful change produces documentation answering:

- What was done?

- Why was it done?

- How was it implemented?

- How was it verified?

- What was learned?

- What could be improved?



## Infrastructure as Code

Configuration belongs in Git whenever practical.

Infrastructure should become reproducible over time.



## Open Source

Favor open-source software whenever practical.



## Purchases

Do not recommend purchases unless they provide significant value

relative to cost. Existing hardware is always used first.



---



# Constraints



## Critical

- No backup solution currently exists — highest infrastructure risk

- No Docker experience yet



## Technical

- Production server CPU does not support virtualization

- Production server RAM is at maximum supported capacity (8 GB)

- Upload bandwidth is 19.32 Mbps — limiting factor for externally

  accessible services, noted but does not currently influence priority

- USB-to-Ethernet is the sole network path on production server —

  no failover available



## Network Performance

| Metric | Value |

|--------|-------|

| Download | 133.31 Mbps |

| Upload | 19.32 Mbps |

| Ping | 17 ms |

| CGNAT | No |



---



# Desired Services



## High Priority

| Service | Notes |

|---------|-------|

| Backup system | Critical — implement before anything else |

| Secure file sharing | Must support files larger than 40 GB |

| Photo and video storage | — |

| Remote access | From outside home network |

| Minecraft server | 2–6 players, already running |

| Pi-hole | Network-level ad blocking |



## Medium Priority

| Service | Notes |

|---------|-------|

| Media server | — |

| Monitoring dashboard | — |



## Low Priority

| Service | Notes |

|---------|-------|

| Blu-ray ripping station | Aspire 8930G candidate |

| Experimentation services | Aspire E15 |



---



# Exposure Model



## Public (via reverse proxy or port forward)

- Reverse proxy

- File sharing

- Photo and video services

- Minecraft



## VPN Only

- SSH

- Monitoring

- Grafana

- Prometheus

- Docker management

- Infrastructure dashboards

- All administrative interfaces



---



# Professional Visibility



At every meaningful milestone produce:

- GitHub commit with documentation

- Content handoff identifying LinkedIn and Twitter/X post opportunities

- Architecture diagram update if topology changed

- Portfolio entry if milestone is significant



Good content topics include:

- Mistakes and how they were resolved

- Architecture decisions and trade-offs

- Audit findings

- Lessons learned

- Security improvements

- Troubleshooting write-ups



Authenticity is preferred over polished success stories.

Document the journey, not only the results.



---



# Roadmap



## Phases

| Phase | Name | Status |

|-------|------|--------|

| Phase 0 | homeLab Foundation | In Progress |

| Phase 1 | Backup and Recovery | Planned |

| Phase 2 | Networking Fundamentals | Planned |

| Phase 3 | Docker Fundamentals | Planned |

| Phase 4 | Infrastructure as Code Foundations | Planned |

| Phase 5 | Secure Remote Access | Planned |

| Phase 6 | Reverse Proxy and TLS | Planned |

| Phase 7 | Monitoring and Observability | Planned |

| Phase 8 | Secure File Platform | Planned |

| Phase 9 | Photo and Video Platform | Planned |

| Phase 10 | DevSecOps Enhancements | Planned |

| Phase 11 | Advanced Infrastructure | Planned |



Do not reorder phases without documented justification.



## Phase 0 — homeLab Foundation



### Checkpoint A — Completed 2026-06-14

- Hardware audit completed — CPU corrected from T6600 to P7350

- LVM layout discovered and documented

- SSH secured (key auth, password disabled, root locked)

- Firewall configured (UFW, default deny)

- Fail2ban active

- No backup system — flagged as critical risk

- Copyparty exposed via Cloudflare Tunnel

- Minecraft intentionally exposed via port forward



### Checkpoint B — Completed

- GitHub repository created: 2Skali3/homeLab

- Documentation structure established

- Coordinator review requested additions:

  - docs/incidents/

  - docs/decisions/

  - docs/backups/

  - ADR-001, ADR-002, ADR-003 (pending)

  - Architecture diagram layering (infrastructure / platform / applications)

  - Configuration drift added to risk register



### Checkpoint C — Pending

- Rebuild repository structure to match canonical layout

- Rename all files to follow naming conventions

- Populate inventory/ with consolidated context files

- Reconcile all existing content against new structure



---



# Naming Conventions



## Files and Folders

- `camelCase` for all project files and folders

- Exceptions: `README.md`, `LICENSE` — follow GitHub convention



## Dates

- `YYYY-MM-DD` format everywhere



## Hostnames

- Always lowercase: `skaliserver`



## Service Names

- Official casing in prose: `Minecraft`, `Copyparty`, `WireGuard`

- Lowercase in configs, paths, and filenames



## Phases and Checkpoints

- `Phase 0`, `Phase 1` — capitalized, numeric

- `Checkpoint A`, `Checkpoint B` — capitalized alphabetic



## ADRs

- `ADR-001-short-description.md` — zero-padded three digits, kebab-case description



## Runbooks

- `runbook-service-action.md`

- Example: `runbook-minecraft-restore.md`



## Postmortems

- `postmortem-YYYY-MM-DD-short-description.md`



## Git Commits

Conventional Commits format: `type(scope): description`



| Type | Usage |

|------|-------|

| feat | New service or capability |

| fix | Correcting something broken |

| docs | Documentation only |

| chore | Maintenance, restructuring |

| refactor | Restructuring without behavior change |



Example: `docs(inventory): update hardware audit findings`



---



# Repository Structure



homeLab/



├── README.md



├── LICENSE



├── .gitignore



│



├── inventory/



│   ├── infrastructure.md



│   ├── operations.md



│   └── project.md



│



├── config/



│   ├── .gitignore



│   └── private/  (local only, never committed)



│



└── docs/



├── architecture/



│   ├── architectureOverview.md



│   └── diagrams/



│       ├── currentArchitecture.md



│       ├── targetArchitecture.md



│       └── securityBoundary.md



│



├── audits/



│   ├── hardwareAudit-2026-06.md



│   ├── storageAudit-2026-06.md



│   ├── networkAudit-2026-06.md



│   └── securityAudit-2026-06.md



│



├── backups/



│   ├── backupObjectives.md



│   ├── backupStrategy.md



│   └── restoreTesting.md



│



├── decisions/



│   └── README.md



│



├── incidents/



│   └── README.md



│



├── learning/



│   ├── linuxNotes.md



│   ├── networkingNotes.md



│   ├── lessonsLearned.md



│   └── contentHandoffs.md



│



├── risks/



│   └── riskRegister.md



│



└── runbooks/



├── README.md



└── private/



---



# Review History



| Date | Notes |

|------|-------|

| 2026-06-14 | Phase 0 Checkpoints A and B completed |

| 2026-06-28 | project.md created, conventions and structure defined |
