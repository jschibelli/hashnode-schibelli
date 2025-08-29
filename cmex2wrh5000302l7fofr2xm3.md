---
title: "A Multi-Tenant Chatbot MVP That Fits SMBs"
datePublished: Fri Aug 29 2025 17:00:34 GMT+0000 (Coordinated Universal Time)
cuid: cmex2wrh5000302l7fofr2xm3
slug: a-multi-tenant-chatbot-mvp-that-fits-smbs
tags: case-study

---

# Building Tendril: A Multi-Tenant Chatbot Platform

## Problem

SMBs need website chat that actually helps customers without enterprise pricing or enterprise setup time. The common complaints: unpredictable costs (per-seat + AI surcharges), slow or fragile setup, and basic features locked behind premium tiers. Agencies also lack a clean way to manage multiple client bots under one roof.

## Research / Discovery

* Users resent per-seat pricing and AI per-resolution fees that cause bill shock.
* Setup is often slow or brittle; some tools struggle to answer from a site's own content without heavy manual work.
* Branding and multi-tenant support are typically gated or missing.
* There's demand for a simple, predictable, SMB-friendly alternative with fast deployment and honest limits.

## Solution / Build Decisions

* **Architecture:** Next.js (App Router), Postgres + `pgvector` for embeddings, Redis for caching/rate limits.
* **AI:** OpenAI for embeddings and default chat; Anthropic as an optional premium model (documented for future iteration).
* **RAG:** URL/PDF ingestion → chunk → embed → retrieve → grounded responses.
* **Multi-tenant:** Subdomain routing per tenant with isolated data and branding.
* **Billing:** Stripe subscriptions with clear tiers; no per-seat or AI surcharges in MVP.
* **Handoff:** Simple human handoff (email/Slack) when the bot is unsure.
* **Analytics:** Core metrics only: conversation volume, deflection/resolution rate, top questions.

## How Tendril Differs

* Transparent, flat pricing. No per-seat, no AI overage line items in the MVP.
* Multi-tenant by design for agencies and multi-brand startups.
* Branding included at Pro.
* Fast setup from real documents (RAG) rather than brittle flowcharts.

## Outcomes / KPIs

:::pricing
Plan, Price, Bots, Conversations, Storage, Branding, Analytics, Notes
Free, $0, 1, 100/mo, 50MB, Powered by Tendril, None, Entry for demos
Pro, $49, 3, 5,000/mo, 5GB, Custom logos & colors, Basic metrics, Direct competitor to Tidio $59
Agency, $199, 10, 20,000/mo, 20GB, White-label + custom domains, Advanced analytics, Multi-tenant control panel
:::

:::comparison
Product, Entry plan, Billing model, Branding, Notes
Tendril, $49 Pro, Flat (no per-seat), Included at Pro, Multi-tenant by design
Intercom, $39–$139/seat, Per-seat + AI usage, Higher plans, AI $0.99 per resolution
Drift, ~$2,500/mo, Quote-based, Limited, Annual contracts
Chatbase, $40–$500, Tiered usage, Add-on fee, Extra for domain/branding
Tidio, $29–$59, Conversations-based, Limited on lower plans, Unlimited seats
:::

:::kpis
label, value
Setup time, Under 30 minutes
Bots at $49, 3
Conversations/month, 5,000
Resolution rate, 60–75% (target)
:::

## Screenshots / Gallery

:::gallery
url, alt
/images/case-studies/tendril-dashboard.png, Tendril dashboard with multi-tenant list
/images/case-studies/tendril-pricing.png, Pricing table on marketing page
:::

:::cta
title, subtitle, ctaText, href
Want a similar build?, I can ship this for your startup or agency., Contact me, /contact
:::

## Notes and Next Steps

* **Model strategy:** Default to OpenAI (cost-efficient), enable Anthropic (Claude) as a premium toggle for longer context.
* **Integrations:** Ticket handoff via email/Slack now; helpdesk/CRM integrations next.
* **Analytics:** Expand with per-intent accuracy and satisfaction scoring as usage grows.

---

If you want a second variant focused on a different project later, we can reuse this exact structure and just remove the blocks you don't need (e.g., no pricing for a pure design case study).