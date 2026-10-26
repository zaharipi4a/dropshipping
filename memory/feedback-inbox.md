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
