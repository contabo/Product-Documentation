---
title: "Object Storage"
description: "Contabo Object Storage is an S3-compatible cloud storage service built on a Ceph cluster following Red Hat production guidance."
lead: "Contabo's flagship product — maximum resources at minimum cost."
date: 2026-06-25
lastmod: 2026-06-25
draft: false
weight: 60
toc: true
---

# Object Storage — Product Documentation

> **Product:** Object Storage  
> **Category:** Storage  
> **URL:** contabo.com/en/object-storage/  
> **Source:** contabo.com | **Last updated:** June 2026

---

## Overview

Contabo Object Storage is an S3-compatible cloud storage service built on a Ceph cluster following Red Hat production guidance. It is designed as a direct, cost-effective alternative to AWS S3 and similar services — with simple month-to-month flat-rate billing per 250 GB slice, free egress, and no hidden transfer fees.

Unlike Storage VPS (which gives you a full virtual machine with a block disk), Object Storage is accessed entirely via the S3 API or a web UI — there is no server to manage. Every object is **triple-replicated** across servers by default, and storage runs in **high availability mode** at all times.

---

## Ideal Use Cases

- Automated server and database backups
- Disaster recovery archives
- Media file storage (photos, videos, audio)
- Large object storage (up to 5 TB per file)
- Application log retention and cold archiving
- Static website asset hosting (images, JS, CSS)
- NAS alternative (API or mounted filesystem via s3fs/goofys)
- AI/ML dataset storage and model checkpoint archiving
- Integration with existing S3-compatible workflows (drop-in replacement)

---

## Plans & Pricing

Pricing is billed per **250 GB slice** per month. You pay only for the storage tiers you use.

### Europe Region

| Storage Capacity | Price/month |
|---|---|
| 250 GB | **€2.49** |
| 500 GB | **€4.98** |
| 1 TB | **€9.96** |
| 2 TB | **€19.92** |
| 5 TB | **€49.80** |
| 10 TB | **€99.60** |

> Custom sizes can be ordered by selecting the number of 250 GB slices needed.  
> US and Asia regions are also available — check contabo.com for current regional pricing.  
> **Egress (outbound transfer) is included in the flat monthly price** — no separate data transfer charges apply.

---

## Key Features

| Feature | Details |
|---|---|
| **API compatibility** | Fully S3-compatible — change credentials and endpoint to migrate from AWS S3 |
| **Redundancy** | Triple-replication across servers; high availability mode by default |
| **Encryption** | End-to-end encryption in transit (TLS) and at rest |
| **Max object size** | Up to 5 TB per file |
| **Buckets per account** | Up to 100 (default) |
| **Objects per account** | Up to 3 million (default; increasable upon request) |
| **API throughput** | Up to 250 API requests per second |
| **Bandwidth** | 10 MB/s (80 Mbit/s) default; speed depends on internet connection |
| **Versioning** | S3-compatible object versioning supported |
| **Object locking** | Supported via S3 API |
| **ACL management** | Per-object and per-bucket access control lists; manageable via Web UI or API |
| **Link sharing** | Share public or private URLs to individual objects |
| **Auto-scaling limit** | Set monthly data growth caps to prevent billing surprises |
| **DDoS protection** | Always-on, network-level, automatic — no extra cost |
| **Data location control** | Choose storage region (EU, US, Asia); data never moved without written consent |
| **Web UI** | Drag-and-drop file and bucket management without needing the API |
| **Custom domains** | Supported via Cloudflare proxy (CNAME + TLS workaround) |

---

## Storage Regions

| Region | Endpoint Format |
|---|---|
| Europe | `eu2.contabostorage.com` |
| United States | US-region endpoint (see Contabo documentation) |
| Asia | Asia-region endpoint (see Contabo documentation) |

> Contabo will **never** move your data to another region/country without your explicit, written consent.

---

## Compatible Tools & Integrations

| Tool | Type |
|---|---|
| **AWS CLI** | Command-line S3 management |
| **Rclone** | Bulk migration, sync, and transfer |
| **Cyberduck** | GUI-based file management |
| **s3cmd** | Command-line S3 client |
| **WinSCP** | Windows GUI client |
| **Cloudberry Explorer** | GUI-based management |
| **BucketAnywhere** | Multi-cloud storage manager |
| **goofys** | Mount as a filesystem |
| **s3fs-fuse** | Mount as a FUSE filesystem |
| **Nextcloud** | Self-hosted file sync and share integration |
| **Apache Spark** | Big data processing integration |
| **Velero** | Kubernetes backup and restore |
| **Virtualmin** | Web hosting panel integration |
| **Plesk** | Control panel backup integration |

> **Note:** FileZilla Pro forces virtual-hosted-style bucket names and is not compatible. Use Cyberduck as an alternative.  
> cPanel/WHM can use Object Storage as a backup destination via folder mounting.

---

## Migrating from AWS S3

Migration from AWS S3 or any other S3-compatible provider requires only two changes:

1. Update the **endpoint URL** to the Contabo Object Storage endpoint
2. Update the **access credentials** (Access Key ID and Secret Access Key)

No code changes are required for applications built on the standard S3 SDK. Tools like Rclone and AWS CLI support bulk data migration directly.

---

## Management

- **Web UI**: Bucket creation, file uploads (drag-and-drop), ACL management, link sharing — no API knowledge required
- **S3 API**: Full programmatic access — versioning, locking, ACL, bucket policies
- **ACL Management**: Set per-file or per-bucket permissions (read/write/public/private) via Web UI or API
- **Auto-Scaling Limit**: Cap maximum monthly storage growth to control spend

---

## Availability & Locations

Object Storage is available in three regions:

**Europe · United States · Asia**

> Data center locations within each region follow Contabo's global infrastructure. Choose the region closest to your primary data consumers for lowest latency.

---

## Billing Terms

| Term | Details |
|---|---|
| Billing unit | Per 250 GB slice/month |
| Billing model | Flat monthly rate — pay only for slices used |
| Egress fees | None — outbound transfer included |
| Minimum commitment | 1 month |
| Setup fee | None |
| Auto-scaling | Growth cap can be set to prevent unexpected charges |
| Payment | Pre-paid monthly |

---

## Support

| Channel | Availability |
|---|---|
| Live Chat | 24/7, English-speaking agents |
| ContaBro (AI chatbot) | In-panel; escalates to human agents |
| Support Tickets / Email | 24/7 |
| Help Desk (self-service) | help.contabo.com |
| Tutorial Videos | YouTube (step-by-step Object Storage setup guide available) |

Contabo provides infrastructure-level support — network, hardware, and the Object Storage platform itself. Configuration of specific S3 client tools and application-level integration are the customer's responsibility.

---

## Limitations & Notes

- Default bandwidth is 10 MB/s (80 Mbit/s); this is sufficient for most backup and archival workloads but may be a bottleneck for high-throughput streaming applications.
- Default object count (3 million) and bucket count (100) can be increased upon request.
- Public objects changed to private may remain cached and accessible for **up to one hour** after the permission change takes effect.
- Object Storage is accessed via HTTPS only (TLS required) — plain HTTP is not supported. Custom domain setup requires a TLS-terminating proxy (e.g. Cloudflare).
- FileZilla Pro is not compatible due to virtual-hosted-style hostname requirements.

---

*Prices listed in EUR, excluding VAT. Specifications subject to change — verify current details at contabo.com.*
