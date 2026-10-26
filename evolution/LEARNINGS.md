# Global Learnings

Rules that apply to **every** agent. Maintained by the `evolver`. Each rule has
an ID, the evidence behind it, and a confidence level. Agents must follow these
rules; when a rule conflicts with an agent's own instructions, the rule wins
unless it's marked `low` confidence.

Format:

```
### L-<number>: <rule in one imperative sentence>
- Applies to: all | <agent names>
- Why: <evidence: feedback ID, performance data, or decision>
- Confidence: low | medium | high
- Added: YYYY-MM-DD (CL-<number>)
```

---

### L-001: Prefer products whose payoff shows on video in under 3 seconds: a visible problem solved, a before/after, a reaction, or a joke that lands without explanation.
- Applies to: product-scout, product-validator, growth-strategist, creative-producer
- Why: Seed rule. Short-form video is the main acquisition channel; demonstrable products convert cold traffic. FB-006: the owner wants products "which can be marketed" and accepts funny gifts, so a reaction or joke counts as the demo, not only a problem solved.
- Confidence: high
- Added: seed; refined 2026-10-26 (CL-006)

### L-002: Target a landed cost (product + shipping) of at most one third of the selling price.
- Applies to: product-scout, product-validator, ads-manager
- Why: Seed rule. Paid acquisition typically eats 30–40% of revenue; anything thinner can't survive testing.
- Confidence: medium
- Added: seed

### L-003: Never promise shipping times the supplier hasn't demonstrated.
- Applies to: brand-strategist, growth-strategist, copywriter, creative-producer, store-builder, social-manager, ads-manager
- Why: Seed rule. Late deliveries cause chargebacks and payment processor holds. FB-004: the brand stage put a shipping-window claim in its file, so the rule now covers every agent that writes customer-facing words.
- Confidence: high
- Added: seed

### L-004: Only pursue products with at least three independent proof-of-sales signals; never bet on unproven inventions.
- Applies to: product-scout, product-validator
- Why: FB-001 — owner wants products proven to sell.
- Confidence: high
- Added: 2026-10-26 (CL-001)

### L-005: Differentiate through positioning that sharpens a natural, obvious angle (gift, occasion, feeling, self-treat) for a broad buyer, never through an invented micro-niche, and pick only products a normal shopper understands and wants on sight without explanation; the store is secondary to marketing.
- Applies to: all (especially product-scout, product-validator, growth-strategist, brand-strategist)
- Why: FB-001 — owner: "website is the easiest part, marketing is the hardest." FB-005 — owner killed the night-shift-nurse reset kit at Gate B as contrived ("leave this nurse care kit and the other bs"); wants products people buy as a Christmas present or for themselves for the holiday feel. Test: if the product only makes sense once you explain who it's "for", reject it. "Wants on sight" is tested concretely by L-009.
- Confidence: high
- Added: 2026-10-26 (CL-001); refined 2026-10-26 (CL-005, CL-006)

### L-006: Plan every store as a custom-coded site with Stripe payments and CJdropshipping API fulfillment; never assume Shopify, its apps, plan costs or CSV imports unless the owner asks.
- Applies to: store-builder, product-validator, copywriter, compliance-officer, ads-manager, growth-strategist, orchestrator
- Why: FB-003 — owner: "I will not use Shopify. I'll create my own custom website… We'll work with CJdropshipping."
- Confidence: high
- Added: 2026-10-26 (CL-003)

### L-007: When fixing a QA issue list, re-check every section you changed against your quality bar and these rules before returning, so a fix never introduces a new blocker.
- Applies to: all agents that produce stage files
- Why: FB-004 / memory/runs.md — the brand stage's fix rounds introduced new blockers (shipping-window claim, unpriced packaging, overclaimed name uniqueness), costing 3 QA rounds plus an opus escalation; the validator also failed its first QA. Seen on 1 product, 2 agents.
- Confidence: medium
- Added: 2026-10-26 (CL-004)

### L-008: Score every candidate on timing: its demand peak (season, holiday, gifting window) must still be ahead, and the supplier's demonstrated processing + transit time (prefer stock already in a CJ/US warehouse) must deliver before the occasion's date with buffer for the organic test; otherwise reject it or hold it for its next season.
- Applies to: product-scout, product-validator, growth-strategist, ads-manager
- Why: FB-005 — owner wants seasonal/emotional demand weighted heavily, including delivery-by-date feasibility via US-warehouse stock. Delivery dates are internal planning numbers; customer-facing promises still follow L-003.
- Confidence: high
- Added: 2026-10-26 (CL-005)

### L-009: Shortlist a product only if it passes the recipient test (a buyer can name 3 real recipients, it gets used or laughed at after unwrapping, and it has a marketable hook per L-001) and it is visibly different from the cheapest identical listing; penalise commodities with a $10–15 mass-market floor and no differentiation.
- Applies to: product-scout, product-validator, growth-strategist
- Why: FB-006 — owner rejected the aurora lamp at Gate A despite passing numbers: "I don't know who will want that. I want something which can be marketed and the customers would actually want it and use it." It was an undifferentiated commodity ($12.99 identical on TikTok Shop) whose only edge was a gift box. Passing the numbers is not enough. Recipients are named people ("my dad", "a coworker for Secret Santa"), not segments. Useful or funny both pass; a decoration nobody asked for fails. Differentiation means a feature, function, joke/print or bundle the buyer can see in the listing photo; packaging or a gift box alone doesn't count. White-elephant / Secret Santa / stocking-stuffer price points ($19–49) are fine; the problem is an identical item far cheaper elsewhere, not a low price.
- Confidence: high
- Added: 2026-10-26 (CL-006)
