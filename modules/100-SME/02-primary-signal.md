---
case: Meridian
date: 2026-10-24
---

# 02 — Primary Signal

## Limitations (read before using this file)

- All three verbatims are drawn from institutional/analyst public sources,
  not from user support calls, app-store reviews, or earnings-call
  frustration threads. Institutional language carries optimism bias and
  understates operational pain. Each quote is labeled accordingly.
- The competitor teardown is desk-based (documented public flows and
  published UX documentation). It is not a live timed walkthrough. Gaps
  identified for Meridian are inferred from public evidence, not observed
  firsthand.
- Three Zalando product names (Zalando Plus, Fashion Assistant,
  Sustainability Filter) appear in the teardown. None is cited to a
  retained source. All three are marked unverified.
- All three verbatim URLs were carried forward from 01-context-brief.md,
  which was itself produced by an AI research pass. No URL was opened
  and checked against the page to confirm the quoted sentence appears
  word for word. All three quotes and their URLs are marked unverified
  against source. They satisfy the kata's named-source requirement in
  form only; they do not satisfy it in substance until a human checks
  each URL and confirms the sentence.

---

## Part 1 — Three Verbatims

**V1**
> "Retailers operating across multiple European markets face the dual
> challenge of capturing growth in high-velocity regions like Southern
> and Eastern Europe while managing the cost structures built for slower
> Western European markets."

Source: EuroCommerce / Ecommerce Europe, *European e-commerce reaches
€911 billion as sector calls for fairer competition*, 22 September 2026.
URL (unverified — not checked against page):
https://www.eurocommerce.eu/2026/09/european-e-commerce-reaches-e911-billion-as-sector-calls-for-fairer-competition/
Limitation: institutional report language; describes structural pressure,
not a named retailer's operational pain. Quote not confirmed word for
word at source URL.

---

**V2**
> "Fragmented technology stacks are the single biggest barrier preventing
> European retailers from deploying AI at the speed their competitors in
> the US and China already operate at."

Source: McKinsey & Company / EuroCommerce, *Rewiring retail in Europe:
The AI imperative*, 10 June 2026.
URL (unverified — not checked against page):
https://www.mckinsey.com/industries/retail/our-insights/rewiring-retail-in-europe-the-ai-imperative
Limitation: analyst assertion, not a retailer quote; no named company
or measured lag time cited in the source. Quote not confirmed word for
word at source URL.

---

**V3**
> "From 27 September 2026, traders must provide consumers with clear,
> accurate and comparable information on product durability, reparability
> and environmental claims — consistently across all sales channels."

Source: European Commission, *Questions & Answers — Directive on
empowering consumers for the Green Transition*, 22 September 2026.
URL (unverified — link points to general topic page, not the specific
Q&A document; quote not confirmed word for word at source):
https://commission.europa.eu/topics/consumers/consumer-rights-and-complaints/sustainable-consumption_en
Limitation: regulatory text confirms the obligation is live; it does
not confirm the operational difficulty of meeting it across 22 sites.
Quote not confirmed word for word at source URL.

---

## Part 2 — Competitor Teardown: Zalando

**Scope:** Zalando Partner Program and consumer-facing platform, EU
multi-market operation. Desk-based analysis of public UX flows, Partner
Program documentation, and published platform architecture. Not a live
timed walkthrough. Gaps identified for Meridian are inferences,
not observations.

| Area | Status | Finding |
|---|---|---|
| Unified cross-market identity | **Solved** | Single Zalando account works across all EU country storefronts; loyalty programme portable across markets (product name unverified — no retained source) |
| AI-driven personalization | **Solved** | Cross-market personalization, recommendations and size tooling operate from a single product data layer (product names unverified — no retained source) |
| Per-market regulatory compliance (ECGT / Directive 2024/825) | **Partial** | Zalando surfaces sustainability labels but label consistency across partner-supplied product data is uneven; partners self-certify (feature name unverified — no retained source) |
| Multi-category platform (home goods, electronics) | **Unsolved** | Zalando is fashion and lifestyle only; no architecture for Meridian's full category mix |
| Headless / composable commerce for 1,400 POS | **Unsolved** | Zalando operates no physical POS estate; no reference model for unified in-store and digital identity at Meridian's scale |

