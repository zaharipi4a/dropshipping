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

## CL-007 — 2026-10-27
Trigger: FB-007 (owner-approved change of market and criteria after two US Christmas rounds, ~100 ideas, nothing passed the US/CJ/China rule set: Germany/DACH, German, EUR, supplier-agnostic, looser margin and differentiation rules)
Classification: global (LEARNINGS) + structural (agent instructions, pipeline skill, pipeline.yaml). Owner profile in memory/MEMORY.md was already updated by the orchestrator and left as is.
Changed:
- evolution/LEARNINGS.md:
  - L-002 revised (medium → high, owner-approved): break-even ROAS (net price excl. VAT ÷ CM before ads) ≤ 2.2 and CM ≥ EUR 12; VAT never counts as margin; Applies-to adds growth-strategist. Superseded text kept in the rule. Evolver interpretation, flagged for the owner: ROAS is defined on the net-of-VAT price, which is what makes "landed up to ~40%" consistent with ≤ 2.2.
  - L-004 refined: proof may come from another market (market arbitrage) if the target-market gap is shown with German sources; DE source list.
  - L-006 revised: custom site stays; supplier-agnostic; tiers CJ (EU/DE stock preferred) / EU-stock dropshippers (BigBuy etc.) / EU POD with public API, no exception needed; integration cost per supplier; anything outside the tiers (e.g. Doba) still needs owner approval. Superseded text kept.
  - L-008 revised: evergreen or a peak 6–10 weeks out; EU stock must show ≤ 5 business days to DE; "Christmas or nothing" and CJ/US-warehouse preference dropped. Superseded text kept.
  - L-009 revised: recipient test, 3-second hook and "makes sense without explaining" stay hard; differentiation becomes a 1–5 score with levers we control (bundle, offer, guarantee, video, own POD design); 1 stays NO-GO; self-purchase buyer may count once as a recipient (evolver interpretation, since evergreen items aren't always gifts); price band EUR 15–80 VAT-inclusive, bundles allowed. Superseded text kept.
  - L-010 new (high): default market Germany/DACH, German customer-facing content, EUR VAT-inclusive prices, German/EU law.
  - New section "Reference: EU/DE economics and compliance": landed-cost formulas (EU stock vs China-direct), VAT/OSS, payment-fee placeholder, returns allowance 8% (assumed), DE compliance checklist, DE research sources. Items marked "to verify": EU low-value-parcel duty (reported interim ~EUR 3/item from 2026-07-01) and handling fees, national fees; VAT/OSS/small-business treatment (owner's registration country BG vs DE unresolved); Stripe/PayPal/Klarna EEA rates (placeholder 2.5% + EUR 0.30, assumed); EU withdrawal-function button from 2026-06-19; ODR-link removal; BattDG; LUCID obligation for supplier packaging in dropshipping; CJ EU/DE warehouse stock per SKU; BigBuy plan/API/delivery; EU POD providers; TikTok Shop DE seller requirements.
- .claude/agents/product-scout.md: DE default market; DE proof sources (Amazon.de, Otto, Kaufland, idealo, Google Trends DE, TikTok Shop DE, EU Meta Ad Library); market-arbitrage proof; Geography angle market-neutral; Part 3 uses L-006 tiers + integration cost + EU landed-cost block (CM, BE ROAS); output table headers updated; recipient-test column now "differentiation lever + score"; Learned rules: timing (evergreen/6–10 weeks, EU stock ≤ 5 bd), prefer EU/DE stock, differentiation score replaces the $10–15 drop rule, EUR 15–80 band.
- .claude/agents/product-validator.md: DE economics (net price, VAT, EU vs non-EU landed, payment mix, returns 8% assumed, supplier integration cost, LUCID/WEEE fixed costs, CM ≥ EUR 12, BE ROAS on net ≤ 2.2); EU product rules in step 5; timing step per L-008; step 7/8: commodity-floor + differentiation potential merged into one ×2 differentiation score (rubric max 70 → 65); quality bar ROAS red flag 2.5 → hard 2.2 + EUR 12; Learned rules: EU/DE-stock evidence, differentiation 1 caps NO-GO (the CL-006 "2 caps MAYBE" rule is superseded), EUR 15–80 band.
- .claude/agents/brand-strategist.md: German-friendly naming, .de via DENIC, DPMAregister/EUIPO/WIPO trademark checks (USPTO removed), du/Sie decision and German voice samples.
- .claude/agents/growth-strategist.md: DACH channels/communities in deliverable 4; Learned rules: evergreen timing, DACH default with "Werbung"/"Anzeige" and the differentiation lever as reason to buy.
- .claude/agents/copywriter.md: new "Language and market" section (German, du/Sie, EUR inkl. MwSt.); policies → DE legal pages (Impressum, Widerrufsbelehrung + Musterformular, AGB, Datenschutz, Versand & Zahlung) with owner-data placeholders and legal-check recommendation; quality bar German UWG/PAngV points.
- .claude/agents/store-builder.md: description (name unchanged) and body made supplier-agnostic (supplier adapter interface, per-supplier mapping, effort per supplier); Stripe with PayPal/Klarna; new "Market defaults" section (EUR VAT-inclusive, PAngV notes, "zahlungspflichtig bestellen", GPSR info, German footer pages); pixel values net of VAT, consent-gated; SETUP adds LUCID.
- .claude/agents/compliance-officer.md: description and checks rewritten for DE/EU (UWG, PAngV, Widerruf, Impressum § 5 DDG, TDDDG/GDPR, GPSR, VerpackG/LUCID, ElektroG/WEEE, BattDG, CE, textile labelling, HWG, DSA); FTC/CPSIA kept for US products only; must verify "to verify" items against official sources.
- .claude/agents/ads-manager.md, creative-producer.md, social-manager.md: Learned rules for German content, EUR/DE audiences, net-of-VAT ROAS, EU platform rules, "Werbung"/"Anzeige" labelling, Impressum on social profiles.
- .claude/skills/pipeline/SKILL.md: briefs always carry market/language/currency; STATUS.md records the market; launch checklist supplier-agnostic + DE items (legal pages, LUCID, GPSR, WEEE, VAT/OSS, consent, net values).
- workflow/pipeline.yaml: scout lanes declared market-agnostic (comment + `market_from`); no stage, parallelism or model changes.
- README.md: roadmap line now supplier-agnostic.
- memory/MEMORY.md: appended one Insights scope note marking the US cost facts as US-only (no history edited; Owner profile untouched).
- Not changed: CLAUDE.md (compliance/honesty/spend rules intact; its CJ/Stripe-free wording still fits), L-001/L-003/L-005/L-007, stage-qa, librarian, performance-analyst, model tiers (no new QA-failure pattern: recent fails were criteria-driven, not tier-driven), knowledge/ and products/ (scout-de-20261027 running). Housekeeping: Learned rules lists now scout 5, validator 4, growth 4, brand 3, ads 2, creative 1, social 1 (all under 12); MEMORY Insights compaction skipped because a scout is writing concurrently. Running scout-de-20261027 may have loaded pre-CL-007 instructions; the validator applies the new rules.
Reason: The US/CJ/China rule set made nothing pass; the owner can operate in Germany, speaks German, and accepted looser but explicit margin, timing and differentiation criteria with EU-stock suppliers.
Revert: git revert this commit, or restore the "Superseded:" text in L-002, L-006, L-008 and L-009 (and their seed/CL-003/CL-005/CL-006 Added lines), remove the FB-007 sentence from L-004, remove L-010 and the "Reference: EU/DE economics and compliance" section; restore the agent files, SKILL.md, pipeline.yaml comment and README line from the parent commit (product-validator: 9-item /70 rubric with commodity-floor risk and differentiation potential, ROAS red flag 2.5, CL-006 learned rules; product-scout: CL-005/CL-006 learned rules with CJ US / $10–15 / $19–49 wording; ads/creative/social learned rules back to "_None yet._"); remove the 2026-10-27 [evolver] Insights note in MEMORY.

## CL-006 — 2026-10-26
Trigger: FB-006 (owner rejected the aurora lamp at Gate A of scout-xmas-20261026, a conditional go that passed the numbers: "I don't know who will want that"; wants funny or useful Christmas gifts that can be marketed and that people actually use)
Changed:
- evolution/LEARNINGS.md: added L-009 (high): recipient test (3 named recipients, used or laughed at after unwrapping, marketable hook) plus visible differentiation from the cheapest identical listing; penalise $10–15 mass-market commodities; packaging/gift box alone isn't differentiation; $19–49 white-elephant/Secret Santa/stocking-stuffer prices are fine. L-001 refined (supersedes "solve a visible problem demonstrable in under 3 seconds"): payoff shows in under 3 s as a problem solved, before/after, reaction or joke; Applies-to adds growth-strategist; confidence medium → high (owner-backed). L-005: pointer to L-009 as its concrete test (wording otherwise unchanged, no duplication).
- .claude/agents/product-scout.md: Output adds a `## Recipient test` table (3 named recipients | use/laugh moment | 3-second hook | cheapest identical listing price + link | visible differentiation); Quality bar adds the recipient test (unfillable cell → drop); Learned rules: drop $10–15 identical commodities without photo-visible differentiation; prefer daily-useful or genuinely funny gifts at $19–49, reject decorations nobody asked for.
- .claude/agents/product-validator.md: new process step 7 (re-check recipient test, find cheapest identical listing on TikTok Shop/Amazon/Temu); Score (now step 8) adds commodity-floor risk, weighted ×2; Quality bar: no GO on a failed recipient test; Learned rules: commodity-floor 1 caps verdict at NO-GO, 2 at MAYBE; don't penalise the price point itself.
- .claude/agents/growth-strategist.md: Learned rule: gift angles built from the recipient test, hooks lead with the use/laugh moment, never packaging as main differentiator.
- Not changed: creative-producer (covered by refined L-001 via Applies-to), brand-strategist, workflow/pipeline.yaml and model tiers (the validator failed QA r1 and r2 on scout-xmas-20261026, but r2 was one trivial wording blocker and the owner's rejection was about selection criteria, not output quality). memory/MEMORY.md (portfolio row and owner rejection already recorded at line 147), knowledge/, products/ (concurrent writers). Housekeeping: Learned rules lists now scout 5, validator 4, growth 3 bullets (under 12); MEMORY compaction skipped (concurrent writers). Scouts launched after this change (scout-xmas2-20261026) pick up L-009 and the new scout rules on start.
Reason: A product can pass margin, proof, appeal and timing and still be something nobody wants to give or receive; the owner needs a named recipient, a real use or laugh, a hook, and a product that isn't an identical $13 listing in a nicer box.
Revert: git revert this commit, or remove L-009; restore L-001 to "Prefer products that solve a visible problem demonstrable in under 3 seconds of video." (Applies to: product-scout, product-validator, creative-producer; Confidence: medium; Added: seed); remove the L-005 pointer sentence and "CL-006" from its Added line; remove the scout `## Recipient test` output line, the recipient-test Quality bar bullet and the 2 new Learned rules; in product-validator remove step 7, renumber Score back to 7 without commodity-floor risk (weights: margin, risk, obvious appeal, timing ×2), remove the Quality bar bullet and the 2 new Learned rules; remove the last growth-strategist Learned rule.

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
