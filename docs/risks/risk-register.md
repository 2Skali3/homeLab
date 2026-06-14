# Risk Register

## Date
2026-06-14 Sunday

## Purpose

This document tracks known infrastructure risks, their impact, likelihood, and planned mitigations.

Risks should be reviewed after major infrastructure changes and at the completion of each project phase.

---

## Risk Summary

| ID    | Risk                                    | Impact   | Likelihood | Severity | Mitigation Status |
| ----- | --------------------------------------- | -------- | ---------- | -------- | ----------------- |
| R-001 | No backup system                        | Critical | High       | Critical | Open              |
| R-002 | Single SSD failure on production server | High     | Medium     | High     | Open              |
| R-003 | Aging production hardware               | Medium   | Medium     | Medium   | Monitoring        |
| R-004 | Services not documented                 | Medium   | Medium     | Medium   | In Progress       |

---

## Risk Details

### R-001 — No Backup System

#### Description

The production server currently has no automated backup solution.

#### Impact

Loss of:

* Minecraft world data
* Service configuration
* System configuration
* Documentation stored on the server

#### Current Controls

None.

#### Planned Mitigation

Implement automated backups to a dedicated backup drive.

---

### R-002 — Single SSD Failure

#### Description

The production server relies on a single SSD.

#### Impact

Complete outage and data loss.

#### Current Controls

None.

#### Planned Mitigation

Implement backups and recovery procedures.

---

### R-003 — Aging Production Hardware

#### Description

The Aspire 5738G platform is based on older hardware.

#### Impact

Potential future hardware failure or compatibility limitations.

#### Current Controls

Hardware inventory and audit completed.

#### Planned Mitigation

Monitor hardware health and maintain backups.

---

### R-004 — Services Not Documented

#### Description

Services can be deployed without being recorded in the service inventory.

#### Impact

Reduced maintainability and troubleshooting difficulty.

#### Current Controls

Service inventory created.

#### Planned Mitigation

Update documentation whenever a new service is deployed.

---

## Review History

| Date    | Notes                                        |
| ------- | -------------------------------------------- |
| 2026-06 | Initial risk register created during Phase 0 |
