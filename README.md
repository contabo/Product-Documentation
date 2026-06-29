# Contabo Knowledge Base

Product documentation for [Contabo](https://contabo.com) cloud infrastructure — built with [Hugo Doks](https://getdoks.org) and published automatically to GitHub Pages on every push to `main`.

---

## Contents

- [Repository structure](#repository-structure)
- [Local development](#local-development)
- [How deployment works](#how-deployment-works)
- [Updating content](#updating-content)
  - [Edit an existing product page](#edit-an-existing-product-page)
  - [Add a new product page](#add-a-new-product-page)
  - [Remove a product page](#remove-a-product-page)
  - [Update site-wide metadata](#update-site-wide-metadata)
- [Document structure](#document-structure)
- [Content conventions](#content-conventions)

---

## Repository structure

```
contabo-docs/
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions — build & publish to GitHub Pages
├── assets/                     # Sass, JS, images (processed by Hugo)
├── config/
│   └── _default/
│       ├── hugo.toml           # Site config: baseURL, title, deployment target
│       ├── menus.toml          # Sidebar and top navigation
│       ├── module.toml         # Hugo module mounts
│       └── params.toml         # Doks theme parameters
├── content/
│   └── docs/
│       ├── _index.md           # Docs landing page
│       └── products/
│           ├── _index.md       # Products section index
│           ├── 01_cloud_vps.md
│           ├── 02_storage_vps.md
│           ├── 03_cloud_vds.md
│           ├── 04_dedicated_servers.md
│           ├── 05_gpu_cloud.md
│           └── 06_object_storage.md
├── static/                     # Static assets served as-is (favicon, etc.)
├── package.json
└── README.md
```

The files under `content/docs/products/` are the authoritative source for all product documentation. Everything else in the repo is theme infrastructure — you will rarely need to touch it.

---

## Local development

**Prerequisites:** Node.js ≥ 20 LTS and Hugo extended ≥ 0.120.

```bash
# Install dependencies
npm install

# Start the development server with live reload
npm run dev
```

Open `http://localhost:1313` in your browser. The page refreshes automatically whenever you save a content file.

```bash
# Build the site locally (same output as CI)
hugo --minify --gc
# Output goes to ./public/
```

---

## How deployment works

Pushing any commit to the `main` branch triggers the GitHub Actions workflow defined in `.github/workflows/hugo.yml`. No manual steps are required.

```
git push origin main
       │
       ▼
GitHub Actions runner
  1. Installs Hugo extended and Node.js
  2. Runs npm ci
  3. Runs hugo --minify --gc  →  ./public/
  4. Publishes ./public/ to the gh-pages branch
       │
       ▼
GitHub Pages serves the site at [https://contabo.github.io/contabo-docs/](https://contabo.github.io/Product-Documentation/)
```

The full workflow file is at `.github/workflows/hugo.yml`:


**Enabling GitHub Pages for the first time:**

1. Go to **Settings → Pages** in this repository.
2. Under *Source*, select **GitHub Actions**.
3. Save. The next push to `main` will publish the site.

Deployments are visible under the **Actions** tab. A green checkmark means the site is live; a red cross means the build failed — click the run for logs.

Attention: the repository has to be public in order to use Github Pages. To use Github Pages with private repositories, an Enterprise Account is required.

---

## Updating content

All product documentation lives in `content/docs/products/`. Changes follow a simple edit → commit → push cycle — GitHub Actions handles the rest.

### Edit an existing product page

Open the relevant file and edit any section. The file renders exactly as written — there is no custom shortcode or template logic involved beyond standard Markdown.

```bash
# Example: update Cloud VPS pricing
$EDITOR content/docs/products/01_cloud_vps.md

git add content/docs/products/01_cloud_vps.md
git commit -m "Update Cloud VPS pricing table — July 2026"
git push
```

The site is live with the change in approximately two minutes.

Common things to update in a product file:

| What changed | Where to edit |
|---|---|
| A plan was added, removed, or repriced | **Plans & Pricing** table |
| A new feature was added | **Key Features** table |
| A new region was added | **Availability & Locations** list |
| A new OS was added | **Supported Operating Systems** table |
| A billing term changed | **Billing Terms** table |
| A known limitation was resolved | **Limitations & Notes** list |

### Add a new product page

Along the example of a Loadbalancer page

**1. Create the file** following the naming convention `NN_product_name.md`, where `NN` is the next available two-digit number:

```bash
cp content/docs/products/01_cloud_vps.md content/docs/products/07_load_balancer.md
```

**2. Update the front matter** at the top of the new file:

```markdown
---
title: "Load Balancer"
description: "Managed L4/L7 load balancer for distributing traffic across Contabo servers."
lead: "High-availability traffic distribution — no infrastructure management required."
date: 2026-07-01
lastmod: 2026-07-01
draft: false
weight: 70
toc: true
---
```

Set `weight` to a value 10 higher than the last existing product (currently `60` for Object Storage), so the sidebar stays in the intended order.

**3. Fill in all twelve sections** of the document structure (see [Document structure](#document-structure) below).

**4. Register the page in the sidebar** by adding an entry to `config/_default/menus.toml`:

```toml
[[docs]]
  name   = "Load Balancer"
  weight = 17
  parent = "products"
  url    = "/docs/products/load-balancer/"
```

**5. Commit and push:**

```bash
git add content/docs/products/07_load_balancer.md config/_default/menus.toml
git commit -m "Add Load Balancer product documentation"
git push
```

### Remove a product page

```bash
git rm content/docs/products/07_load_balancer.md
```

Also remove the corresponding `[[docs]]` block from `config/_default/menus.toml`, then commit and push. Hugo will not build a page for a deleted file, and the sidebar entry will disappear.

### Update site-wide metadata

| What to change | File | Key |
|---|---|---|
| Site title | `config/_default/hugo.toml` | `title` |
| Site description | `config/_default/params.toml` | `description` |
| Base URL | `config/_default/hugo.toml` | `baseURL` |
| Top navigation links | `config/_default/menus.toml` | `[[main]]` entries |
| Logo or favicon | `static/` directory | Replace files directly |

---

## Document structure

Every product file uses the same twelve-section structure. This consistency means readers always know where to find a specific type of information, and contributors know exactly what to include when writing a new page.

With upcoming products, this structure might be subject to change! If the structure is changed/adapted, for consistency it should be adapted in all product documentation files.

```
# [Product Name] — Product Documentation

> metadata block (product, category, source URL, last updated date)

---

## Overview
## Ideal Use Cases
## Plans & Pricing
## Key Features
## Supported Operating Systems
## Software & App Images (1-Click)  ← omit if not applicable
## Management & DevOps
## Availability & Locations
## Billing Terms
## Support
## Limitations & Notes

---
*footer: prices, VAT note, last updated*
```

### Section-by-section guide

**Metadata block** — the blockquote directly under the `h1` title. Contains four fields on separate lines. Do not add or remove fields.

```markdown
> **Product:** Cloud VPS (Virtual Private Servers)
> **Category:** Compute
> **URL:** contabo.com/en/vps-server/
> **Source:** contabo.com | **Last updated:** June 2026
```

---

**Overview** — two to four sentences describing what the product is, how it works, and what makes it different from adjacent products. End with a callout sentence highlighting the most popular or recommended plan, if one exists. Keep it factual — no marketing language.

---

**Ideal Use Cases** — a bulleted list of concrete workloads and audiences. Each item is a short phrase, not a sentence. Aim for six to ten items.

```markdown
- Static and dynamic websites, WordPress, CMS platforms
- Web application backends and REST APIs
- Development, staging, and CI/CD environments
```

---

**Plans & Pricing** — a Markdown table with one row per plan. Required columns vary by product but always include the plan name and the monthly price in EUR formatted as `**€X.XX**`. Mark the most popular plan with a ⭐ in the name cell. Follow the table with a blockquote callout explaining any footnotes (traffic limits, discount conditions, etc.).

---

**Key Features** — a two-column Markdown table with `Feature` and `Details` as headers. Feature names in the left column are **bold**. Keep each details cell to one concise sentence or clause.

---

**Supported Operating Systems** — a two-column table with `OS` and `Cost`. Cost is either `Free` or `Additional monthly fee`. Windows Server is always paid; all Linux distributions are always free.

---

**Software & App Images (1-Click)** — a single line of tool names separated by ` · ` (middot with spaces). Mark paid tools with `*(paid)*` inline. Omit this section entirely if the product has no 1-click images.

```markdown
Docker · LAMP · Webmin (free) · Plesk *(paid)* · cPanel *(paid)*
```

---

**Management & DevOps** — a bulleted list. Each item starts with a **bold** tool or interface name followed by an em dash and a brief description of what it covers for this product. Use inline `code` formatting for CLI commands and API endpoint names.

---

**Availability & Locations** — a single sentence listing all regions, followed by a blockquote with any region-specific caveats (surcharges, availability limits, etc.).

---

**Billing Terms** — a two-column table with `Term` and `Details`. Include: minimum contract, billing cycles, annual discount, setup fee, cancellation notice, and payment model. Highlight `None` for setup fees in bold.

---

**Support** — a two-column table with `Channel` and `Availability`. Always end with a blockquote callout clarifying that Contabo provides unmanaged hosting and what that means for support scope.

---

**Limitations & Notes** — a bulleted list of known constraints, caveats, and edge cases. Each item describes something a customer might get wrong or expect to work differently. Keep these factual — do not editorialize. This section prevents support tickets.

---

**Footer line** — the final line of every file, separated by `---`. Always this exact text, with the date updated:

```markdown
*Prices listed in EUR, excluding VAT. Specifications subject to change — verify current details at contabo.com.*
```

---

## Content conventions

**Prices** — always in EUR, always formatted as `€X.XX`, always bold inside table cells (`**€4.50**`). Never include VAT. Note at the footer that VAT is excluded.

**Dates** — use `Month YYYY` format (e.g. `June 2026`). Update `lastmod` in front matter and the metadata block whenever you make a substantive change to a file.

**Tables** — use standard GFM pipe tables. Align columns with `|---|` (no explicit alignment markers needed). Keep cell content short — if a details cell runs long, rewrite it as a shorter clause.

**Footnotes in tables** — use an asterisk `*` in the cell and explain it in a blockquote immediately after the table. Do not use Markdown footnote syntax (`[^1]`).

**Product names** — use the exact official Contabo product names: Cloud VPS, Storage VPS, Cloud VDS, Dedicated Servers, GPU Cloud, Object Storage. Do not abbreviate or invent variants.

**Tone** — factual and direct. Avoid superlatives, marketing language, and vague qualifiers ("very fast", "highly available" without specifics). Use numbers and precise statements wherever possible.

**draft: false** — all published pages must have `draft: false` in their front matter. Pages with `draft: true` are built locally with `hugo server --buildDrafts` but are never included in the production build.

---

*Source data: contabo.com · Last updated: June 2026 · Prices in EUR excluding VAT*
