---
case: Meridian
date: 2026-10-24
---

# 03 — Research Audit

## Survival count

18 claims in → 18 survived, 0 cut
4 SOURCED (3 fully confirmed, 1 with caveat — see P3),
14 UNVERIFIED (11 plain, 1 priority-flagged,
1 superlative-flagged, 1 assumption-labeled), 0 CUT

---

## K 1.W.5 inheritance rules

The following claims must not be used in use cases, canvases,
or ROI models as if they were sourced. They are UNVERIFIED and
carry specific flags:

- B5 (Tesco): do not cite as competitive evidence until footnote
  29 is confirmed in the McKinsey/EuroCommerce report
- P2 ("single biggest barrier"): do not use the superlative in
  any exec-facing artefact until the sentence is confirmed word
  for word at the [C] URL
- P4, P5 (Zalando identity and AI layer): do not cite as
  architectural evidence; desk-based claims with no retained
  source
- P6 (Zalando ECGT partial): do not cite as competitive
  corroboration for Pain 3; desk-based with no retained source

Sourced claims cleared for K 1.W.5 use: B6, B7, B9, P3
(P3 with caveat — see trust ledger)

---

## Blocker — partial URL verification

[M] EuroCommerce and [C] McKinsey/EuroCommerce URLs require
registration. No sentence from either source has been confirmed
word for word at its cited page. Claims drawing on [M] and [C]
are cleared for internal drafts only, not exec review.

[R] European Commission — Directive (EU) 2024/825 confirmed by
human check at EUR-Lex:
https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024L0825
Transposition deadline 27 March 2026: confirmed.
Application date 27 September 2026: confirmed.
"Across all sales channels" scope: not searched in directive
text; sourced from V3 (Commission Q&A, URL unconfirmed) — see
P3 caveat below.

---

## Trust ledger

| ID | Claim | Tag | Reason |
|---|---|---|---|
| B1 | EU B2C e-commerce reached €911B in 2025 (+7%); forecast 5% growth in 2026 | UNVERIFIED | [M] URL requires registration; figure not confirmed at source page |
| B2 | Western Europe +5%, Southern Europe +11%, Eastern Europe +14% | UNVERIFIED | Same [M] URL; not confirmed at source page |
| B3 | Zalando expanding AI personalization, recommendations, sizing, fulfillment | UNVERIFIED | [C] URL requires registration; directionally plausible but not confirmed |
| B4 | John Lewis investing in AI-enabled shopping and AI-discoverable catalog | UNVERIFIED | Same [C] URL; not confirmed at source page |
| B5 | Tesco trialed in-app generative-AI assistant with ~280,000 employees, footnote 29, "Wave 2: AI-orchestrated commerce", Tesco announcement 9 Apr 2026 | UNVERIFIED — priority verification flag | Paywall blocks confirmation; false-precision pattern (internal footnote number + section name + employee count + specific announcement date) makes this highest-risk claim in file; verify before any other [C] claim; if footnote 29 absent when report is opened, cut immediately |
| B6 | ECGT (Directive 2024/825) transposition deadline 27 March 2026 | SOURCED | Confirmed by human check at EUR-Lex: https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024L0825 |
| B7 | ECGT application date 27 September 2026 | SOURCED | Confirmed by human check at same EUR-Lex URL |
| B8 | GDPR requires per-market consent architecture for unified identity systems | UNVERIFIED | No specific citation beyond general [R] label; per-market consent framing is an inference, not a cited claim |
| B9 | Meridian digital channel 31% of revenue, growing 18% YoY | SOURCED | Sourced directly to case definition (modules/001-reference-cases.md); authoritative input document |
| B10 | USD 2–4M per-market platform duplication cost | UNVERIFIED — assumption (labeled) | No external source; case assumption only; never to be promoted to sourced |
| P1 | Cost structures built for slower Western European markets create a dual-market challenge (V1 quote) | UNVERIFIED | [M] URL requires registration; sentence not confirmed word for word at source |
| P2 | Fragmented stacks are "the single biggest barrier" to AI deployment speed vs US/China (V2 quote) | UNVERIFIED — superlative flagged | [C] URL requires registration; "single biggest" may be AI intensification of hedged original; sentence not confirmed word for word; do not use superlative in exec-facing artefact |
| P3 | ECGT obligations live from 27 Sep 2026 across all sales channels (V3 quote) | SOURCED — caveat on channel scope | Dates confirmed at EUR-Lex; "across all sales channels" sourced from V3 (Commission Q&A) whose URL was not confirmed word for word; channel-scope claim is consistent with directive purpose but specific clause not located in directive text; do not cite channel scope as confirmed until EUR-Lex clause is found |
| P4 | Zalando unified cross-market identity and loyalty portability — Solved | UNVERIFIED | Desk-based; no retained source; product name unverified |
| P5 | Zalando AI personalization from single product data layer — Solved | UNVERIFIED | Desk-based; architectural claim not confirmed from retained source |
| P6 | Zalando ECGT compliance partial; partners self-certify — Partial | UNVERIFIED | Desk-based; no retained source |
| P7 | Zalando no multi-category architecture for home goods or electronics — Unsolved | UNVERIFIED | Desk-based; directionally accurate but not confirmed from retained source |
| P8 | Zalando no physical POS estate — Unsolved | UNVERIFIED | Desk-based; publicly known but not confirmed from retained source |