Gap that matters for Meridian: Zalando has solved cross-market identity
and AI reuse within a single category and with no physical store estate.
The unsolved gap — multi-category unification across 1,400 POS systems —
is precisely Meridian's problem and has no Zalando equivalent.

---

## Part 3 — Pain Point Re-ratings

**Pain 1: Margin-safe localization [M]**
Rating: SHARPENED (nearest available; no independent primary signal —
"nearest available" is author's reading of the scheme, not kata-stated;
treat as unvalidated until a source outside EuroCommerce corroborates
the cost-structure claim)
V1 adds the framing that cost structures are calibrated to slower Western
European markets, which the brief did not state explicitly. However, V1
and [M] Market Trend 2 share the same EuroCommerce source family; V1
introduces no new fact, no measured magnitude, and no user voice. The
11–14% figures that do the sharpening work were already in the brief
before primary signal was collected ([M] Market Trend 2). V1 quote is
unverified against source URL.
Moving evidence: none independent of the brief.
Action needed: a practitioner verbatim or named retailer cost disclosure;
URL verification of V1 before treating quote as confirmed.

---

**Pain 2: AI speed versus architecture drag [C]**
Rating: SHARPENED (nearest available; no independent primary signal —
"nearest available" is author's reading of the scheme, not kata-stated;
treat as unvalidated until a named retailer or practitioner source
corroborates the lag claim)
V2 restates the fragmentation-as-AI-barrier claim from the same
McKinsey/EuroCommerce source family already in the brief. The Zalando
teardown is desk-based; the gap it identifies for Meridian is an
inference, not an observation. Neither piece independently moves the
pain beyond what the brief already contained. V2 quote is unverified
against source URL.
Moving evidence: none independent of the brief.
Action needed: a named retailer disclosure or practitioner quote
measuring AI deployment lag attributable to stack fragmentation;
URL verification of V2 before treating quote as confirmed.

---

**Pain 3: Consumer compliance at scale [R]**
Rating: SHARPENED (nearest available; V3 is independent of the brief's
source family and confirms the regulatory trigger, but confirms the
obligation, not the operational pain — "nearest available" is author's
reading of the scheme, not kata-stated; marginally stronger than Pains
1 and 2 because V3 is a genuinely independent source, but the
operational difficulty across 22 sites remains unconfirmed by any
user voice or practitioner disclosure)
The operative instrument is Directive (EU) 2024/825 — the Directive on
empowering consumers for the Green Transition (ECGT) — which amends the
Consumer Rights Directive 2011/83/EU. "CRD" used elsewhere in this file
is shorthand for that amending relationship; the September 2026
obligations flow from the ECGT, not the original CRD alone. V3
independently confirms the ECGT obligation is live as of 27 September
2026 and applies across all sales channels. However, V3 backs the
existence of the obligation, not the difficulty of meeting it across
Meridian's 22 fragmented sites. The Zalando teardown shows ECGT
compliance is partial even for a best-in-class EU platform, but the
inference that Meridian's fragmented estate makes this harder is
desk-based and not observed. The same discount applied to the teardown
in Pain 2 applies here. V3 quote is unverified against source URL;
the URL cited points to a general topic page, not the specific Q&A
document, and must be corrected before the quote can be treated as
confirmed.
Moving evidence: V3 (obligation confirmed, independent source, quote
unverified) + Zalando teardown (Partial: ECGT compliance —
desk-based inference only).
Action needed: locate and verify the specific Q&A document URL; obtain
a practitioner quote on the per-site ECGT compliance cost.

---

## Signal health check

Pain 1 (localization): SHARPENED — same-source echo, no independent
signal. Weakest in the file.
Pain 2 (AI drag): SHARPENED — same-source echo plus desk-based
inference. Equivalent weakness to Pain 1.
Pain 3 (compliance): SHARPENED — strongest in the file; V3 is an
independent source confirming the regulatory trigger, but the
operational pain across 22 sites has no user voice behind it.

All three pains are rated SHARPENED. No pain reached CONFIRMED under
consistent evidential standards. All three source URLs are unverified
against their pages. The entire signal layer requires both URL
verification and practitioner-sourced verbatims before the audit kata
should treat any pain as field-validated. This is the correct finding
to carry forward: the artefact accurately reflects what AI-assisted
institutional sources can and cannot establish.