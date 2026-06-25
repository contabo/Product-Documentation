---
title: "Dedicated Server"
description: "Full dedicated Hardware Power."
lead: "Contabo's flagship product — maximum resources at minimum cost."
date: 2026-06-25
lastmod: 2026-06-25
draft: false
weight: 40
toc: true
---

# Dedicated Servers — Product Documentation

> **Product:** Dedicated Servers (Bare Metal)  
> **Category:** Compute  
> **URL:** contabo.com/en/dedicated-servers/  
> **Source:** contabo.com | **Last updated:** June 2026

---

## Overview

Dedicated Servers — also referred to as Bare Metal — are single-tenant physical machines where every resource (CPU, RAM, storage, and network) belongs exclusively to one customer. There are no shared hypervisors, no neighboring tenants, and no resource contention. You either run the OS directly on the hardware or install your own hypervisor (Proxmox, KVM, VMware) to create your own virtualized environment.

Contabo's Dedicated Server lineup includes AMD Ryzen consumer-grade, AMD EPYC Genoa, and the latest AMD EPYC Turin (9th gen) processors. AMD EPYC Turin processors deliver 17% better instructions-per-clock compared to the previous Genoa generation. Outlet Servers (discounted refurbished configurations) are also available.

---

## Ideal Use Cases

- High-traffic websites and large-scale e-commerce platforms
- Production databases with heavy transaction volumes (OLTP, data warehouses)
- AI/ML model training requiring full GPU access
- Self-managed hypervisor environments (Proxmox, VMware ESXi, KVM)
- Game servers requiring stable, low-latency performance
- Crypto mining operations
- Applications with strict data isolation or compliance requirements (GDPR, HIPAA, PCI-DSS)
- Reseller hosting with full hardware control
- Rendering farms and computationally intensive media processing

---

## Plans & Pricing

| Server | CPU | Cores / Freq. | Base RAM | Max RAM | Base Storage | Port | Traffic | Price/month |
|---|---|---|---|---|---|---|---|---|
| AMD Ryzen 12 Cores | AMD Ryzen 9 7900 | 12 × 3.70 GHz | 64 GB | 128 GB | 1 TB NVMe | 1 Gbit/s | Unlimited* | **€96.00** |
| AMD Genoa 24 Cores | AMD EPYC 9224 | 24 × 2.50 GHz (3.70 max) | 128 GB REG ECC | 768 GB | 2 × 1 TB SSD | 1 Gbit/s | Unlimited* | **€169.00** |
| AMD Turin 32 Cores *(Special Offer)* | AMD EPYC 9355P | 32 × 3.55 GHz (4.20 max) | 128 GB | 768 GB | 2 × 1 TB NVMe | 1 Gbit/s (10 Gbit/s available) | Unlimited* | **from €249.00** |
| AMD Turin 64 Cores | AMD EPYC 9555P | 64 × 3.20 GHz (4.20 max) | 192 GB | 1,152 GB | 2 × 1 TB NVMe | 1 Gbit/s (10 Gbit/s available) | Unlimited* | **€666.00** |

> Additional RAM, storage, and GPU configurations are available for all models.  
> Outlet Servers offer discounted pricing on selected hardware configurations.  
> \* Incoming traffic: unlimited and unmetered. Outgoing: fair usage policy applies.

---

## Key Features

| Feature | Details |
|---|---|
| **Resource isolation** | 100% single-tenant — CPU, RAM, storage, and network exclusively yours |
| **CPU** | AMD Ryzen 9 (consumer), AMD EPYC Genoa, or AMD EPYC Turin (latest gen) |
| **RAM** | ECC memory on EPYC platforms; up to 1,152 GB on the 64-core Turin |
| **Storage options** | HDD, SSD, NVMe — configurable; hardware and software RAID available |
| **Network port** | 1 Gbit/s standard; 10 Gbit/s available on Turin-generation servers |
| **Traffic** | Unlimited inbound; outbound fair usage policy |
| **Provisioning** | Most standard configurations within 90 minutes of payment confirmation |
| **GPU add-on** | NVIDIA GeForce and Tesla GPUs available for AI/ML and rendering workloads |
| **Nested virtualization** | Full hypervisor support — Proxmox, KVM, VMware, Hyper-V |
| **Remote management** | IPMI and KVM-over-IP for out-of-band console access and server control |
| **IP addresses** | Dedicated IPv4 + IPv6; additional IPs available |
| **Private networking** | Create isolated private networks with unlimited free internal traffic |
| **DDoS protection** | Always-on, network-level, automatic — no extra cost |
| **Customization** | RAM, storage, and GPU upgrades available on all models |

