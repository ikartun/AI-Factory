---
case: Meridian
date: 2026-11-04
---

# 05 — Opportunity Canvas

## Use case: UC-07/10 — ECGT Compliance Gap Detector

Source: 04-use-cases.md, score 20 (value 5, feasibility 4),
Pain 3 — Consumer compliance at scale.
Regulatory grounding: Directive (EU) 2024/825, B6/B7 SOURCED
via EUR-Lex. All other claims in this canvas are inferences
or assumptions unless labeled otherwise.

---

## Problem

Catalogue managers have no automated way to identify which of
Meridian's SKUs are missing or carrying inconsistent durability,
reparability, and environmental claims across web, app, and
in-store channels — and with Directive (EU) 2024/825 in
application since 27 September 2026, every non-compliant
listing currently live represents unquantified regulatory
exposure (enforcement cadence by national authorities is not
in the research base).

---

## Users

Primary segment: catalogue and compliance managers responsible
for product data quality across Meridian's 22 markets.

Sub-segments:
- Central catalogue team: owns master product data and ECGT
  field completeness across all markets
- Per-market localisation teams: responsible for channel-
  specific listings where claim inconsistency is most likely
  to occur between web, app, and POS
- Legal/compliance function: owns regulatory exposure and
  sign-off on remediation prioritisation

---

## Value

Reduces live non-compliant SKUs in Meridian's active catalogue
by ~56% if A2 and A3 hold at threshold — magnitude to be
confirmed by A1 catalogue audit (assumption, not sourced).

Derivation note: A2 (≥70% of gaps detectable from existing
structured data) × A3 (≥80% of flags actioned within 30 days)
= 56% of non-compliant listings cleared at threshold values.
A higher clearance rate requires improving data completeness
beyond A2's 70% or raising the actioning rate above A3's 80%.
The 56% figure is assumption arithmetic, not a sourced figure.

---

## Assumptions

Three falsifiable claims. If any one fails, the use case
does not deliver its stated value without redesign.

**A1 — Non-compliance prevalence**
≥20% of Meridian's active SKUs across 22 markets are
currently missing at least one required ECGT claim field
(durability, reparability, or environmental statement).
Failure condition: if fewer than 20% are non-compliant,
the manual review cost is lower than the build cost and
the investment case does not hold.
Test: catalogue data audit on a sample of 500 SKUs across
three markets before build commitment.

**A2 — Data detectability**
≥70% of ECGT compliance gaps are detectable from structured
product attribute data already held in Meridian's catalogue
system, without requiring new data collection.
Failure condition: if fewer than 70% of gaps are detectable
from existing structured data, the classifier cannot operate
as scoped and a prior data remediation programme is required.
Test: data readiness assessment mapping ECGT required fields
against current catalogue attribute schema.

**A3 — Manager actioning rate**
Catalogue managers will action ≥80% of high-priority
classifier flags (top-velocity SKUs by revenue) within
30 days of first output.
Failure condition: if the actioning rate is below 80%,
the compliance gap persists regardless of detection quality
and the use case requires a change management intervention
before it can deliver regulatory protection.
Test: pilot with one market, measure flag-to-action rate
over 30 days before full rollout.

---

## Solution

A multi-label classifier trained on ECGT disclosure
requirements scans Meridian's product catalogue and flags
SKUs with missing or inconsistent durability, reparability,
and environmental claims across web, app, and POS channels.
Output is a prioritised remediation queue surfaced to
catalogue managers, ordered by sales velocity so the
highest-revenue regulatory exposure is addressed first.
The classifier operates on existing structured product
attribute data; it does not generate replacement claim
text (that is UC-08). Human review and sign-off remain
in the workflow before any claim is published.

---

## Open items inherited from 04-use-cases.md

- Commodity check for UC-07/10 is UNVERIFIED: Salsify and
  Syndigo root pages opened, no ECGT terms found; Akeneo
  URL unresolved. Confirm at feature/product sub-pages
  before committing to build.
- "Across all sales channels" scope of Directive 2024/825
  is inference consistent with directive purpose; specific
  clause not located in directive text (P3 caveat,
  03-research-audit.md).
- Enforcement cadence by national authorities is not in
  the research base; Problem cell reflects this explicitly.