# Storage Inventory

## Date

2026-06-14 Sunday

## Purpose

This document tracks physical storage devices, logical storage allocation, and available capacity.

---

# Production Storage

## Primary SSD

| Property | Value |
|-----------|----------|
| Device | /dev/sda |
| Capacity | 447 GB |
| Purpose | Operating System and Services |

---

# Partition Layout

| Partition | Purpose | Size |
|------------|---------|------|
| sda1 | BIOS Boot | 1 MB |
| sda2 | /boot | 2 GB |
| sda3 | LVM Physical Volume | 445 GB |

---

# LVM Layout

## Volume Group

ubuntu-vg

### Capacity

445 GB

### Free Capacity

345 GB

---

## Logical Volume

ubuntu-lv

### Mount Point

/

### Allocated Size

100 GB

---

# Available Capacity

| Filesystem | Size | Used | Available |
|------------|------|------|------------|
| / | 98 GB | 24 GB | 70 GB |

---

# Additional Storage Resources

## Spare Drives

Multiple 500 GB HDDs available.

## USB HDD Enclosure

Available.

---

# Backup Status

Current State:

No automated backups configured.

---

# Future Usage

- Backup destination
- Recovery testing
- Storage experimentation

---

# Review History

| Date | Notes |
|--------|--------|
| 2026-06 | Initial inventory created |