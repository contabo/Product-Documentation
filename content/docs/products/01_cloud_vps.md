---
title: "Cloud VPS"
description: "KVM-based virtual private servers with AMD EPYC CPUs and unlimited traffic."
lead: "Contabo's flagship product — maximum resources at minimum cost."
date: 2026-06-25
lastmod: 2026-06-25
draft: false
weight: 10
toc: true
---

# Cloud VPS — Product Documentation

> **Product:** Cloud VPS (Virtual Private Servers)  
> **Category:** Compute  
> **URL:** contabo.com/en/vps-server/  
> **Source:** contabo.com | **Last updated:** June 2026

---

## Overview

Cloud VPS is Contabo's flagship product and the entry point for most customers. These are KVM-based virtualized servers with dedicated resource allocations — offering shared vCPU cores, generous RAM, and a choice between Gen 4 PCIe NVMe or standard SSD storage. The entire lineup was redesigned in May 2025 to deliver more performance per euro than any comparable offering on the market.

**Cloud VPS 20 is Contabo's most popular plan**, offering 6 vCPUs, 12 GB RAM, and 100 GB NVMe for €7.00/month.

---

## Ideal Use Cases

- Static and dynamic websites, WordPress, CMS platforms
- Web application backends and REST APIs
- Development, staging, and CI/CD environments
- Self-hosted services (Nextcloud, Bitwarden, Gitea, etc.)
- Small to medium databases
- Blockchain nodes (Bitcoin, Ethereum)
- Crypto trading platforms
- Reseller hosting (cPanel/Plesk)

---

## Plans & Pricing

| Model | vCPU Cores | RAM | NVMe Storage | SSD Alternative | Network Port | Traffic | Price/month |
|---|---|---|---|---|---|---|---|
| Cloud VPS 10 | 4 vCPUs | 8 GB | 75 GB NVMe | 150 GB SSD | 200 Mbit/s | Unlimited* | **€4.50** |
| Cloud VPS 20 ⭐ | 6 vCPUs | 12 GB | 100 GB NVMe | 200 GB SSD | 300 Mbit/s | Unlimited* | **€7.00** |
| Cloud VPS 30 | 8 vCPUs | 24 GB | 200 GB NVMe | 400 GB SSD | 600 Mbit/s | Unlimited* | **€14.00** |
| Cloud VPS 40 | 12 vCPUs | 48 GB | 250 GB NVMe | 500 GB SSD | 800 Mbit/s | Unlimited* | **€25.00** |
| Cloud VPS 50 | 16 vCPUs | 64 GB | 300 GB NVMe | 600 GB SSD | 1 Gbit/s | Unlimited* | **€37.00** |
| Cloud VPS 60 | 18 vCPUs | 96 GB | 350 GB NVMe | 700 GB SSD | 1 Gbit/s | Unlimited* | **€49.00** |

> ⭐ Most popular plan.  
> \* Incoming traffic: unlimited and unmetered. Outgoing: up to 32 TB/month at EU locations; fair usage policy applies. Contabo reserves the right to throttle servers with exceptionally high or disruptive usage.

---

## Key Features

| Feature | Details |
|---|---|
| **Virtualization** | KVM hypervisor |
| **CPU** | AMD EPYC (modern generation), shared vCPU cores |
| **Storage choice** | Gen 4 PCIe NVMe (faster) or standard SSD (higher capacity) — both included at no extra cost |
| **Traffic** | Unlimited inbound; up to 32 TB outbound (EU); fair usage applies |
| **Network speed** | 200 Mbit/s to 1 Gbit/s depending on plan |
| **Provisioning** | Minutes via Control Panel, API, or CLI |
| **IP addresses** | Dedicated IPv4 + IPv6 per instance; additional IPs available |
| **Private networking** | VLANs between servers; internal traffic free and unlimited |
| **Firewall** | Free built-in firewall, configurable via Control Panel |
| **DDoS protection** | Always-on, network-level, automatic — no extra cost |
| **Snapshots** | Up to 3 snapshot versions, managed via Control Panel |
| **Auto Backup** | Available as paid add-on (daily, up to 10 versions) |
| **Nested virtualization** | Not supported — use VDS or Dedicated Server for running VMs |
| **Storage expansion** | Additional SSD/NVMe purchasable directly from Control Panel |

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

Docker · LAMP · Webmin (free) · Plesk *(paid)* · cPanel *(paid)* · Blockchain node images (Bitcoin, Ethereum, and others)

---

## Management & DevOps

- **Customer Control Panel** (my.contabo.com): start/stop/restart, reinstall, snapshots, VNC access, storage expansion, DNS management
- **Contabo API**: RESTful; covers provisioning, networking, snapshots, storage
- **CLI (`cntb`)**: Command-line mirror of the API for scripting and automation
- **cloud-init**: Automated provisioning with user-data scripts at boot
- **Custom images**: Upload and deploy custom OS images or ISOs
- **SSH keys**: Inject at deployment time via Control Panel or API
- **CI/CD integration**: API and CLI are compatible with GitHub Actions, GitLab CI, and Terraform

---

## Availability & Locations

Deployed across **12 data centers** in **9 global regions**:

EU (default) · USA (East & West) · United Kingdom · Singapore · Japan · Australia · India

> Region selection is available at order time. Non-EU regions may carry an additional monthly fee. The Customer Control Panel displays expected latency per location.

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

- Nested virtualization is **not supported** on Cloud VPS. Use Cloud VDS or Dedicated Servers to run VMs.
- Storage type (NVMe vs. SSD) change requires a server reinstall — back up data first.
- Windows Server incurs an additional monthly license fee.
- Provisioning time is typically a few minutes; may vary by location.

---

*Prices listed in EUR, excluding VAT. Specifications subject to change — verify current details at contabo.com.*
