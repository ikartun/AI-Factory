---
case: Meridian
date: 2026-11-04
---

# 07 — Executive Deck
## UC-07/10 — ECGT Compliance Gap Detector

---

## S1 — Context

**Meridian at a glance**

Meridian operates 1,400 stores across 22 countries.
Revenue USD 8.2B. Digital channel 31%, growing 18% YoY.
Directive (EU) 2024/825 in application since 27 September
2026.

*Word count: 25*

**Speaker note:**
ECGT is already live — this deck is about acting now
versus waiting for enforcement.

---

## S2 — Problem

**What catalogue managers face today**

Catalogue managers cannot identify which SKUs are missing
or inconsistent ECGT claims across web, app, and in-store
— and cannot manually review the full catalogue.

*Word count: 24*

**Speaker note:**
We have no tool to find compliance gaps at scale; manual
review of 22 markets is not feasible.

---

## S3 — Opportunity

**The gap we can close**

A classifier that detects ECGT compliance gaps across
22 markets, prioritised by revenue, before enforcement
actions accumulate.

*Word count: 17*

**Speaker note:**
One classifier, 22 markets, highest-revenue gaps first
— targeted, not a platform rebuild.

---

## S4 — Solution

**How it works**

Multi-label classifier scans the catalogue, flags missing
or inconsistent durability, reparability, and environmental
claims, and surfaces a revenue-prioritised remediation
queue.

*Word count: 20*

**Speaker note:**
The classifier finds and ranks gaps; managers action
them; human sign-off stays in the loop.

---

## S5 — Value

**What success looks like**

Reduces live non-compliant SKUs by ~56% if A2 (70%
detectable) and A3 (80% actioned) hold. Magnitude
confirmed by catalogue audit. Assumption, not sourced.

*Word count: 23*

**Speaker note:**
56% is 70% detectable times 80% actioned — the catalogue
audit turns this assumption into a real number.

---

## S6 — ROI

**The numbers**

Base: ~+USD 1.24M Year 1 net (ramp-adjusted: value from
month 7 per S9, assumption). Pessimistic: no payback.
Payback roughly within Year 1 (assumption). Build cost
USD 350K–1,200K. All figures UNVERIFIED.

*Word count: 30*

**Speaker note:**
Base net is ~+USD 1.24M after ramp; if enforcement never
happens, it never pays back.

---

## S7 — Risks

**The binding gate**

Binding gate: legal opinion on ECGT enforcement scale.
Without it, V1 and V4 are zero and the use case never
pays back.

*Word count: 22*

**Speaker note:**
Every other risk is manageable; this one is binary —
enforcement happens or it doesn't.

---

## S8 — Ask

**What we need to proceed**

~USD 50K discovery budget (assumption, unverified —
vendor quotes needed): catalogue data audit (A1), data
readiness assessment (A2), EU regulatory counsel
opinion (V1).

*Word count: 22*

**Speaker note:**
USD 50K is an assumption from three components; we are
asking to get quotes, not to build.

---

## S9 — Timeline

**Indicative schedule**

Month 1–2: catalogue audit and legal opinion. Month 3:
data readiness assessment. Month 4–6: build. Month 7:
first output to catalogue managers. Assumption, not
scheduled.

*Word count: 25*

**Speaker note:**
Discovery stops at month 2 if the legal opinion shows
low risk; the build timeline needs vendor quotes.

---

## S10 — Next Steps

**Three actions this week**

Commission legal opinion. Initiate catalogue audit.
Assign catalogue data owner. No build commitment until
all three UNVERIFIED flags are resolved.

*Word count: 20*

**Speaker note:**
Three actions this week: legal opinion, catalogue audit,
name a data owner — no build commitment yet.

---

## Deck provenance note

Sourced figures in this deck:
- ECGT application date 27 September 2026 (B6/B7,
  EUR-Lex, confirmed by human check)
- Meridian revenue USD 8.2B, digital share 31%, growth
  18% YoY (case definition, modules/001-reference-cases.md)

All other figures are UNVERIFIED assumptions, including:
- ~+USD 1.24M Year 1 net (S6) — ramp-adjusted assumption;
  06-roi.md retains unadjusted +USD 3.3M figure
- ~USD 50K discovery budget (S8) — assumption; three-
  component derivation: counsel ~USD 15–20K, audit
  ~USD 15–20K, data readiness ~USD 10–15K; vendor
  quotes needed
- USD 350K–1,200K build cost (S6) — UNVERIFIED
- ~56% SKU clearance rate (S5) — assumption arithmetic
- All ROI figures — see 06-roi.md for full flag table

No figure should be presented externally without
completing the discovery actions on S10 and obtaining
the legal opinion named on S7.