# Troubleshooting Guide — CloudArmor.dev (v1)

This document captures common issues encountered during
setup, deployment, and operation of cloudarmor.dev.

The goal is fast diagnosis, clear root cause identification,
and repeatable resolution.

---

## DNS Issues

### Symptom
- Domain does not resolve
- `NXDOMAIN` or incorrect IP returned

### Checks
- Confirm Route 53 is authoritative
- Verify registrar name servers match Route 53
- Run:
  - dig cloudarmor.dev
  - dig www.cloudarmor.dev

### Common Causes
- Registrar still pointing to old DNS
- Missing A / AAAA alias records
- Cached DNS results

---

## TLS / Certificate Errors

### Symptom
- Browser shows certificate warning
- HTTPS fails

### Checks
- ACM certificate status = Issued
- Certificate issued in us-east-1
- Certificate attached to CloudFront

### Common Causes
- Certificate issued in wrong region
- Domain name mismatch
- Old CloudFront distribution still in use

---

## CloudFront Issues

### Symptom
- Site loads intermittently
- Old content persists
- Redirect loops

### Checks
- Origin domain correct (Squarespace)
- Viewer protocol policy = Redirect HTTP to HTTPS
- Canonical domain configuration correct

### Fixes
- Invalidate CloudFront cache
- Recheck apex → www redirect logic

---

## Squarespace Issues

### Symptom
- Site loads via Squarespace URL but not custom domain
- SSL appears disabled in Squarespace UI

### Checks
- Domain connected in Squarespace
- SSL enabled in Squarespace
- Squarespace not managing DNS

### Common Causes
- Squarespace DNS mistakenly enabled
- Partial domain connection

---

## Header / Security Issues

### Symptom
- CSP errors in browser console
- Content blocked unexpectedly

### Checks
- CSP is in Report-Only mode
- Review browser console errors
- Adjust CSP gradually

### Guidance
Never enforce CSP without observing first.

---

## General Debugging Rules

- Change one thing at a time
- Document before fixing
- Avoid registrar-level shortcuts
- Prefer AWS-native controls

---

## When to Escalate

Escalate only if:
- DNS authority is correct
- Certificate is valid
- CloudFront configuration is verified
- Issue persists after cache invalidation

