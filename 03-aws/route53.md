# AWS Route 53 Configuration — CloudArmor.dev (v1)

This document defines the authoritative DNS configuration
for CloudArmor.dev.

---

## Hosted Zone

- Public hosted zone: cloudarmor.dev
- Route 53 is the sole DNS authority

Registrar name servers must match Route 53.

---

## Records

### Apex Records

- A (Alias) → CloudFront distribution
- AAAA (Alias) → CloudFront distribution

---

### WWW Records

- www A (Alias) → CloudFront distribution
- www AAAA (Alias) → CloudFront distribution

---

## DNS Principles

- No CNAMEs at apex
- No registrar-level forwarding
- No Squarespace-managed DNS

---

## Validation

- dig cloudarmor.dev
- dig www.cloudarmor.dev
- Confirm alias targets CloudFront

---

## Operating Principle

DNS is infrastructure.
Changes must be intentional and documented.

