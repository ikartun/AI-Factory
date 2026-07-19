# Onboarding Baseline

**Date:** 2026-07-04
**Name:** Igor Kartun
**Role:** Engineering
**Primary skill (Deep role):** Engineering

## Maturity Self-Read (project: current engagement)

| # | Dimension | Level (L1 / L2 / L3) | Evidence (one sentence) |
|---|-----------|----------------------|-------------------------|
| 1 | AI Capabilities | L2 | Team uses Copilot individually with uneven adoption across roles; a centrally-added PR-review bot in ADO exists, but no shared practice or tracking. |
| 2 | Reusability | L1 | AI usage is one-off per person; nothing captured as a shared prompt, agent, or template. |
| 3 | AI Champions | L1 | No one is designated to drive AI adoption on the team. |
| 4 | Performance Tracking | L1 | No metric exists for AI's impact on delivery. |
| 5 | DAU (Daily Active Use) | L2 | Most teammates use AI tools, but not daily; the only centralized piece is AI code review. |

**Weakest dimension:** Reusability — nothing AI-related is captured or shared across the team; every use is one-off.

## What I Expect From This Course

I expect to apply agents to my team's daily work: different agents would do different things based on their role, fully or partially replacing human work, while humans orchestrate and check the results.

## Tool Setup

| # | Tool | Verified? (Y/N) |
|---|------|------------------|
| 1 | Chat assistant (DIAL): one prompt run | Y |
| 2 | IDE + coding agent: one AI completion accepted | Y |
| 3 | Claude via CodeMie: one message routed | Y |
| 4 | DIAL API key: one model call succeeded | Y |

## Running Case

**One-paragraph scope:** Meridian Retail Group grew through acquisitions, leaving each region with its own e-commerce stack (Shopify, .NET, Magento) that cannot talk to any other. That fragmentation now costs real revenue — ~7% of click-and-collect orders are cancelled due to phantom stock, customers hold 3–4 fragmented loyalty accounts across regions, and conflicting regional promotions erode margins. The 18-month, $42M program unifies 22 country sites, 12 mobile apps, and 1,400 POS systems onto a single headless commerce platform (commercetools + AWS EKS) with shared identity, cart, loyalty, and inventory — under a strangler-fig pattern with no acceptable downtime, serving an 80-person multi-SI team including a client product team learning the platform alongside delivery.

**Gut-check** — answer each question in one short line:

- Why build it? Each region built its own stack as the company grew through acquisition; that fragmentation now costs real revenue through phantom stock, lost loyalty, and conflicting promos.
- Who uses it, and where? Customers in stores and online, via web and mobile app.
- Is there code? Yes — commercetools + AWS EKS microservices, Kafka, Apollo GraphQL, Auth0, React Native, Next.js.
- Is there data? Yes — transactional orders, SAP ECC inventory feeds, Auth0 identity records, Snowflake for analytics.
- Is there a team? Yes — 80-person multi-SI squad with 6 product squads, QA chapter, and architecture team.
- Anything missing? Centralized communication between regions is not yet in place — the core problem this platform solves.
