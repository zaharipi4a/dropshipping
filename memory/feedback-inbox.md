# Feedback Inbox

Raw refinements from the owner and from performance reviews, waiting for the
evolver. `/feedback` appends here; `/evolve` processes entries and marks them done.

Format:

```
## FB-<number> — YYYY-MM-DD — pending
Source: owner | performance-analyst | <agent>
Scope: global | <agent-name> | <product-slug>
Feedback: <what to change, in the owner's words>
Context: <what triggered it, file/stage it relates to>
```

When processed, the evolver changes `pending` to `applied → CL-<number>` or
`rejected — <reason>`.

---

## FB-001 — 2026-10-26 — applied → CL-001
Source: owner
Scope: global
Feedback: Sell products that are proven to sell, then position ourselves in a specific market and dropship it. Building the website is the easy part; marketing is the hardest and needs the most attention.
Context: Initial design of the pipeline.

## FB-002 — 2026-10-26 — applied → CL-002
Source: owner
Scope: global
Feedback: Run things in parallel wherever possible; use different models (Haiku/Sonnet/Opus) by difficulty; make the whole thing a workflow where everything any agent finds is saved somewhere; make the architecture the best it can be.
Context: After the first scout run.

## FB-003 — 2026-10-26 — applied → CL-003
Source: owner
Scope: global (store-builder, ads-manager, copywriter, growth-strategist, compliance-officer, pipeline skill, README)
Feedback: "I will not use Shopify. I'll create my own custom website because I can. We'll work with CJdropshipping."
Context: Gate A of the first run. Store-builder must default to a custom-coded storefront: product page, cart/checkout via Stripe, CJ API order creation, tracking sync (webhook or polling) and customer emails, pixels/Conversions API, legal pages. Remove Shopify assumptions (plan costs, Shopify apps, product CSV) or keep them only as an optional fallback.

## FB-004 — 2026-10-26 — applied → CL-004
Source: orchestrator (from memory/runs.md)
Scope: pipeline skill, stage-qa, brand-strategist
Feedback: The brand stage took 3 QA rounds plus an opus escalation, and each fix round introduced or exposed new issues (shipping-time claims, unpriced packaging, overclaimed certainty, bullet counts). Proposed: (1) stage-qa reports ALL issues in round 1 with a severity, and on re-checks verifies only the earlier list plus genuinely new text; (2) after an escalation, the orchestrator may fix trivial blockers (formatting, single sentences) directly instead of another agent round; (3) add to brand-strategist's quality bar: no delivery or dispatch-time words anywhere (L-003), and every packaging element must be priced or marked as an excluded upgrade. Also: stage-qa gave a false positive on a memory entry written concurrently. It should re-read shared files right before reporting them missing.
Context: Brand stage, first run.

## FB-005 — 2026-10-26 — applied → CL-005
Source: owner
Scope: global (product-scout, product-validator, growth-strategist; LEARNINGS L-005)
Feedback: "Leave this nurse care kit and the other bs. I want a product which actually makes sense, that people buy as a Christmas present or for themselves for the Christmas-time feel."
Context: Gate B of nurse-reset-kit. Lesson: segment positioning must feel natural and obvious to a normal buyer. The owner rejects contrived micro-niches (a kit invented for one profession). Prefer products whose appeal is clear on sight, with seasonal/emotional demand (gifting, cozy, holiday feel). Positioning can sharpen an angle, but the product must make sense without explanation. Also weight seasonality/timing heavily, including delivery-by-date feasibility (US-warehouse stock).

## FB-006 — 2026-10-26 — applied → CL-006
Source: owner
Scope: global (product-scout, product-validator; LEARNINGS L-005 / new rule)
Feedback: "Do a new check for something with the Christmas-vibe gift which is either funny or useful. This lamp: I don't know who will want that. I want something which can be marketed and the customers would actually want it and use it."
Context: Gate A of scout-xmas-20261026 (aurora lamp, conditional go). The owner rejected a technically passing product because it is an undifferentiated commodity ($13 floor on TikTok) with no clear buyer or reason to want it. Lesson: passing the numbers is not enough. A product needs (1) a clear "who buys this and why" story a normal person gets instantly, (2) real use or real laughs after the gift is opened (useful or funny, not a decoration nobody asked for), (3) something to market: a hook, a reaction, a joke, a before/after. Commodity items with a $10-15 mass-market floor and no differentiation should be penalised. Prefer gifts that a buyer can name a recipient for ("this is perfect for my dad / coworker / mom"), white-elephant / Secret Santa / stocking-stuffer use cases, and products people actually use daily.

## FB-007 — 2026-10-27 — applied → CL-007
Source: owner
Scope: global (LEARNINGS L-002, L-006, L-008, L-009 and the market/currency defaults; product-scout, product-validator, brand-strategist, growth-strategist, copywriter, store-builder, compliance-officer, ads-manager, pipeline skill, workflow/pipeline.yaml)
Feedback: "Let's say leave the US market if there is no product which we can dropship, even though I think there is one. Maybe we need to change the criteria for what we're searching for, and also the distributor of it who can handle everything." Then: "I am in Bulgaria. Europe. I can manage everything in Europe. [Target one country.]" Then: "I speak fluent German, so German is not a problem. And I am Germany."
Context: After two Christmas rounds (about 100 ideas, nothing passes the US/CJ/China rule set). Approved changes (orchestrator proposal, owner accepted by replying with market and language):
1. MARKET: Germany first (DACH), language German, currency EUR. Replaces the US default. Compliance must cover German/EU rules (Impressum, 14-day withdrawal/Widerruf, price display, LUCID packaging register, WEEE for electronics, EU OSS VAT, GPSR product safety/EU responsible person, no health claims). Verify current EU low-value-parcel customs/handling rules before relying on China-direct routes.
2. L-009 (differentiation): from a kill rule to a SCORE. A cheaper identical listing is a risk, not an automatic reject, if we control a reason to pick us: a bundle, a better offer, strong video content, a guarantee, or our own design (print-on-demand). The recipient test, the 3-second demo and the "makes sense without explaining" tests stay hard.
3. L-002 (margin): replace "landed <= 1/3 of price" with break-even ROAS <= 2.2 and contribution margin >= EUR 12 per order before ads (allows landed cost up to about 40%). Landed in EU: unit + EU shipping + (no duty for EU stock; duty/handling for China-direct), VAT shown separately; prices shown VAT-inclusive in DE.
4. L-006 (suppliers): from "CJ only" to a tier list: CJ (default, incl. EU/DE warehouse if it exists), EU-stock dropship suppliers (BigBuy etc.), EU print-on-demand for own designs. No exception approval needed for these tiers, but the store-builder must be supplier-agnostic and every scout/validator must state the integration cost per supplier. Prefer suppliers with a public API.
5. L-008 (timing): drop "Christmas or nothing". Look for evergreen products or a demand peak 6-10 weeks away (Q4/winter, then Valentine's/spring, Mother's/Father's Day). Delivery to DE should be demonstrated at <= 5 business days for EU stock.
6. Price band $15-80 -> EUR 15-80, bundles allowed.
7. Proof: keep >= 3 sales signals; also allow products proven in another market (e.g. US) that are not yet well served in Germany (market arbitrage), and use German sources (Amazon.de, Otto, Kaufland, idealo, Google Trends DE where reachable, TikTok Shop DE).
Also: replace the stale US-centric facts in agent files (35% duty, $1 clearance, Stripe 4.5% cross-border, CJ US warehouse) with a EU/DE equivalent block, flagged as to-verify.
