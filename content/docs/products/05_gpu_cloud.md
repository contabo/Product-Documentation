---
title: "GPU Cloud"
description: "Contabo's GPU Cloud provides dedicated and virtualized GPU server instances powered by enterprise-grade NVIDIA hardware."
lead: "Contabo's flagship product — maximum resources at minimum cost."
date: 2026-06-25
lastmod: 2026-06-25
draft: false
weight: 50
toc: true
---

# GPU Cloud — Product Documentation

> **Product:** GPU Cloud  
> **Category:** Compute / AI & ML  
> **URL:** contabo.com/en/gpu-cloud/  
> **Source:** contabo.com | **Last updated:** June 2026

---

## Overview

Contabo's GPU Cloud provides dedicated and virtualized GPU server instances powered by enterprise-grade NVIDIA hardware. Each instance pairs a high-end GPU with a powerful CPU, large system RAM, fast NVMe SSD storage, and generous monthly bandwidth — giving AI and ML teams production-ready compute at predictable flat-rate pricing, without the per-hour billing surprises of hyperscalers.

Instances are available in two deployment models:

- **Dedicated GPU:** Single-tenant physical host — full physical isolation, no neighbors, highest performance consistency
- **Cloud GPU:** Virtualized instance on a shared host — same NVIDIA GPU and specs, slight virtualization overhead, same pricing tier

GPU Cloud is primarily available across **three US locations** with additional global locations available.

---

## Ideal Use Cases

- Large language model (LLM) inference and API serving
- LLM fine-tuning and training
- AI image generation (Stable Diffusion, Flux, etc.)
- Machine learning model training (PyTorch, TensorFlow, JAX)
- Scientific simulations requiring high-throughput parallel compute
- 3D rendering and visualization
- Video encoding and transcoding with GPU acceleration
- Computer vision pipelines

---

## Plans & Pricing

### NVIDIA L40S — Ada Lovelace Architecture

Optimized for multi-workload acceleration: LLM inference, graphics, and video.

| Deployment | GPU | GPU VRAM | vCPUs | System RAM | NVMe Storage | Bandwidth | Price/month |
|---|---|---|---|---|---|---|---|
| Dedicated NVIDIA L40S | 1× L40S | 48 GB | 32 | 106 GB | 1.75 TB | 15 TB | **€600.00** |
| Cloud NVIDIA L40S | 1× L40S | 48 GB | 32 | 106 GB | 1.75 TB | 15 TB | **€630.00** |

### NVIDIA H100 — Hopper Architecture (4th-Gen Tensor Cores)

Up to 4× faster than previous-generation GPUs for advanced language model training.

| Deployment | GPU | GPU VRAM | vCPUs | System RAM | NVMe Storage | Bandwidth | Price/month |
|---|---|---|---|---|---|---|---|
| Dedicated NVIDIA H100 | 1× H100 | 94 GB | 32 | 106 GB | 1.75 TB | 15 TB | **€1,600.00** |
| Cloud NVIDIA H100 | 1× H100 | 94 GB | 32 | 106 GB | 1.75 TB | 15 TB | **€1,953.00** |

### NVIDIA H200

Maximum VRAM configuration — suited for the largest models and highest-throughput workloads.

| Deployment | GPU | GPU VRAM | vCPUs | System RAM | NVMe Storage | Bandwidth | Price/month |
|---|---|---|---|---|---|---|---|
| Dedicated NVIDIA H200 | 1× H200 | 141 GB | 32 | 213.3 GB | 3.84 TB | 15 TB | **€1,650.00** |
| Cloud NVIDIA H200 | 1× H200 | 141 GB | 32 | 213.3 GB | 3.84 TB | 15 TB | **€2,294.00** |

---

## GPU Model Comparison

| GPU | VRAM | Architecture | Tensor Core Gen | Best For |
|---|---|---|---|---|
| NVIDIA L40S | 48 GB | Ada Lovelace | 4th Gen | Inference, multi-workload, graphics, video |
| NVIDIA H100 | 94 GB | Hopper | 4th Gen | LLM training, large-model inference |
| NVIDIA H200 | 141 GB | Hopper (HBM3e) | 4th Gen | Very large models, highest VRAM requirement |

