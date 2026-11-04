---
case: Meridian
date: 2026-10-24
---

# 04 — Use Cases

## Inheritance note

Claims tagged UNVERIFIED in 03-research-audit.md are not treated
as sourced here. Use cases grounded only in B6, B7 (SOURCED via
EUR-Lex) and the case definition (22-country scope, 31% digital
share, 18% YoY — sourced to modules/001-reference-cases.md).
B5 (Tesco), P2 (superlative), and unverified Zalando rows are
not cited as evidence in any use case.

---

## Blocker — open vendor checks (logged for canvas kata)

The following vendor checks were not completed before this kata
closed. No top-three candidate should be treated as confirmed
non-commodity until these are done.

| Vendor | Check needed | Status |
|---|---|---|
| Akeneo | Find correct product URL; search for ECGT, durability, reparability, 2024/825 | URL returned page-not-found — unresolved |
| Writer | Find correct product URL; search for regulatory, compliance, ECGT, EU, multilingual | URL returned page-not-found — unresolved |
| Salsify | Check feature/product sub-pages and release notes (root page opened, no ECGT found) | Root page only — incomplete |
| Syndigo | Check feature/product sub-pages and release notes (root page opened, no ECGT found) | Root page only — incomplete |
| Jasper | Check feature/product sub-pages and release notes (root page opened, no ECGT found) | Root page only — incomplete |
| Informatica | Check feature/product sub-pages and release notes (root page opened, no ECGT found) | Root page only — incomplete |
| Blue Yonder | Open product page; search for regional demand forecasting, per-market inventory segmentation, EU market localisation | Not opened |
| o9 Solutions | Same search terms as Blue Yonder | Not opened |
| Relex | Same search terms as Blue Yonder | Not opened |

Until these checks are complete, all commodity verdicts in this
file are UNVERIFIED. Weak signal toward non-commodity for
UC-07/10, UC-08, UC-09 (no ECGT found on root pages). No signal
either way for UC-01 (Blue Yonder, o9, Relex not opened).

---

## Candidate use cases — scored survivors

| ID | Use case | Pain | Type | Value (1–5) | Feasibility (1–5) | Score | Value rationale | Feasibility rationale |
|---|---|---|---|---|---|---|---|---|
| UC-01 | Demand-signal localisation model | Pain 1 | Classical-ML | 3 | 3 | 9 | Pain 1 evidence UNVERIFIED; regional growth divergence (11–14%) unconfirmed at source; markdown rate is plausible metric, not case-sourced | Requires clean per-market sales and inventory data across 22 countries; data quality likely uneven |
| UC-02 | Automated localisation content engine | Pain 1 | Generative | 3 | 4 | 12 | Reduces per-market content duplication cost; value real but secondary; Pain 1 evidence UNVERIFIED | Generative content from structured catalogue data is well-solved; CMS integration is main friction |
| UC-03 | Localisation orchestration agent | Pain 1 | Agentic | 3 | 2 | 6 | Pain 1 evidence UNVERIFIED; agent value plausible but ungrounded in sourced figures | Agentic reliability across 22 markets with heterogeneous data is high-risk; requires mature data foundation first |
| UC-04 | Unified feature store for cross-market ML | Pain 2 | Classical-ML | 3 | 2 | 6 | Pain 2 evidence UNVERIFIED; "foundational" framing is structural logic not sourced evidence; $42M budget is cost of fix, not evidence of value delivered | Circular dependency on $42M platform consolidation; cannot be built before estate is unified |
| UC-05 | Cross-market AI assistant for store operations | Pain 2 | Generative | 3 | 4 | 12 | Not tied to a sourced measurable pain; value plausible, not evidenced | Single generative endpoint across POS is technically straightforward; change management at 1,400 stores is the constraint |
| UC-06 | AI deployment pipeline agent | Pain 2 | Agentic | 3 | 2 | 6 | Pain 2 evidence UNVERIFIED; directional logic sound but no sourced figure supports the lag claim | MLOps maturity required is high; 22-market heterogeneity makes automated retraining high-risk without governance |
| UC-07/10 | ECGT compliance gap detector (missing + inconsistent claims) | Pain 3 | Classical-ML | 5 | 4 | 20 | Regulatory obligation SOURCED and live (B6, B7 via EUR-Lex); 22-country scope from case definition; non-compliance risk is inference — directive is live and Meridian operates across EU, therefore exposed | Classifier on structured product data is well-understood; main risk is catalogue data completeness across 22 markets |
| UC-08 | Automated ECGT disclosure generator | Pain 3 | Generative | 4 | 3 | 12 | ECGT obligation SOURCED (B6, B7); reduces manual effort of generating compliant text for every SKU in 22 languages; hallucination risk noted | Hallucination risk for regulatory disclosure requires human review loop; pattern established but operationally complex |
| UC-09 | Compliance monitoring agent | Pain 3 | Agentic | 4 | 3 | 12 | ECGT obligation SOURCED (B6, B7); continuous monitoring across 22 sites prevents regulatory exposure accumulating silently; 22-country scope from case definition | Agent reliability for compliance requires audit trail and human escalation; operationally complex but not novel |

