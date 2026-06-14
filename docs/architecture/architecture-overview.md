# Architecture Overview

## Date 
2026-06-14 Sunday

## Purpose

This document provides a high-level overview of the homelab architecture.

Detailed diagrams are stored in:

docs/architecture/diagrams/

---

# Design Principles

1. Learning over convenience
2. Security over convenience
3. Documentation first
4. Reproducible infrastructure
5. Modular architecture

---

# Current Architecture

## Production Environment

### Aspire 5738G

Current responsibilities:

- SSH administration
- Minecraft hosting
- Copyparty file sharing

---

## Network Edge

### Cloudflare

Responsibilities:

- DNS management
- Tunnel connectivity
- External access control

---

## Home Router

Responsibilities:

- Internet gateway
- DHCP
- Firewall
- Port forwarding

---

# Planned Architecture

## Production Environment

Responsibilities:

- Public services
- Stable workloads
- Long-term hosting

---

## Lab Environment

### Aspire E15

Responsibilities:

- Docker experimentation
- Linux experimentation
- Security testing
- Infrastructure validation

---

# Security Model

## Public Zone

Examples:

- Minecraft
- Future public services

---

## Internal Zone

Examples:

- Production server
- Lab server

---

## Administrative Zone

Examples:

- SSH
- Monitoring
- Dashboards

Access to administrative services should require VPN access whenever practical.

---

# Planned Diagrams

## Current Architecture Diagram

Documents the current infrastructure state.

---

## Target Architecture Diagram

Documents the intended future state.

---

## Security Boundary Diagram

Documents trust boundaries and exposure levels.

---

# Review History

| Date | Notes |
|--------|--------|
| 2026-06 | Initial architecture document created |