# Storage VPS — Product Documentation

> **Product:** Storage VPS  
> **Category:** Compute / Storage  
> **URL:** contabo.com/en/storage-vps/  
> **Source:** contabo.com | **Last updated:** June 2026

---

## Overview

Storage VPS plans are purpose-built for workloads that require large amounts of affordable SSD storage inside a full virtual machine. Unlike Object Storage (which is accessed via API), Storage VPS gives you a complete Linux or Windows environment with root access and a large SSD block device — ideal for high-capacity workloads that don't demand extreme I/O speed. All plans include unlimited traffic and are priced competitively against equivalent Cloud VPS tiers, with the storage-to-price ratio as the primary differentiator.

**Storage VPS 20 carries the "Unbeatable Value" badge on Contabo's website**, delivering 400 GB SSD, 3 vCPUs, and 8 GB RAM for €7.00/month.

---

## Ideal Use Cases

- Backups and disaster recovery (database dumps, server snapshots, archive files)
- Self-hosted Nextcloud file storage
- Block storage alternative (full VM with large disk pool)
- Cold archiving of infrequently accessed data
- Log aggregation and long-term log retention
- Data repositories for analytics pipelines
- FTP/SFTP file servers
- Media asset storage (photos, video files)

---

## Plans & Pricing

| Model | vCPU Cores | RAM | SSD Storage | Network Port | Traffic | Price/month |
|---|---|---|---|---|---|---|
| Storage VPS 10 | 2 vCPUs | 4 GB | 300 GB SSD | 200 Mbit/s | Unlimited* | **€4.50** |
| Storage VPS 20 ⭐ | 3 vCPUs | 8 GB | 400 GB SSD | 300 Mbit/s | Unlimited* | **€7.00** |
| Storage VPS 30 | 6 vCPUs | 18 GB | 1 TB SSD | 600 Mbit/s | Unlimited* | **€14.00** |
| Storage VPS 40 | 8 vCPUs | 30 GB | 1.2 TB SSD | 800 Mbit/s | Unlimited* | **€25.00** |
| Storage VPS 50 | 14 vCPUs | 50 GB | 1.4 TB SSD | 1 Gbit/s | Unlimited* | **€37.00** |

> ⭐ "Unbeatable Value" — Contabo's recommended Storage VPS plan.  
> \* Incoming traffic: unlimited and unmetered. Outgoing: fair usage policy applies. Contabo reserves the right to throttle servers with exceptionally high or disruptive usage.

---

## Key Features

| Feature | Details |
|---|---|
| **Storage type** | High-capacity SSD — optimized for volume, not peak I/O speed |
| **CPU** | Shared vCPU cores |
| **Traffic** | Unlimited inbound; fair usage applies on outbound |
| **Network speed** | 200 Mbit/s to 1 Gbit/s depending on plan |
| **Provisioning** | Minutes via Control Panel, API, or CLI |
| **IP addresses** | Dedicated IPv4 + IPv6 per instance; additional IPs available |
| **Private networking** | VLANs between servers; internal traffic free and unlimited |
| **Firewall** | Free built-in firewall, configurable via Control Panel |
| **DDoS protection** | Always-on, network-level, automatic — no extra cost |
| **Snapshots** | Available via Control Panel |
| **Auto Backup** | Available as paid add-on |
| **API & CLI** | Full management via Contabo API and CLI (`cntb`) |

---

## Supported Operating Systems

| OS | Cost |
|---|---|
| Ubuntu | Free |
| Debian | Free |
| CentOS | Free |
| Windows Server | Additional monthly fee |

---

## Software & App Images (1-Click)

Webmin (free) · Docker · Plesk *(paid)* · cPanel *(paid)*

---

## Management & DevOps

- **Customer Control Panel** (my.contabo.com): start/stop/restart, reinstall, snapshots, VNC access, DNS management
- **Contabo API**: RESTful; covers provisioning, networking, snapshots, storage
- **CLI (`cntb`)**: Command-line mirror of the API for scripting and automation
- **cloud-init**: Automated provisioning with user-data scripts at boot
- **Custom images**: Upload and deploy custom OS images or ISOs
- **SSH keys**: Inject at deployment time via Control Panel or API

---

## Availability & Locations

Deployed across **12 data centers** in **9 global regions**:

EU (default) · USA (East & West) · United Kingdom · Singapore · Japan · Australia · India

> Region selection is available at order time. Non-EU regions may carry an additional monthly fee.

---

## Billing Terms

| Term | Details |
|---|---|
| Minimum initial contract | 1 month |
| Following contracts | Equal to initial term |
| Billing cycles | Monthly, quarterly, 6-month, annual |
| Annual discount | Yes — reduced per-month rate |
| Setup fee | None |
| Cancellation notice | None (pre-paid) / 4 weeks (post-paid) |
| Payment | Pre-paid or post-paid |

---

## Support

| Channel | Availability |
|---|---|
| Live Chat | 24/7, English-speaking agents |
| ContaBro (AI chatbot) | In-panel; escalates to human agents |
| Support Tickets / Email | 24/7 |
| Help Desk (self-service) | help.contabo.com |
| Tutorial Videos | YouTube |

Contabo provides **unmanaged hosting**. Support covers network, hardware, and initial 1-click add-on setup. OS configuration, application troubleshooting, and third-party software are the customer's responsibility.

---

## Limitations & Notes

- Storage type is SSD, **not NVMe** — suitable for high-capacity use cases, not for extreme I/O throughput workloads (use Cloud VPS with NVMe for that).
- Upgrading to a different storage plan requires a server reinstall — back up data first.
- Changing storage type also requires a reinstall and full data backup.
- Additional SSD storage beyond the plan's base can be added via Control Panel (Cloud VPS process); VDS/Dedicated customers must contact support.
- Windows Server incurs an additional monthly license fee.

---

*Prices listed in EUR, excluding VAT. Specifications subject to change — verify current details at contabo.com.*
