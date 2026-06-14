# Network Audit - June 2026

## Audit Information

Date: 2026-06-14 Sunday

Purpose:

Document network topology, addressing, connectivity, and exposed services.

---

# Host Information

Hostname:

skaliserver

---

# Connectivity

## Active Interface

enx00e04c68aceb

## Gateway

Present and functioning.

---

# Public Exposure

## Minecraft

Exposure Method:

Router Port Forward

---

## Copyparty

Exposure Method:

Cloudflare Tunnel

Tunnel verified during audit.

---

# Administrative Access

## SSH

Status:

Enabled

Access:

Internal network

---

# Firewall Findings

## UFW Status

Active

### Default Policy

Incoming: Deny

Outgoing: Allow

### Explicit Rules

- SSH
- Minecraft

---

# Open Services Identified

| Service | Port |
|----------|------|
| SSH | 22 |
| Copyparty | 3923 |

---

# Findings

## Positive Findings

- Firewall enabled
- Cloudflare Tunnel operational
- Limited public exposure

## Concerns

- Service inventory required updating to include Copyparty

---

# Lessons Learned

Listening services should be periodically audited.

Exposure should always be verified rather than assumed.

---

# Future Improvements

- Deploy VPN for administration
- Document future network changes
- Maintain service inventory