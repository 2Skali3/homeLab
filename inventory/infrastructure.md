# infrastructure.md

Last Updated: 2026-06-28



## Purpose

Single source of truth for all physical hardware, storage, and network

infrastructure available to the homelab project.

Includes both active homelab devices and personal devices available for

future use or repurposing.



---



# Homelab Servers



## Production Server — Aspire 5738G-734G50Mn

| Property | Value |

|----------|-------|

| Hostname | skaliserver |

| IP Address | 192.168.1.10 |

| Operating System | Ubuntu Server 24.04.4 LTS |

| CPU | Intel Core2 Duo P7350 @ 2.00 GHz |

| RAM | 8 GB DDR3 (maximum supported) |

| Storage | 480 GB SSD (Patriot Burst PBU480GS25SSDR) |

| GPU | NVIDIA GeForce G105M (512 MB VRAM) |

| Network | USB-to-Ethernet adapter (enx00e04c68aceb) — built-in NIC non-functional |

| Power | Battery installed — provides limited UPS-like protection |



### Notes

- Primary homelab server

- Currently hosts Minecraft and Copyparty

- Virtualization not supported by CPU

- RAM is already at maximum supported capacity

- Future storage expansion may involve a DAS



---



## Lab Server — Aspire E15 E5-573G-51VE

| Property | Value |

|----------|-------|

| Hostname | Not yet assigned |

| Operating System | Lubuntu (Arch Linux installation previously started) |

| CPU | Intel Core i5-4210U (1.7 GHz base / 2.7 GHz Turbo) |

| RAM | 8 GB DDR3L (1×8 GB, upgradeable to 2×8 GB = 16 GB max) |

| Storage | 512 GB HDD |

| GPU | NVIDIA GeForce 920M (2 GB VRAM) |

| No M.2 slot available | |



### Notes

- Intended for Docker experimentation, Linux learning, security testing

- May eventually become a lightweight management or remote-access node

- RAM upgrade is a low-cost meaningful improvement when needed



---



## Legacy Device — Aspire 8930G-664G64Bn

| Property | Value |

|----------|-------|

| CPU | Unknown |

| RAM | 4 GB (2×2 GB) |

| Storage | None currently installed |



### Notes

- Considered legacy hardware

- Potential use cases: Blu-ray ripping station, monitoring/dashboard display

- May be dismantled for parts if no suitable use case is identified



---



# Daily Use Devices (Not for Experimentation)



| Device | Role |

|--------|------|

| Samsung Galaxy Book3 Pro 360 | Primary work laptop — remote administration capable |

| Samsung Galaxy S26 Ultra | Primary phone |



---



# Mobile Devices Available for Repurposing



| Device | Notes |

|--------|-------|

| Samsung Galaxy S22 Ultra | Available |

| Samsung Galaxy S9 | Available |

| Samsung Galaxy S6 Edge | Available |

| Samsung Galaxy (legacy tablet) | Model unknown |



---



# Storage



## Production Server Storage Layout



| Layer | Detail |

|-------|--------|

| Physical device | /dev/sda — 447 GB usable |

| sda1 | BIOS boot partition — 1 MB |

| sda2 | /boot — 2 GB |

| sda3 | LVM Physical Volume — 445 GB |

| Volume Group | ubuntu-vg — 445 GB total, 345 GB free |

| Logical Volume | ubuntu-lv → / — 100 GB allocated |

| Current utilization | 24 GB used / 70 GB available on / |



### Notes

- LVM provides flexibility for future volume expansion

- 345 GB unallocated in the volume group — available for future use



---



## Spare Drives



| Drive | Interface | Speed | Notes |

|-------|-----------|-------|-------|

| Samsung ST500LM012 500 GB 2.5" | SATA | — | Available |

| WDBAAA5000ASL-00 500 GB 2.5" | USB 2.0 | — | USB-only interface |

| Toshiba MQ01ABF050 500 GB 2.5" | SATA 3 | 5400 RPM | Available |

| Toshiba MQ01ABD050 500 GB 2.5" | SATA 3 | 5400 RPM | Available |

| HGST HTS725050A7E630 500 GB 2.5" (×2) | SATA 3 | 7200 RPM | Best candidates for backup use |

| HGST HTS545050A7E680 500 GB 2.5" | SATA 3 | 5400 RPM | Available |

| Generic 1 TB 3.5" HDD | SATA | — | No power source currently available |

| USB drive 8 GB | USB | — | General use |

| USB drive 8 GB | USB | — | Reserved for OS installations only |



### Enclosures

- 2× USB 2.5" SATA enclosures available

- Each enclosure supports one drive at a time

- Currently both unused



### Recommended backup candidates

The two HGST 7200 RPM drives are the highest-quality spare drives available.

Recommended as primary backup targets when backup strategy is implemented.



---



# Networking



## Active Infrastructure



| Device | Role |

|--------|------|

| ZXHN H389X | Primary home router/modem (WindTre ISP) |

| TP-Link Deco E4 AC1200 | Currently unused |

| TG788vn v2 | Legacy router — currently unused |



## ZXHN H389X Capabilities

- Wi-Fi 6 (802.11ax), dual-band 2.4/5 GHz

- Gigabit Ethernet ports

- WPA3 support

- Linux-based firmware

- Static public IP available



---



## LAN Configuration



| Property | Value |

|----------|-------|

| Subnet | 192.168.1.0/24 |

| Default Gateway | 192.168.1.1 |

| Production Server | 192.168.1.10 (skaliserver) |



---



## External Connectivity



| Property | Value |

|----------|-------|

| Domain | skali.me |

| Registrar | Cloudflare Registrar |

| DNS Management | Cloudflare |

| Public IP | Static |

| Tunnel Provider | Cloudflare Tunnel |



---



## Publicly Accessible Services



| Service | Method |

|---------|--------|

| Minecraft | Router port forward — TCP 25565 |

| Copyparty | Cloudflare Tunnel |



---



# Additional Equipment



| Item | Notes |

|------|-------|

| Tapo P125M Smart Plug | Server power monitoring |

| 40 Gbps USB-C Thunderbolt 4 cable (240W) | Available |

| Flying Bear Ghost 3 (3D printer) | Available for printed homelab components |

| Flipper Zero | Available |



---



# Future Hardware Considerations



Purchases should only be recommended when they provide significant value

relative to cost. Do not suggest purchases without clear justification.



| Item | Rationale |

|------|-----------|

| RAM upgrade for Aspire E15 | Low cost, meaningful improvement for Docker workloads |

| SSD for Aspire E15 | HDD is a bottleneck for lab workloads |

| DAS enclosure | Future storage expansion for production server |

| UPS | Proper power protection — battery on laptop is partial mitigation only |

| Larger storage drives | When backup or NAS strategy matures |



---



# Review History



| Date | Notes |

|------|-------|

| 2026-06-14 | Initial inventories created |

| 2026-06-28 | Consolidated and reconciled into infrastructure.md |
