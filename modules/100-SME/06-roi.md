---
case: Meridian
date: 2026-11-04
---

# 06 — ROI Sketch

## Use case: UC-07/10 — ECGT Compliance Gap Detector
Source: 05-canvas.md

## Provenance rule
Every figure carries a source label or UNVERIFIED flag.
UNVERIFIED = confirm before exec review.
SOURCED = confirmed at named document.

---

## Cost and value drivers

| Line | Driver | Pessimistic | Base | Optimistic | Source |
|---|---|---|---|---|---|
| C1 | Build cost (one-time) | USD 1,200K | USD 700K | USD 350K | UNVERIFIED — retail ML classifier build range; no named benchmark confirmed |
| C2 | Run cost — annual | USD 250K | USD 150K | USD 80K | UNVERIFIED — cloud inference estimate; AWS/Azure pricing not checked |
| C3 | Change management (one-time) | USD 400K | USD 200K | USD 100K | UNVERIFIED — Prosci benchmarks exist but not opened |
| C4 | Data readiness (one-time, conditional) | USD 600K | USD 0 | USD 0 | UNVERIFIED — triggered only if A2 fails; zero in base/optimistic assumes A2 holds |
| C5 | Monitoring — annual | USD 120K | USD 70K | USD 40K | UNVERIFIED — MLOps cost benchmarks not confirmed at source |
| V1 | Regulatory penalty avoided — annual | USD 0 | USD 2,000K | USD 5,000K | UNVERIFIED — pessimistic sets to zero: enforcement by national authorities may not occur; ECGT penalty scale not established; GDPR 4% turnover cap used as ceiling reference only (SOURCED: GDPR Article 83); GDPR cap does not apply to ECGT |
| V2 | Manual review cost saved — annual | USD 60K | USD 120K | USD 200K | UNVERIFIED — FTE count, salary, and time allocation are assumptions; no Meridian staffing data in research base |
| V3 | Reactive remediation avoided (one-time) | USD 200K | USD 300K | USD 400K | UNVERIFIED — 2–3× planned remediation multiplier is consulting rule of thumb, not named benchmark |
| V4 | Revenue protected — annual | USD 0 | USD 2,000K | USD 5,000K | UNVERIFIED — pessimistic sets to zero: delisting risk depends on enforcement occurring; rests on A1 (assumption) and 0.1–1% protection rate with no benchmark; digital revenue base SOURCED (B9, case definition) |

---

## Scenario totals

| Row | Pessimistic | Base | Optimistic |
|---|---|---|---|
| Year 1 total cost | USD 2,570K | USD 1,120K | USD 570K |
| Year 1 total value | USD 260K | USD 4,420K | USD 10,600K |
| Year 1 net | −USD 2,310K | +USD 3,300K | +USD 10,030K |
| Annual run cost (Y2+) | USD 370K | USD 220K | USD 120K |
| Annual value (Y2+) | USD 60K | USD 4,120K | USD 10,200K |
| Annual net (Y2+) | −USD 310K | +USD 3,900K | +USD 10,080K |
| **Payback period** | **No payback** | **~3 months** | **~1 month** |

**Pessimistic payback note:** Annual run cost (USD 370K)
exceeds annual value (USD 60K, V2 only) by USD 310K every
year. The cumulative deficit grows indefinitely when V1
and V4 are zero. No payback occurs within any reasonable
horizon. This is the honest worst case: enforcement never
materialises and the use case delivers only manual review
savings, which do not cover operating costs.

**Base payback note:** ~3 months assumes value starts on
day one of the engagement. This omits build and rollout
time. A realistic ramp for a 22-market catalogue
integration is 3–6 months before first classifier output
reaches catalogue managers (UNVERIFIED — no project
schedule in research base). If value starts at month 4,
payback shifts to approximately 7 months in the base
case — still within Year 1 but materially different from
~3 months. Ramp assumption must be confirmed with the
delivery team before exec presentation.

