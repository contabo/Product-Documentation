# Cloud VDS — Product Documentation

> **Product:** Cloud VDS (Virtual Dedicated Servers)  
> **Category:** Compute  
> **URL:** contabo.com/en/vds/  
> **Source:** contabo.com | **Last updated:** June 2026

---

## Overview

Cloud VDS occupies the performance tier between Cloud VPS and fully bare-metal Dedicated Servers. The defining difference from VPS is that every VDS instance runs on **dedicated physical CPU cores** — not shared virtual cores. This means neighboring tenants on the same host cannot cause performance degradation ("noisy neighbor" problem). RAM is also 100% reserved. VDS plans are ideal for workloads that need predictable, consistent compute without the cost and management overhead of a full bare-metal server.

A 20% discount is currently available on all VDS plans with an annual commitment.

---

## Ideal Use Cases

- Production databases (PostgreSQL, MySQL, MongoDB) under sustained load
- CPU-intensive backend services and APIs
- Video encoding and transcoding pipelines
- Machine learning inference workloads
- High-frequency trading bots requiring consistent latency
- High-traffic web applications with unpredictable CPU spikes
- Self-hosted hypervisors (Proxmox, KVM, Hyper-V) and virtual machine hosting
- Applications requiring guaranteed compute free from shared-resource contention

---

## Plans & Pricing

| Model | Physical CPU Cores | CPU Model | RAM | NVMe Storage | Network Port | Traffic | Monthly Price | Annual Price (~20% off) |
|---|---|---|---|---|---|---|---|---|
| Cloud VDS S | 3 cores | AMD EPYC 7282, 2.8 GHz | 24 GB | 180 GB NVMe | 250 Mbit/s | Unlimited* | €42.99 | **~€34.40** |
| Cloud VDS M | 4 cores | AMD EPYC 7282, 2.8 GHz | 32 GB | 240 GB NVMe | 500 Mbit/s | Unlimited* | €55.99 | **~€44.80** |
| Cloud VDS L | 6 cores | AMD EPYC 7282, 2.8 GHz | 48 GB | 360 GB NVMe | 750 Mbit/s | Unlimited* | €79.99 | **~€64.00** |
| Cloud VDS XL | 8 cores | AMD EPYC 7282, 2.8 GHz | 64 GB | 480 GB NVMe | 1 Gbit/s | Unlimited* | €102.99 | **~€82.40** |
| Cloud VDS XXL | 12 cores | AMD EPYC 7282, 2.8 GHz | 96 GB | 720 GB NVMe | 1 Gbit/s | Unlimited* | €149.99 | **~€119.00** |

> Additional NVMe storage configurations are available beyond the base amounts listed above.  
> \* Incoming traffic: unlimited and unmetered. Outgoing: fair usage policy applies. Contabo reserves the right to throttle servers with exceptionally high or disruptive usage.

---

## Key Features

| Feature | Details |
|---|---|
| **CPU** | AMD EPYC 7282 — dedicated **physical** cores, not shared vCPUs |
| **Hyper-Threading (SMT)** | AMD Simultaneous Multithreading enabled — each physical core appears as 2 logical vCPUs |
| **Core Performance Boost (CPB)** | AMD automatic frequency boosting for burst performance |
| **RAM** | 100% dedicated — no memory ballooning or sharing with other tenants |
| **Storage** | Enterprise-grade NVMe SSD — fast local disk on all plans |
| **Traffic** | Unlimited inbound; outbound fair usage policy |
| **Network speed** | 250 Mbit/s to 1 Gbit/s depending on plan |
| **Provisioning** | Minutes via Control Panel, API, or CLI |
| **Nested virtualization** | Supported — run Proxmox, KVM, Hyper-V, or other hypervisors |
| **IP addresses** | Dedicated IPv4 + IPv6; additional IPs available |
| **Private networking** | VLANs between servers; internal traffic free and unlimited |
| **Firewall** | Free built-in firewall included on all VDS plans |
| **DDoS protection** | Always-on, network-level, automatic — no extra cost |
| **Snapshots** | Available via Control Panel |
| **Auto Backup** | Available as paid add-on |

---

## Supported Operating Systems

| OS | Cost |
|---|---|
| Ubuntu | Free |
| Debian | Free |
| AlmaLinux | Free |
| Rocky Linux | Free |
| CentOS | Free |
| openSUSE | Free |
| FreeBSD | Free |
| Windows Server | Additional monthly fee |

---

## Software & App Images (1-Click)

Webmin (free) · Docker · Proxmox · Plesk *(paid)* · cPanel *(paid)*

---

## Management & DevOps

- **Customer Control Panel** (my.contabo.com): start/stop/restart, reinstall, snapshots, VNC access, storage management, DNS management
- **Contabo API**: RESTful; covers provisioning, networking, snapshots, storage
- **CLI (`cntb`)**: Command-line mirror of the API for scripting and automation
- **cloud-init**: Automated provisioning with user-data scripts at boot
- **Custom images**: Upload and deploy custom OS images or ISOs
- **SSH keys**: Inject at deployment time via Control Panel or API
- **IPMI / KVM-over-IP**: Not available on VDS (available on Dedicated Servers only)

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
| Annual discount | ~20% off (currently active promotion) |
| Setup fee | None on standard configurations |
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

- CPU cores are dedicated **physical** cores, but the host machine is still multi-tenant at the hardware level — only cores and RAM are exclusively reserved.
- Storage changes (type or capacity) require a server reinstall — back up data before requesting.
- Windows Server incurs an additional monthly license fee.
- IPMI / KVM-over-IP remote management is not available — use the Control Panel VNC console or SSH.
- VDS supports nested virtualization (Proxmox, KVM, Hyper-V); Cloud VPS does not.

---

*Prices listed in EUR, excluding VAT. Specifications subject to change — verify current details at contabo.com.*