---

## Dedicated vs. Cloud GPU

| Aspect | Dedicated GPU | Cloud GPU |
|---|---|---|
| Physical isolation | Full — single-tenant host | Virtualized — shared physical host |
| Performance consistency | Highest — no virtualization overhead | High — slight overhead from hypervisor |
| Best for | Steady, sustained production workloads | Flexible or variable workloads |
| Price | Lower of the two | Slightly higher |

---

## Key Features

| Feature | Details |
|---|---|
| **GPU** | NVIDIA L40S (48 GB), H100 (94 GB), or H200 (141 GB VRAM) |
| **CUDA** | Full NVIDIA CUDA stack — supports PyTorch, TensorFlow, JAX, RAPIDS |
| **vCPUs** | 32 vCPUs per instance on all plans |
| **System RAM** | 106 GB (L40S, H100) or 213.3 GB (H200) |
| **NVMe storage** | 1.75 TB (L40S, H100) or 3.84 TB (H200) — fast local disk minimizes GPU idle time |
| **Bandwidth** | 15 TB outbound per month per instance |
| **Root access** | Full root/administrator access — install any framework, driver, or toolchain |
| **Provisioning** | Instances provisioned in minutes |
| **IP addresses** | Dedicated IPv4 + IPv6 per instance |
| **DDoS protection** | Always-on, network-level, automatic — no extra cost |
| **Security** | RBAC access controls; strict data security procedures |

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

## Software & Frameworks

Customers install their preferred ML/AI stack via root access. Commonly used:

- **PyTorch** — primary framework for most LLM and diffusion model training
- **TensorFlow / Keras** — widely used for classification and production inference
- **JAX** — Google-developed, popular for research and TPU-compatible workloads
- **Hugging Face Transformers** — model hub and inference library
- **vLLM / TGI** — high-throughput LLM inference servers
- **AUTOMATIC1111 / ComfyUI** — Stable Diffusion frontends
- **NVIDIA CUDA Toolkit** — available for all instances

---

## Management & DevOps

- **Customer Control Panel** (my.contabo.com): start/stop/restart, reinstall, VNC console, DNS management
- **Contabo API**: RESTful; covers provisioning, networking, and basic instance management
- **CLI (`cntb`)**: Command-line mirror of the API
- **cloud-init**: Automated provisioning with user-data scripts at boot
- **SSH keys**: Inject at deployment time via Control Panel or API
- **Custom images**: Upload and deploy custom OS or ML-ready images

---

## Availability & Locations

GPU Cloud instances are primarily available across **three US data center locations** for low cross-continental latency. Additional global locations may be available — check the Contabo website for current availability.

---

## Billing Terms

| Term | Details |
|---|---|
| Minimum initial contract | 1 month |
| Following contracts | Equal to initial term |
| Billing model | Flat monthly rate — no per-hour billing |
| Annual discount | Available |
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

Contabo provides **unmanaged hosting**. Support covers network, hardware, and initial setup. GPU driver installation, framework configuration, model deployment, and application-level troubleshooting are the customer's responsibility.

---

## Limitations & Notes

- GPU Cloud instances are priced at a flat monthly rate — unlike hyperscaler GPU clouds (AWS, GCP, Azure) that bill per second or per hour. This makes Contabo GPU Cloud better suited to sustained workloads than sporadic short jobs.
- For irregular or short-burst GPU workloads, per-hour providers (RunPod, vast.ai) may offer lower total cost.
- VRAM is the primary sizing constraint for LLM workloads: a 70B parameter model in FP16 requires ~140 GB VRAM — matching the H200's 141 GB configuration.
- Multi-GPU configurations are not listed in the standard plans; contact Contabo for custom multi-GPU setups.
- Windows Server incurs an additional monthly license fee.

---

*Prices listed in EUR, excluding VAT. Specifications subject to change — verify current details at contabo.com.*