**Zero-enforcement sensitivity check (base costs, V1=V4=0):**
Year 1 net: V2(120K) + V3(300K) − 1,120K = −USD 700K.
Year 2+ annual net: V2(120K) − run cost(220K) = −USD 100K.
Annual net is negative. No payback. Consistent with
pessimistic finding: the use case cannot pay back on
cost-saving alone in any scenario.

---

## Top two sensitivity drivers

### Driver 1 — V1: Regulatory penalty avoided
±20% move on base: USD 2M → USD 2.4M / USD 1.6M.
Year 1 net impact: ±USD 400K.
Real sensitivity is binary, not ±20%: either enforcement
occurs or it does not. If V1 = 0, the model moves from
base (+USD 3.3M Year 1) toward the zero-enforcement
sensitivity case (−USD 700K Year 1). That is a USD 4M
swing on a single unverified assumption.
Decomposition: penalty probability × penalty magnitude
per action × number of actions per year.
None of the three inputs has a sourced figure.
Flag: UNVERIFIED — confirm before exec review.

### Driver 2 — V4: Revenue protected
±20% move on base: USD 2M → USD 2.4M / USD 1.6M.
Year 1 net impact: ±USD 400K.
Pessimistic-to-optimistic range is 10× (USD 0 to USD 5M),
making this the dominant spread driver in the model.
Decomposition: non-compliant SKU share (A1, assumption) ×
revenue per non-compliant SKU × enforcement-driven
delisting probability.
None of the three inputs has a sourced figure.
Flag: UNVERIFIED — confirm before exec review.

Both top drivers are enforcement-dependent value lines.
If both are zero, annual run costs exceed annual value
in every scenario and no payback occurs. The investment
case is a regulatory risk hedge, not a cost-saving play.

---

## Honest summary

The ROI is defensible only if at least one of V1 or V4
materialises. Both are UNVERIFIED and both depend on
enforcement actions whose cadence by national authorities
is not covered in the research base (P3 caveat,
03-research-audit.md). When both are zero, annual
operating costs exceed annual savings in every scenario
and the use case never pays back.

The investment case is strongest as a regulatory risk
hedge: the one-time build cost (USD 350K–1,200K,
UNVERIFIED — C1 range) is the insurance premium against
a penalty whose scale and frequency are unknown until
Meridian's EU regulatory counsel provides an opinion —
that opinion is the single action that determines whether
the base case holds.

The single most important pre-exec action: obtain a
legal opinion from Meridian's EU regulatory counsel on
the realistic penalty range and enforcement timeline for
Directive (EU) 2024/825 non-compliance. That opinion
replaces V1's UNVERIFIED tag with a sourced range and
either confirms or collapses the base case.

---

## UNVERIFIED flags requiring confirmation before exec review

| Flag | Line | Action needed |
|---|---|---|
| Build cost range | C1 | Obtain vendor quotes or comparable project actuals |
| Run cost range | C2 | Check AWS/Azure pricing calculator for catalogue-scale inference |
| Change management range | C3 | Check Prosci or equivalent benchmark for 22-market rollout |
| Data readiness cost | C4 | Conduct A2 data readiness assessment before build commitment |
| Monitoring cost | C5 | Obtain MLOps vendor quote |
| Penalty scale | V1 | Obtain EU regulatory counsel opinion on ECGT enforcement; GDPR cap does not apply to ECGT |
| Staffing assumption | V2 | Confirm FTE count and time allocation with Meridian compliance team |
| Remediation multiplier | V3 | Confirm with Meridian procurement or legal on emergency contractor rates |
| Revenue at risk | V4 | Confirm A1 non-compliance rate via catalogue audit; obtain legal view on delisting risk |
| Ramp assumption | Payback | Confirm build and rollout timeline with delivery team; ~3 month base payback assumes day-one value, which is not realistic for a 22-market integration |