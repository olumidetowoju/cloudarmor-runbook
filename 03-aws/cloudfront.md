# AWS CloudFront Configuration — CloudArmor.dev (v1)

This document defines the canonical CloudFront configuration
used to front Squarespace for CloudArmor.dev.

---

## Region Requirement

All TLS certificates for CloudFront must be issued in:

us-east-1

---

## Distribution Overview

**Origin**
- Type: Custom origin
- Origin domain: Squarespace-provided origin
- Origin protocol policy: HTTPS only
- Minimum TLS version: TLSv1.2

---

## Default Behavior

- Viewer protocol policy: Redirect HTTP to HTTPS
- Allowed methods: GET, HEAD
- Cache policy: Managed-CachingOptimized
- Compression: Enabled

---

## Alternate Domain Names (CNAMEs)

- cloudarmor.dev
- www.cloudarmor.dev

---

## TLS Certificate

- AWS Certificate Manager (ACM)
- Region: us-east-1
- Covers apex and www domains

Squarespace-managed certificates are not used.

---

## Security Headers (Baseline)

Applied via CloudFront Response Headers Policy:

- Strict-Transport-Security  
  max-age=31536000; includeSubDomains; preload

- X-Frame-Options  
  DENY

- X-Content-Type-Options  
  nosniff

- Referrer-Policy  
  strict-origin-when-cross-origin

---

## Content-Security-Policy

- Mode: Report-Only initially
- Tighten after observing violations

---

## Canonical Domain Strategy

- Primary domain: www.cloudarmor.dev
- Redirect apex → www

Registrar-level forwarding is not used.

---

## Explicitly Not Enabled (v1)

- AWS WAF
- Lambda@Edge
- Geo restrictions
- Bot mitigation

Controls are added only when justified.

---

## Validation Checklist

- HTTPS loads correctly
- HTTP redirects to HTTPS
- Certificate valid
- Squarespace editor functional
- Mobile rendering intact

---

## Operating Principle

Edge controls must remain operable.
Unmaintainable security is technical debt.

