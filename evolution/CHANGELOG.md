# Evolution Changelog

Every change the `evolver` makes to agents, skills, or learnings. Newest first.
This is what lets you audit or revert how the system has evolved.

Format:

```
## CL-<number> — YYYY-MM-DD
Trigger: FB-<number> | performance review <slug> | pattern across <n> products
Changed:
- <file>: <what changed>
Reason: <one or two sentences>
Revert: <how to undo, e.g. "remove rule L-007" or the old text>
```

---

## CL-003 — 2026-10-26
Trigger: FB-003
Changed:
- .claude/agents/store-builder.md: rewritten. Removed Mode A (Shopify: theme, apps, products.csv, Liquid) and the Shopify Buy Button option; the custom-coded site is now the only mode: mobile-first product page, Stripe Checkout/Payment Element, signed + idempotent Stripe webhook that creates CJ orders via the CJ API (offer → CJ SKU/variant mapping, address, logistics), tracking sync (CJ webhook or scheduled poll), transactional emails (confirmation, shipped, delay), Meta Pixel + CAPI and TikTok pixel + Events API with event_id dedup, legal pages, minimal admin view of orders/failures, env-var secrets with `.env.example`, `DRY_RUN` default, `store/SETUP.md`. Must check official CJ/Stripe/Meta/TikTok docs before coding and cite them. Description frontmatter updated (name unchanged).
- .claude/agents/ads-manager.md: tracking checklist now server-side events from the Stripe webhook, dedup, Stripe test mode.
- .claude/agents/product-validator.md: COGS uses CJ costs + Stripe fees (cross-border/FX) instead of "payment ~3% + app costs"; fixed launch costs are domain/hosting/email/samples, no platform subscription.
- .claude/agents/copywriter.md: email deliverable adds transactional emails (confirmation, shipped with tracking, delay).
- .claude/agents/compliance-officer.md: store check covers the custom site + Stripe + CJ (pixel consent, total before payment, transactional emails vs policies).
- .claude/skills/pipeline/SKILL.md: launch checklist verifies env secrets, Stripe live + webhooks, DRY_RUN off, and a real end-to-end order (Stripe → CJ → tracking → emails).
- README.md: roadmap item 1 drops the Shopify connector notes; Stripe + CJ APIs are the data sources.
- evolution/LEARNINGS.md: added L-006 (high).
- Not changed: CLAUDE.md (no Shopify references), social-manager and growth-strategist (no Shopify assumptions; TikTok Shop is a sales channel, kept), workflow/pipeline.yaml (outputs unchanged), memory/MEMORY.md and products/ (concurrent writers; MEMORY already records the platform decision). Housekeeping skipped this run (MEMORY compaction) per orchestrator.
Reason: Owner won't use Shopify; builds a custom site with Stripe and fulfills via the CJdropshipping API.
Revert: git revert this commit, or restore Mode A/Mode B in store-builder.md from git history and remove L-006.
Follow-up: products/nurse-reset-kit/02-validation.md and gate-a-report.html still list Shopify trial/plan costs; the owner or validator should replace them with domain/hosting/email costs on the next pass.

## CL-002 — 2026-10-26
Trigger: FB-002
Changed:
- workflow/pipeline.yaml: new; the pipeline as data (stages, parallel/fan-out, models, gates, escalation)
- .claude/agents/*: `model:` tiers (haiku: librarian, stage-qa; opus: validator, growth, analyst, evolver; sonnet: rest)
- Parallelism: scout fans out over 3 lanes; brand ∥ growth (growth now owns the avatar); creatives fan out per angle group; store ∥ social ∥ compliance; librarian always in the background
- New agents: librarian (knowledge filing), stage-qa (blocking quality gate), compliance-officer
- knowledge/: new cross-product library; memory/runs.md: new run log
- All stage outputs start with a `## Handoff` section; agents check knowledge/ before researching
- .claude/skills/pipeline: rewritten to execute pipeline.yaml, run QA + librarian, log, escalate to opus on repeated QA failure
- evolver: may edit pipeline.yaml and model tiers based on memory/runs.md
Reason: Owner wants maximum parallelism, cost/difficulty-based model routing, and every finding saved.
Revert: git revert the commit that added workflow/pipeline.yaml.

## CL-001 — 2026-10-26
Trigger: FB-001
Changed:
- .claude/agents/: merged trend-researcher + product-hunter into product-scout (proven sellers + positioning gap)
- .claude/agents/growth-strategist.md: new marketing-strategy stage (4) before content
- copywriter, creative-producer, social-manager, ads-manager: now work from 04-growth-plan.md angle IDs
- evolution/LEARNINGS.md: added L-004, L-005
Reason: Owner wants proven products with niche positioning, and marketing as the main effort.
Revert: split product-scout back into a trend researcher + product hunter, delete growth-strategist, remove L-004/L-005.

## CL-000 — seed
Trigger: initial setup
Changed:
- evolution/LEARNINGS.md: added seed rules L-001 to L-003
Reason: Starting heuristics so the first pipeline run has a baseline.
Revert: delete the rules.
