# Maturity Gap Analysis

**Date:** 2026-09-16
**Author:** Igor Kartun — Engineering
**Project:** Meridian Retail Group (MRG)
**Committed location:** https://github.com/ikartun/AI-Factory.git

---

## Scorecard

| Dimension | Level (L1 / L2 / L3) | Score (1.0 / 2.0 / 3.0) | Evidence (2–3 sentences)                                                                   |
|---|----------------------|-------------------------|--------------------------------------------------------------------------------------------|
| AI Capabilities | L2                   | 2                       | each delivery uses AI for development, code review. but not L3 because we don't use agents |
| Reusability | L1                   | 1                       | All prompts are per persons only, not shared                                               |
| AI Champions | L1                   | 1                       | No designated champion, only enthusiasts                                                   |
| Performance Tracking | L1                   | 1                       | No tracking of AI impact.                                                                  |
| DAU | L2                   | 2                       | Almost all team members use AI daily.                                                      |
| **Average** |                      | **[sum ÷ 5]**           |                                                                                            |
| **Overall Level** | L1                   | 1.4                     | L1 = 1.0–1.9 / L2 = 2.0–2.9 / L3 = 3.0                                                     |

---

## Gap Analysis

### Gap 1

**Dimension:** Reusability
**Current level:** L1
**Why this gap is most damaging:** Delivery can be faster only because each person uses its own AI help. If there would be shared prompts - it would speed up delivery much more, on a global, team level
**Root cause:** no established practice or infrastructure for organizing shared prompts

---

### Gap 2

**Dimension:** AI Champions
**Current level:** L1
**Why this gap is most damaging:** Because people can not start using AI properly hence gap 1 Reusability is still in place
**Root cause:** no formal Champion role defined anywhere and no time/budget allocated for it

---

## 30-Day Improvement Plan

### Step 1 — addresses Gap 1

| Field | Value                                                                                                                                                                                                                       |
|---|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Action** | Will be created a standard - how to support and share AI artifacts. In that standard will be described naming convention of md AI files, types of the files and the path where to have them for our applications codebases. |
| **Owner** | Tomás Reyes                                                                                                                                                                                                                 |
| **Timeline** | 10/16/2026                                                                                                                                                                                                                  |
| **Success metric** | AI standards are created and more than 20% of applications have the standards applied in their repos.                                                                                                                       |

---

### Step 2 — addresses Gap 2

| Field | Value                                                                                                                                  |
|---|----------------------------------------------------------------------------------------------------------------------------------------|
| **Action** | Designating an existing teammate Tomás Reyes as Champion. Then he will share his experience to existing team mates to make them also AI champions |
| **Owner** | Lena Park                                                                                                                              |
| **Timeline** | 10/16/2026                                                                                                                             |
| **Success metric** | 3 AI champions in the team                                                                                                             |

---

## Peer Review

**Reviewer:** Igor Kartun
**Date reviewed:** 2026-09-16

| Review question | Reviewer answer                                                                         |
|---|-----------------------------------------------------------------------------------------|
| Is the evidence for each dimension specific and observable — not aspirational? | Yes, the evidences are full and clear                                                   |
| Which score do you challenge, and why? | AI capabilities should be L1 because not all roles use AI and the usage is inconsistent |
| Is each root cause a structural/behavioural cause — not a symptom? | Yes / No — Yes, it's showing clearly why we have that gap                               |
| Are the success metrics measurable without asking the author? | Yes / No — Yes because they have particular numbers                                     |
| Would you sign off on this plan as a teammate? | Yes / No — It's fully analyzed and clear                                                |

---

## Revision History

| Version | Date       | Change                  | Author |
|---|------------|-------------------------|---|
| 1.0 | 2026-09-16 | Added module 020 kata 3 | Igor Kartun |
| 1.1 | 2026-09-16 | Reviewed                | Igor Kartun |  