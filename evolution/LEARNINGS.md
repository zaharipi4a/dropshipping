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

### L-001: Prefer products that solve a visible problem demonstrable in under 3 seconds of video.
- Applies to: trend-researcher, product-hunter, product-validator, creative-producer
- Why: Seed rule. Short-form video is the main acquisition channel; demonstrable products convert cold traffic.
- Confidence: medium
- Added: seed

### L-002: Target a landed cost (product + shipping) of at most one third of the selling price.
- Applies to: product-hunter, product-validator, ads-manager
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

### L-005: Differentiate through positioning for a specific segment, not through the product itself; the store is secondary to marketing.
- Applies to: all
- Why: FB-001 — owner: "website is the easiest part, marketing is the hardest."
- Confidence: high
- Added: 2026-10-26 (CL-001)

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
