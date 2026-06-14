# Storage Audit - June 2026

## Audit Information

Date: 2026-06-14 Sunday

Purpose:

Assess storage layout, utilization, capacity, and recoverability.

---

# Physical Storage

## Primary Storage Device

| Property | Value |
|-----------|----------|
| Device | /dev/sda |
| Capacity | 447 GB |
| Type | SSD |

---

# Filesystem Utilization

| Filesystem | Size | Used | Available |
|------------|------|------|------------|
| / | 98 GB | 24 GB | 70 GB |

---

# LVM Findings

## Volume Group

ubuntu-vg

| Property | Value |
|-----------|----------|
| Total Capacity | 445 GB |
| Allocated | 100 GB |
| Free Capacity | 345 GB |

---

## Logical Volume

ubuntu-lv

Mount Point:

/

Allocated Size:

100 GB

---

# Backup Assessment

## Automated Backups

Not Present

## Minecraft Backups

Not Present

## System Configuration Backups

Not Present

---

# Risk Assessment

## Critical Risk

No backup system currently exists.

Potential loss includes:

- Minecraft world data
- Operating system configuration
- Service configuration
- Documentation stored on server

---

# Findings

## Positive Findings

- Significant storage capacity available
- LVM successfully configured
- No storage pressure identified

## Concerns

- No backups
- Single SSD failure would result in complete service loss

---

# Lessons Learned

LVM provides flexibility for future storage growth.

Recoverability is more important than capacity.

---

# Future Improvements

- Implement backup strategy
- Test recovery procedures
- Document backup workflows