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

## CL-005 — 2026-10-26
Trigger: FB-005 (owner killed nurse-reset-kit at Gate B as contrived; wants products with obvious Christmas gift / holiday-feel appeal, timing weighted heavily incl. delivery-by-date via US-warehouse stock)
Changed:
- evolution/LEARNINGS.md: L-005 refined (supersedes the old "positioning for a specific segment" wording): sharpen a natural, obvious angle for a broad buyer, never invent a micro-niche; product must make sense on sight without explanation. Added L-008 (high): score timing; demand peak must be ahead and demonstrated processing + transit (prefer CJ US-warehouse stock) must deliver before the occasion, else reject or hold for next season; customer-facing promises still follow L-003. Housekeeping: L-001/L-002 Applies-to updated from retired trend-researcher/product-hunter to product-scout.
- .claude/agents/product-scout.md: Part 2 rewritten to rank angles by preference (occasion/season, value/identity, broad audience, geography, gift-set bundle) and explicitly exclude profession/hobby micro-niches; Learned rules: `Obvious appeal (1–5)` column with drop below 4; `Timing` column (peak, deadline, warehouse, processing + transit, latest order date); seasonal briefs rank L-002-passing combos by appeal × timing and prefer CJ US-warehouse SKUs.
- .claude/agents/product-validator.md: new process step 6 "Timing & delivery feasibility"; score adds obvious appeal and timing, both weighted ×2 alongside margin and risk; Learned rules: appeal 1–2 = NO-GO; timing infeasible = NO-GO/hold, no assumed US-warehouse stock without a listed SKU or quote.
- .claude/agents/growth-strategist.md: nurse examples replaced (identity angle, quality-bar "specific beats broad" line now "natural beats contrived"); Learned rules: lead with natural occasion angles and hooks clear in <3 s; plan backwards from the latest-order date.
- Not changed: memory/MEMORY.md, knowledge/, products/ (3 concurrent scouts writing; MEMORY already records the kill and the rejected idea). workflow/pipeline.yaml and model tiers (no QA-failure evidence for scout/validator this run). brand-strategist (L-005 applies via "all"). Housekeeping: no Learned rules list over 12 bullets; MEMORY compaction skipped (concurrent writers).
Reason: The owner rejected a contrived single-profession kit; positioning must refine an angle the product naturally has, and seasonal products only work if they can arrive before the occasion.
Revert: git revert this commit, or restore L-005 to "Differentiate through positioning for a specific segment, not through the product itself; the store is secondary to marketing." (Applies to: all), remove L-008, restore L-001/L-002 Applies-to, restore product-scout Part 2 bullets (Audience/Use case/Value/Geography/Bundle) and step 6 Score text in product-validator from git history, restore the two growth-strategist example lines, and reset the three Learned rules sections to "_None yet._".

## CL-004 — 2026-10-26
Trigger: FB-004 (orchestrator, evidence in memory/runs.md: nurse-reset-kit brand stage took 3 QA rounds + opus escalation; 1 QA false positive on a concurrently written MEMORY entry)
Changed:
- .claude/agents/stage-qa.md: new `## Rounds` section. Round 1 reports every issue with a severity. Re-checks verify the prior list plus new/changed text only (compliance blockers in unchanged text still allowed, labeled "missed in round 1"). Re-read/Grep shared files (MEMORY, runs, knowledge) right before reporting an entry missing. Output adds `Round:`, a "trivial" tag on blockers, and a `Prior issues` fixed/not-fixed list. Input now includes the prior issue list on re-checks.
- .claude/skills/pipeline/SKILL.md: QA step passes the prior issue list on re-checks; after an opus escalation, the orchestrator may fix trivial blockers (formatting, a label, one sentence; no new facts/numbers; never compliance, pricing, segment or brand name) directly, logged in memory/runs.md and STATUS.md.
- workflow/pipeline.yaml: `escalate` comment notes the post-escalation trivial-fix path (no stage/model changes).
- .claude/agents/brand-strategist.md Learned rules: no delivery/dispatch-time words before a test parcel per L-003 (high); every packaging element priced or marked excluded upgrade (medium); uniqueness/availability claims match the name-check table (medium).
- evolution/LEARNINGS.md: L-003 Applies-to widened to brand-strategist, growth-strategist, creative-producer; added L-007 (medium): re-check changed sections against the quality bar and rules before returning a fix.
- Not changed: model tiers (brand-strategist failed twice on sonnet, but opus round 3 also failed on trivial blockers, so the problem was the QA loop and checklist, not tier; revisit if brand fails again on the next product). memory/MEMORY.md, knowledge/, products/ untouched (concurrent writers). Housekeeping: no Learned rules list over 12 bullets; MEMORY compaction skipped (not mine to edit this run).
Reason: Fix rounds kept exposing new issues because QA re-audited incrementally and the brand agent had no explicit check for shipping words, packaging costs or claim hedging; a trivial-blocker fourth round wastes time.
Revert: git revert this commit, or remove the `## Rounds` section and output additions from stage-qa.md, the "Re-checks"/"Trivial blockers" paragraphs from the pipeline SKILL, the 3 brand-strategist Learned rules (restore "_None yet._"), L-007, the pipeline.yaml comment lines, and restore L-003 Applies-to to "copywriter, store-builder, social-manager, ads-manager".

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
