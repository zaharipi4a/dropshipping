# Shared Memory

The long-term memory of the studio. Every agent reads this before working and
appends to it after. **Append only** in the logs; the evolver may compact old
entries into `evolution/LEARNINGS.md`.

---

## Owner profile

Fill in once; agents tailor everything to it.

- Target markets / ship-to countries: **US** (owner is based outside the US, likely Europe — no US residency needed to sell; payments via owner's home-country Shopify Payments/Stripe)
- Store language(s): English (US)
- Starting budget (product samples + store + ads): **under $500 total**
- Daily ad budget ceiling for tests: **$0 during organic test**; max ~$10–15/day once an organic winner exists, only after Gate C
- Preferred platform: Shopify (default) — cheapest plan / trial
- Suppliers / apps already in use: none yet — prefer suppliers with US warehouses (CJdropshipping US, Zendrop, AutoDS) for ≤10-day delivery
- Channels to market on: TikTok (organic; TikTok Shop US likely needs a US entity — treat as affiliate/later option), Instagram Reels, Facebook ads, Pinterest, YouTube Shorts
- Hard no's (niches, product types): defaults from CLAUDE.md (no supplements, medical devices, trademarked goods, weapons, heavy regulation)
- Brand taste (likes / dislikes): TBD — ask at Gate B

---

## Portfolio

| Slug | Product | Stage | Status | Last update |
|---|---|---|---|---|
| scout-20261026 | Post-Shift Reset Kit (recommended) / Curl Kit (runner-up) | Gate A | waiting-on-human | 2026-10-26 |

Stage = 0–9 as defined in `CLAUDE.md`. Status = `active`, `waiting-on-human`,
`paused`, `killed`, `scaling`.

---

## Decision log

Format: `- YYYY-MM-DD [slug|global] [agent] DECISION — reason`

- 2026-10-26 [global] [orchestrator] Target market US, organic-first, <$500 budget — owner answers at intake; no US residency needed to sell to US.
- 2026-10-26 [scout-20261026] [product-scout] TOP PICK heatless curl kit → teen/adult competitive dancers & cheer ($29, landed ~$9, ~66%); runner-up ice-roller kit → night-shift nurses ($34) — strongest proof stack + lightest/cheapest to ship + unowned segment; see 01-scouting.md.
- 2026-10-26 [scout-20261026] [product-validator] GO Post-Shift Reset Kit → night-shift nurses ($34 / $59 2-pack, landed ~$12.30, CM $17.87, BE ROAS 1.90). MAYBE curl kit (CM $15.35, BE ROAS 1.89): unproven that it gives comp-grade curls, CPSIA pull, Kitsch $16 price anchor. NO-GO paw, STR, TNR. Nurse kit wins on Christmas-gift timing (order cutoff ~Dec 3) and lower compliance risk; see 02-validation.md.
- 2026-10-26 [scout-20261026] [product-validator] REVISED after Stage QA: nurse kit downgraded to CONDITIONAL GO (30/40), with the hero offer now the $59 2-pack (landed $19.30 = 32.7%, CM $33.49, BE ROAS 1.76). The single at $34 fails L-002 (36%); sell it only if CJ landed is ≤$11.33 (or ≤$12.00 at $36). Condition C2: all 3 product-level sales signals are Amazon-only and the nurse segment has 0, so a Meta ad running 30+ days is required, or the verdict becomes MAYBE. Curl kit stays MAYBE (29/40) and is set for January.
- 2026-10-26 [scout-20261026] [orchestrator] CORRECTION to the earlier product-validator GO entry: verdict is CONDITIONAL GO (C1: CJ landed ≤ thresholds, 2-pack ≤ $19.67; C2: a 30+ day Meta Ad Library ad for ice roller / blackout mask / nurse-gift kit). The $34 single is not sold at landed $12.30 (36.2%). Hero offer = $59 2-pack.

---

## Insights

Things learned about markets, products, suppliers, audiences, and creatives that
are worth reusing. Format: `- YYYY-MM-DD [agent] INSIGHT — evidence`

- 2026-10-26 [product-scout] Free proof source: asinsight.com/report/US/<keyword-with-dashes> shows Amazon monthly unit estimates per ASIN plus weekly search volume, with no login. Amazon Best Sellers pages return 503 to agents.
- 2026-10-26 [product-scout] CJ, AliExpress search, Syncee, Zendrop catalog, DHgate and Alibaba showroom all sit behind captcha or login for agents. Indexed AliExpress item pages and Made-in-China listings are readable. Unit costs stay "estimated" until the owner quotes SKUs in a free CJ account.
- 2026-10-26 [product-scout] US de minimis ended for China parcels (2025-08-29); since 2026-03-01 duty is a % of value. Add about 35% of product cost as duty (assumed) to China-shipped landed cost. CJ US-warehouse stock-in needs ≥10/variant and ≥100 pcs total, which is too much for a <$500 start, so honest shipping is 7–15 days at first.
- 2026-10-26 [product-scout] Proven generic tools (ice roller, heatless rod, lick mat, scalp massager, pet roller) sell for $5–15 on Amazon. A single unit cannot reach $25+; a segment-specific kit is required to hit $25–40 while keeping landed ≤1/3. Source: asinsight reports in products/scout-20261026/01-scouting.md.
- 2026-10-26 [product-scout] US TikTok Shop, 4 weeks to 2026-10-21: Beauty 18.2% of revenue (#1), Sports & Outdoor +12% over 4 weeks, Home Supplies −6.6% over 13 weeks, Pet only 1.4%. The $20–35 band holds the top revenue share (26.8%). Source: medialabs-co.com/blog/what-to-sell-on-tiktok-shop.
- 2026-10-26 [product-scout] Heatless curls demand: #heatlesscurls/#overnightcurls 224M views in 30 days; Kitsch headband ~11.4k TikTok orders Aug 14–Sep 10 2026 (tt123.com/t/IhrZ34Oy). Satin rods cost $1.0–1.8 at MOQ 100 with custom logo (Made-in-China).
- 2026-10-26 [product-scout] Hair or other products marketed primarily to kids ≤12 trigger CPSIA (third-party testing, CPC, tracking labels). Position for teens and adults.
- 2026-10-26 [product-validator] US duty stack for China parcels as of 2026-10-14 (zonos.com/us-tariff-updates): IEEPA tariffs ended 2026-02-24; the Section 122 10% surcharge expired 2026-07-24; a new Section 301 rate of 12.5% for China started 2026-07-24; MFN now applies to postal parcels; legacy 301 lists (7.5–25%) are assumed to still apply. Total is about 20–46% of value, so 35% stays a fair planning number. Postal parcels must be DDP and entered by a broker, so add about $1/parcel for clearance (assumed). Entry Type 13 starts 2027-01-20.
- 2026-10-26 [product-validator] An owner outside the US pays international card and FX fees on US orders, so budget 4.5% + $0.30 per order, not 3%. At realistic duty and clearance, every scouted kit lands at 35–39% of price; only 2-pack bundles meet L-002.
- 2026-10-26 [product-validator] CORRECTION to the scout's heatless-curls insight: TT123 attributes its 11.4k TikTok Shop orders (Aug 14–Sep 10) to an UNNAMED heatless-headband brand, not Kitsch. Kitsch's own figure is 29.5k sold, lifetime, on its TikTok Shop listing. The duty-stack lower bound is 17.5% (MFN 5% + new 301 12.5%), not 20%.
- 2026-10-26 [product-validator] Amazon sales proof (asinsight, 2026): blackout sleep masks have MZOO ~50k units/mo, and premium masks hold at $38–39 (Nodpod ~8k, Manta ~7k). Top sellers for "gifts for nurses" (2.4k searches/week, April) are $8–14 self-care items, with no kits in the top 10. Gift buyers are anchored low.

---

## Rejected ideas

Products/niches already evaluated and dropped, so nobody re-researches them.
Format: `- YYYY-MM-DD <product/niche> — why rejected`

- 2026-10-26 Car seat gap filler — Drop Stop (patented, 74k reviews) dominates; patent/lookalike risk.
- 2026-10-26 Medicube PDRN neck cream / NeeDoh advent / branded TikTok best-sellers — trademarked brands; skin claims.
- 2026-10-26 LED Christmas light gift boxes — one-day TikTok spike (5.4k units on Oct 17, then 1/day by Oct 20; FastMoss).
- 2026-10-26 "Old man" face balaclava — seasonal novelty spike, sizing.
- 2026-10-26 Press-on nails — many size/shape variants, high return risk.
- 2026-10-26 Wearable blanket hoodie — bulky, landed >$15, sizing variants.
- 2026-10-26 Electric mug warmer, rechargeable hand warmers, heated vests, electric fabric shaver, electric paw cleaner — battery/electrical compliance burden.
- 2026-10-26 Pet hair remover → car/dog-owner segment — Chemical Guys "Furry Friend" kit + Simoniz already own it.
- 2026-10-26 Lick mat → grooming/nail-trim segment — SodaPup and Wahl own it; lick mat interest −9% YoY (Glimpse).
- 2026-10-26 Scalp massager → braids/locs segment — Luxe Scalp Soother owns it; $5–7 Amazon anchor.
- 2026-10-26 Tear-off microfiber roll — strong TikTok week but launched Oct 7 (spike risk); cyclist segment owned by Muc-Off; Home Supplies declining.
- 2026-10-26 Snuffle mat — proven, but ~300 g bulk kills margin vs $6–12 Amazon anchor; no clear unowned segment found.
- 2026-10-26 Self-warming pad 3-pack for TNR caretakers — kept as backup only; ~650 g makes landed ~49% of price (fails L-002) unless a CJ US-warehouse quote is ≤$13.
- 2026-10-26 Self-warming pad 3-pack → TNR caretakers — NO-GO (validator): landed $20.43 = 52% of $39 price; break-even ROAS 2.73 (>2.5); community is price-sensitive.
- 2026-10-26 Salt-Season paw-washer kit → snow-belt city dog owners — NO-GO (validator): Dexas MudBuster ($10–15, ~62k ratings) already sells against road salt; landed 39%; S/M/L sizes.
- 2026-10-26 Pet-hair turnover kit → Airbnb/STR hosts — NO-GO (validator): B2B hosts already buy these $7–15 tools on Amazon; little organic reach; design-patent takedown risk (ChomChom-style roller, Uproot-style rake).
