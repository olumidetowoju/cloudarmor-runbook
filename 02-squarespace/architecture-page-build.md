# Architecture Page Build — Squarespace (v1)

This document defines the structure and copy for the Architecture page.
This page is the authority anchor of CloudArmor.dev.

Tone: Calm, opinionated, engineering-first  
Theme: Light  
Audience: Engineers, CTOs, CISOs

---

## Section 1 — Introduction

**Headline (H1)**
Architecture before tools. Design before controls.

**Body**
CloudArmor architectures are designed for production environments.
We assume compromise is possible, credentials will leak, and systems will fail.

The goal is not to prevent every incident.
The goal is to limit impact, preserve trust, and maintain control.

---

## Section 2 — Core Design Assumptions

**Headline (H2)**
Our architectures start with these assumptions:

**List**
- Identity is the primary security perimeter
- No network is inherently trusted
- Human and non-human identities must be isolated
- Public exposure is a deliberate exception
- Failures must be survivable
- Security controls must remain operable

---

## Section 3 — Identity-First Perimeter

**Headline (H2)**
Identity is the real boundary.

**Body**
Authentication and authorization occur before network access.
Access paths are explicit, least-privileged, and documented.

**Callout**
If identity is compromised, the blast radius must still be small.

---

## Section 4 — Network Containment

**Headline (H2)**
Networks exist to limit damage, not to create trust.

**Body**
Networks are used to reduce lateral movement, isolate workloads,
and control ingress and egress intentionally.

---

## Section 5 — Control Plane vs Data Plane

**Headline (H2)**
Separate what manages from what runs.

**Body**
Control planes and data planes are isolated to reduce escalation,
privilege sprawl, and operational risk.

---

## Section 6 — Runtime and Operations

**Headline (H2)**
Security that works after deployment.

**Body**
Architecture extends into logging, visibility, alerting,
and ownership by real teams.

Unmaintainable controls are technical debt.

---

## Section 7 — Failure and Resilience

**Headline (H2)**
Design for failure, not perfection.

**Body**
Architectures must expect mistakes, outages, and compromise.
Resilience is designed, not retrofitted.

---

## Section 8 — What We Intentionally Avoid

**Headline (H2)**
What we deliberately avoid.

**List**
- Flat networks
- Implicit trust
- Long-lived credentials
- Over-engineered tooling
- Security theater

---

## Section 9 — Closing CTA

**Headline (H2)**
Architecture should reduce risk, not add complexity.

**Button**
Contact Us

