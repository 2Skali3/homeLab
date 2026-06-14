# Hardware Audit - June 2026

## Audit Information

Date: 2026-06-14 Sunday

Purpose:

Validate actual hardware against documented inventory and establish a baseline for future homeLab development.

---

# System Information

## Hostname

skaliserver

## Platform

Acer Aspire 5738G

## Operating System

Ubuntu Server 24.04.4 LTS

---

# CPU Findings

## Documented CPU

Intel T6600

## Actual CPU

Intel Core2 Duo P7350 @ 2.00 GHz

## Result

Documentation was incorrect.

Inventory updated to reflect actual hardware.

---

# Memory Findings

| Property | Value |
|-----------|----------|
| Installed RAM | 7.8 GiB |
| Used During Audit | 577 MiB |
| Available During Audit | 7.2 GiB |

## Assessment

Memory pressure is currently very low.

---

# Hardware Health Observations

## Firmware

Version: V1.09

Date: 2009-05-11

### Observation

Firmware is significantly older than the operating system.

No immediate issues identified.

---

# Findings

## Positive Findings

- Hardware inventory validated
- Low memory utilization
- Stable Ubuntu Server installation

## Corrections Required

- CPU documentation updated from T6600 to P7350

---

# Lessons Learned

Audits should verify assumptions.

Documentation can become inaccurate over time.

---

# Future Improvements

- Continue maintaining hardware inventory
- Monitor hardware reliability
- Maintain backup strategy once implemented