# CloudArmor Runbook

This repository is the **canonical operational runbook** for  
**cloudarmor.dev**.

It documents the design decisions, build steps, deployment procedures,
and operational practices used to run the CloudArmor website using
**Squarespace + AWS**.

This is a documentation and governance repository — **not** a source
code repository.

---

## What This Repository Is

- A step-by-step runbook for building and operating cloudarmor.dev
- A system of record for architectural and deployment decisions
- Documentation for Squarespace page construction
- AWS edge, DNS, and TLS configuration reference
- QA, troubleshooting, and change tracking

---

## What This Repository Is Not

- The website source code
- A CI/CD pipeline
- A static-site or frontend framework
- A marketing content repository

Website content lives in **Squarespace**.  
Infrastructure control lives in **AWS**.

---

## Canonical Stack

- **Squarespace** — Content management and page layout
- **AWS Route 53** — Authoritative DNS
- **AWS ACM (us-east-1)** — TLS certificates
- **AWS CloudFront** — CDN, HTTPS enforcement, security headers
- **GitHub** — Runbook version control

---

## Repository Structure

cloudarmor-runbook/
├── 00-overview/ # Mission, positioning, sitemap
├── 01-design-system/ # Visual and UX rules
├── 02-squarespace/ # Page-by-page build instructions
├── 03-aws/ # DNS, TLS, CloudFront configuration
├── 04-qa-and-go-live/ # Validation, troubleshooting, checklists
├── 05-changelog/ # Change history
└── evidence/ # Screenshots and exports

yaml
Copy code

---

## Core Principles

- Production environments only
- Consulting + engineering hybrid
- Clear scope, no pricing theatrics
- Minimal tooling, maximal clarity
- Changes are documented before being applied

If the site grows beyond this structure, focus has been lost.

---

## How to Use This Runbook

1. Start with `00-overview/` to understand intent and structure
2. Follow `02-squarespace/` for page construction
3. Use `03-aws/` for DNS, TLS, and CloudFront setup
4. Validate with `04-qa-and-go-live/`
5. Record all material changes in `05-changelog/`

---

## Change Management

- Documentation changes are committed first
- Infrastructure changes follow documented steps
- Historical entries are never deleted
- This runbook is a living document

---

## Status

Active  
Versioned  
Authoritative