---

## Storage Options

| Type | Description | Best For |
|---|---|---|
| **HDD** | Mechanical spinning disks; high capacity, lower cost | Backups, archives, cost-sensitive high-volume storage |
| **SSD** | Flash memory, no moving parts; reliable and fast | General production workloads, databases |
| **NVMe** | PCIe-attached flash; lowest latency, highest throughput | Real-time analytics, transaction-heavy systems, virtualization |

**RAID configurations:** Hardware and software RAID both available for redundancy and read/write performance improvements.

---

## GPU Add-On

NVIDIA GeForce and Tesla GPUs can be added to Dedicated Servers:

- Suitable for AI/ML training, data analytics, rendering, and high-performance parallel processing
- Full CUDA support
- Combined with EPYC CPUs, large RAM configurations, and fast NVMe storage for balanced AI workloads

For GPU-specific cloud instances, see the [GPU Cloud documentation](05_gpu_cloud.md).

---

## Supported Operating Systems

| OS | Cost |
|---|---|
| Ubuntu | Free |
| Debian | Free |
| CentOS | Free |
| AlmaLinux | Free |
| Rocky Linux | Free |
| Windows Server | Additional monthly fee |

---

## Software & App Images (1-Click)

Proxmox · Docker · Plesk *(paid)* · cPanel *(paid)* · Custom ISOs supported

---

## Management & DevOps

- **Customer Control Panel** (my.contabo.com): server management, reinstall, DNS, billing, snapshot management (integration in progress)
- **IPMI**: Out-of-band remote management — restart, monitor, and troubleshoot as if physically on-site
- **KVM-over-IP**: Remote console access, including pre-boot and BIOS-level control
- **Contabo API**: RESTful; covers provisioning, networking, and storage
- **CLI (`cntb`)**: Command-line mirror of the API
- **cloud-init**: Automated provisioning with user-data scripts at boot
- **Custom ISOs**: Upload and boot from custom images
- **SSH keys**: Inject at deployment time

---

## Availability & Locations

Deployed across **12 data centers** in **9 global regions**:

EU (default) · USA (East & West) · United Kingdom · Singapore · Japan · Australia · India

> Non-EU regions may carry additional fees. The 10 Gbit/s uplink is currently available on AMD Turin configurations.

---

## Billing Terms

| Term | Details |
|---|---|
| Minimum initial contract | 1 month |
| Following contracts | Equal to initial term |
| Billing cycles | Monthly, quarterly, 6-month, annual |
| Annual discount | Available |
| Setup fee | None on standard configurations |
| Cancellation notice | None (pre-paid) / 4 weeks (post-paid) |
| Payment | Pre-paid or post-paid |
| Fast provisioning limit | 1 order per customer (max. 5 servers); standard configs only; no order notes; automated payment |

---

## Support

| Channel | Availability |
|---|---|
| Live Chat | 24/7, English-speaking agents |
| ContaBro (AI chatbot) | In-panel; escalates to human agents |
| Support Tickets / Email | 24/7 |
| Help Desk (self-service) | help.contabo.com |
| Tutorial Videos | YouTube |

Contabo provides **unmanaged hosting**. Support covers network, hardware failures, and initial 1-click add-on setup. OS configuration, hypervisor management, application troubleshooting, and third-party software are the customer's responsibility.

---

## Limitations & Notes

- Standard configurations provision within ~90 minutes; custom configurations (non-standard RAM, storage, GPU) may take longer.
- Hardware upgrades (CPU, RAM, storage) may require downtime and hardware swap by Contabo engineers.
- GPU add-ons are subject to availability — contact sales or support for GPU-enabled configurations.
- The fast provisioning offer is limited to 1 order per customer, max. 5 servers, standard configs only.
- Windows Server incurs an additional monthly license fee.

---

*Prices listed in EUR, excluding VAT. Specifications subject to change — verify current details at contabo.com.*