**Dedup note:** UC-07 and UC-10 consolidated into UC-07/10.
Partial overlaps UC-08/UC-09 and UC-03/UC-06 kept separate
(different buyers, different operational owners).

**Forced low scores:** UC-03, UC-04, UC-06 all score 6.
UC-01 scores 9. All Pain 1 and Pain 2 use cases capped at
value 3 — unverified evidence base throughout.

---

## Top three

### 1. UC-07/10 — ECGT compliance gap detector
Score: 20 (value 5, feasibility 4)
Type: Classical-ML
Pain: Pain 3 — Consumer compliance at scale
Commodity check: UNVERIFIED — no ECGT terminology found on
Salsify or Syndigo root marketing pages; Akeneo URL returned
page-not-found. Weak signal toward non-commodity. Confirm at
feature/product sub-pages before canvas.

### 2. UC-08 — Automated ECGT disclosure generator
Score: 12 (value 4, feasibility 3)
Type: Generative
Pain: Pain 3 — Consumer compliance at scale
Commodity check: UNVERIFIED — no ECGT terminology found on
Jasper root marketing page; Writer URL returned page-not-found.
Weak signal toward non-commodity. Confirm at feature/product
sub-pages before canvas.

### 3. UC-09 — Compliance monitoring agent
Score: 12 (value 4, feasibility 3)
Type: Agentic
Pain: Pain 3 — Consumer compliance at scale
Commodity check: UNVERIFIED — Informatica root page opened,
no compliance monitoring terms found at ECGT level. Weak
signal toward non-commodity. Confirm at feature/product
sub-pages before canvas.

---

## Reserve

UC-02 — Automated localisation content engine
Score: 12 (value 3, feasibility 4) | Pain 1 — UNVERIFIED
Promoted if any top candidate confirmed commodity and no
Pain 3 candidate available.

UC-05 — Cross-market AI assistant for store operations
Score: 12 (value 3, feasibility 4) | Pain 2 — UNVERIFIED
Promoted if Pain 2 sources verified and Pain 2 candidate
needed.

UC-01 — Demand-signal localisation model
Score: 9 (value 3, feasibility 3) | Pain 1 — UNVERIFIED
Promoted only if Pain 1 sources verified and commodity check
clears Blue Yonder, o9, and Relex.

---

## Top-three pattern note

All three top candidates address Pain 3 (ECGT compliance).
Pattern diversity maintained: classifier, generator, agent.
Pain diversity absent. Honest reason: Pain 3 is the only pain
with sourced evidence (B6, B7 via EUR-Lex; 22-country scope
from case definition). Pain 1 and Pain 2 rest entirely on
UNVERIFIED claims; their use cases are capped at value 3
under evidence-graded scoring. If [M] and [C] sources are
verified, re-score UC-01, UC-02, UC-04, UC-05 and revisit
top three before canvas kata.

---

## Audit trail

Sourced claims used: B6 (ECGT transposition deadline), B7
(ECGT application date), case definition (22-country scope,
31% digital share, 18% YoY — modules/001-reference-cases.md)
Unverified claims used as directional context only: B2
(regional growth divergence), B3 (Zalando AI expansion)
Claims not used: B5 (Tesco — priority flag), P2 (superlative),
P4/P5/P6 (Zalando teardown — desk-based)
B9 removed from UC-07/10 rationale: B9 measures digital
growth, not compliance exposure; 22-country scope now cited
directly to case definition; non-compliance risk labeled
as inference