---

## Propagated cuts

None. No claim has been cut. B5 (Tesco) carries a priority
verification flag but remains UNVERIFIED until the report is
opened and footnote 29 is checked. Do not inherit B5 into any
exec-facing artefact until verified.

---

## Triangulation check

Market domain (B1–B2, P1): EuroCommerce [M] only — unverified
Competitive domain (B3–B5, P2): McKinsey/EuroCommerce [C] only —
unverified
Regulatory domain (B6–B7, P3): EUR-Lex confirmed — sourced
(P3 channel-scope caveat applies)

Regulatory domain is the only domain with independent
confirmation. Market and competitive domains have no
corroboration from a second source.

---

## Adversarial pass findings

- B5 (Tesco): UNVERIFIED, priority flag — false-precision
  pattern; highest-risk claim in file; verify footnote 29 first
- P2 (superlative): UNVERIFIED — "single biggest barrier" is the
  kind of intensifier AI models add to hedged analyst language;
  do not use in exec deck until sentence confirmed word for word
- B8 (GDPR per-market consent): UNVERIFIED — inference presented
  as cited claim; needs a specific GDPR article or guidance
  document to become sourced
- P3 (channel scope): SOURCED with caveat — dates confirmed;
  "across all sales channels" not located as a specific clause
  in directive text; log as open verification item

---

## Dependent section — Pain ratings

Pain ratings are derived from ledger claims above. They are not
independent claims and are not counted in the survival total.

**Pain 1 — Margin-safe localization**
Depends on: B2 (regional growth figures) + P1 (V1 framing)
Both UNVERIFIED, same [M] source family
→ If [M] confirmed: rating stands as SHARPENED with existing flag
→ If [M] 404s or sentence absent: no primary signal; rating
  withdrawn

**Pain 2 — AI speed vs architecture drag**
Depends on: P2 (V2 quote) only
P4 and P5 (Zalando AI) are desk-based and cannot substitute
→ If P2 confirmed: rating stands as SHARPENED with superlative
  flag
→ If P2 cut: no primary signal; rating withdrawn

**Pain 3 — Consumer compliance at scale**
Depends on: P3 (V3 quote) — SOURCED with channel-scope caveat
P6 (Zalando partial) remains desk-based
→ Dates confirmed via EUR-Lex: Pain 3 rating stands as SHARPENED
→ Channel-scope claim carries caveat; do not cite "across all
  sales channels" as confirmed until specific clause located
→ Operational difficulty across 22 sites remains unconfirmed
  by any user voice

---

## Weakest kept claim

**P2 — "Fragmented stacks are the single biggest barrier to AI
deployment speed in EU retail."**

Kept because: removing it leaves Pain 2 with no verbatim and no
primary signal; directional claim is consistent with B3 and the
structural logic of the engagement.

Kept despite: URL requires registration; "single biggest" is an
unconfirmed superlative; no named company or measured lag time;
most likely claim to be challenged in an exec setting.

CONFIRM BEFORE EXEC REVIEW.
If the McKinsey/EuroCommerce report is opened and the sentence
does not appear word for word, P2 must be cut and Pain 2 rating
withdrawn.

---

## Audit summary

4 SOURCED: B6, B7, B9, P3 (P3 with channel-scope caveat)
11 UNVERIFIED (plain): B1, B2, B3, B4, B8, P1, P4, P5, P6,
  P7, P8
1 UNVERIFIED — priority verification flag: B5
1 UNVERIFIED — superlative flagged: P2
1 UNVERIFIED — assumption labeled: B10
0 CUT
18 claims total