# AWS ACM Certificate — CloudArmor.dev (v1)

This document defines TLS certificate issuance
for CloudArmor.dev.

---

## Region Requirement

Certificates for CloudFront must be issued in:

us-east-1

---

## Certificate Scope

- cloudarmor.dev
- www.cloudarmor.dev

---

## Validation Method

- DNS validation
- CNAME records added to Route 53
- Automatic renewal enabled

---

## Restrictions

- No email validation
- No Squarespace-managed certificates

---

## Validation Checklist

- Certificate status: Issued
- Domains validated
- Attached to CloudFront distribution

---

## Operating Principle

TLS is non-negotiable.
Certificate ownership remains in AWS.

