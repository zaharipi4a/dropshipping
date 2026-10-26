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
- Preferred platform: **custom-coded website built by the owner (NOT Shopify)**. Payments via Stripe (owner's home country). Fulfillment via **CJdropshipping API** (order creation, tracking via webhook or polling).
- Suppliers / apps already in use: none yet — prefer suppliers with US warehouses (CJdropshipping US, Zendrop, AutoDS) for ≤10-day delivery
- Channels to market on: TikTok (organic; TikTok Shop US likely needs a US entity — treat as affiliate/later option), Instagram Reels, Facebook ads, Pinterest, YouTube Shorts
- Hard no's (niches, product types): defaults from CLAUDE.md (no supplements, medical devices, trademarked goods, weapons, heavy regulation)
- Brand taste (likes / dislikes): TBD — ask at Gate B

---

## Portfolio

| Slug | Product | Stage | Status | Last update |
|---|---|---|---|---|
| nurse-reset-kit | Off-Clock Club — Post-Shift Reset Kit → night-shift nurses | Gate B | killed (owner) | 2026-10-26 |
| scout-xmas-20261026 | Christmas: aurora / northern-lights projector lamp (US stock, conditional) | Gate A | paused: owner rejected the lamp as a commodity (FB-006); superseded by scout-xmas2 | 2026-10-26 |
| scout-xmas2-20261026 | Christmas gift round 2: funny or useful, marketable | 1 scout x3 lanes | active | 2026-10-26 |

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
- 2026-10-26 [nurse-reset-kit] [orchestrator] GATE A: owner proceeds with Post-Shift Reset Kit (conditional on C1 CJ quote + C2 30+ day Meta ad). Folder renamed from scout-20261026. Curl kit held for January.
- 2026-10-26 [global] [orchestrator] Platform: custom website + Stripe + CJdropshipping API instead of Shopify (owner preference).
- 2026-10-26 [nurse-reset-kit] [brand-strategist] DECISION (pending Gate B) brand = Off-Clock Club, tagline "Sleep when the world's awake.", hero = The Off-Clock Pair ($59, gift one keep one). Alternates: Sunrise Sleeper, Day Sleep Club. Offclockclub.com looks available (Verisign RDAP 404); no web trademark hits; IG/TikTok handles unverifiable (unclear); USPTO search still required before printing. Rejected: Quiet Hours (existing self-care label), "Wind Down Kit" (Pinch Provisions $32 kit), plus ~10 names with taken .com. Two visual directions offered: A After Dark (navy/plum/brass, serif) vs B Golden Hour (peach/cobalt, rounded sans). See 03-brand.md.
- 2026-10-26 [nurse-reset-kit] [growth-strategist] GO-TO-MARKET: TikTok organic is primary (2 accounts: main + gift-guide), cross-posted to Reels/Shorts; Pinterest for gift search. Meta is the only paid channel ($12/day Nov 21–Dec 3 after Gate C + C2; TikTok ad-group minimum ~$20/day is above the ceiling). Top angles: A1 lights-on blackout test, A4 "gift they'll actually use" (not mugs/pens), A2 7:15 a.m. reset (creators only). Organic test Nov 9–22 (warm-up from Oct 29), 3 angles × 3 hooks, 2–3 posts/day. Seed 5 US night-shift nurse micro-creators with a 2-pack (~$97); kits ordered by Nov 3 or no Christmas content; 15% commission + 10% audience code; 60-day partnership/Spark rights. Paid budget cut $300→$230 to fund seeding (owner decides at Gate C). Last Christmas order date Dec 3, then late-gift printable card, then January self-purchase and Nurses Week. See 04-growth-plan.md.
- 2026-10-26 [nurse-reset-kit] [orchestrator] KILLED by owner at Gate B ("leave this nurse kit"). Files kept for reference; brand Off-Clock Club unused.
- 2026-10-26 [scout-xmas-20261026] [orchestrator] New run: Christmas gift / self-purchase holiday-feel product. Delivery before Dec 25 is the hard constraint.
- 2026-10-26 [scout-xmas-20261026] [product-validator] CONDITIONAL GO (43/60): aurora / ocean-wave projector lamp from **US stock**. SKU: Doba Honesty House D01027HNF0W, 4.85-day measured average delivery. Price $34.99 single / $64 2-pack. Delivered cost $10.17 is estimated from Doba's "up to $5.01 (33% margin)" hint: landed 29.1%, CM $21.19, BE ROAS 1.65. Latest safe order Dec 9, giving 24–29 selling days. Conditions, all due by Nov 2: Doba price ≤ $11.66, stock ≥ 50, no unsecured coin-cell remote, manual ordering allowed without the $149.99/mo API plan, and the owner approves the L-006 exception. A CJ US-warehouse SKU at ≤ $11.66 including the $0.50 fee replaces Doba. All China-route candidates fail L-002 and/or L-008 for 2026. If the conditions fail: build the store/brand now, launch Valentine's on the China route (latest order about Jan 20, 2027), and hold the book nook for Oct 2027. See 02-validation.md.
- 2026-10-26 [scout-xmas-20261026] [product-validator] CORRECTION after Stage QA r1 to the entry above:
  - Verdict: **GO only with an explicit owner waiver** covering the CJ-only rule (L-006) and the CJ US-warehouse condition (FB-005 / validator rule). Score 43/60 with the waiver; without it timing = 1, 37/60 = NO-GO this season.
  - The 4.85-day delivery is platform-displayed, not independently verified.
  - The 4.5% + $0.30 Stripe fee is assumed, not from the owner brief.
  - Customer shipping copy: "Ships from a US warehouse; delivery window confirmed after our test order" (L-003).
  - L-004 is met by 4 sales signals: Amazon B0B4518KC2, the Amazon top-10 average of ~3,900/mo, TikTok OneFire 34.6K and TikTok DESUNIC 22.6K.

---

## Insights

Things learned about markets, products, suppliers, audiences, and creatives that
are worth reusing. Format: `- YYYY-MM-DD [agent] INSIGHT — evidence`

- 2026-10-26 [product-scout] Free proof source: asinsight.com/report/US/<keyword-with-dashes> shows Amazon monthly unit estimates per ASIN plus weekly search volume, with no login. Amazon Best Sellers pages return 503 to agents.
- 2026-10-26 [product-scout] CJ, AliExpress search, Syncee, Zendrop catalog, DHgate and Alibaba showroom all sit behind captcha or login for agents. Indexed AliExpress item pages and Made-in-China listings are readable. Unit costs stay "estimated" until the owner quotes SKUs in a free CJ account.
- 2026-10-26 [product-scout] US de minimis ended for China parcels (2025-08-29); since 2026-03-01 duty is a % of value. Add about 35% of product cost as duty (assumed) to China-shipped landed cost. CJ US-warehouse stock-in needs ≥10/variant and ≥100 pcs total, which is too much for a <$500 start, so honest shipping is 7–15 days at first.
- 2026-10-26 [product-scout] Proven generic tools (ice roller, heatless rod, lick mat, scalp massager, pet roller) sell for $5–15 on Amazon. A single unit cannot reach $25+; a segment-specific kit is required to hit $25–40 while keeping landed ≤1/3. Source: asinsight reports in products/nurse-reset-kit/01-scouting.md.
- 2026-10-26 [product-scout] US TikTok Shop, 4 weeks to 2026-10-21: Beauty 18.2% of revenue (#1), Sports & Outdoor +12% over 4 weeks, Home Supplies −6.6% over 13 weeks, Pet only 1.4%. The $20–35 band holds the top revenue share (26.8%). Source: medialabs-co.com/blog/what-to-sell-on-tiktok-shop.
- 2026-10-26 [product-scout] Heatless curls demand: #heatlesscurls/#overnightcurls 224M views in 30 days; Kitsch headband ~11.4k TikTok orders Aug 14–Sep 10 2026 (tt123.com/t/IhrZ34Oy). Satin rods cost $1.0–1.8 at MOQ 100 with custom logo (Made-in-China).
- 2026-10-26 [product-scout] Hair or other products marketed primarily to kids ≤12 trigger CPSIA (third-party testing, CPC, tracking labels). Position for teens and adults.
- 2026-10-26 [product-validator] US duty stack for China parcels as of 2026-10-14 (zonos.com/us-tariff-updates): IEEPA tariffs ended 2026-02-24; the Section 122 10% surcharge expired 2026-07-24; a new Section 301 rate of 12.5% for China started 2026-07-24; MFN now applies to postal parcels; legacy 301 lists (7.5–25%) are assumed to still apply. Total is about 20–46% of value, so 35% stays a fair planning number. Postal parcels must be DDP and entered by a broker, so add about $1/parcel for clearance (assumed). Entry Type 13 starts 2027-01-20.
- 2026-10-26 [product-validator] An owner outside the US pays international card and FX fees on US orders, so budget 4.5% + $0.30 per order, not 3%. At realistic duty and clearance, every scouted kit lands at 35–39% of price; only 2-pack bundles meet L-002.
- 2026-10-26 [product-validator] CORRECTION to the scout's heatless-curls insight: TT123 attributes its 11.4k TikTok Shop orders (Aug 14–Sep 10) to an UNNAMED heatless-headband brand, not Kitsch. Kitsch's own figure is 29.5k sold, lifetime, on its TikTok Shop listing. The duty-stack lower bound is 17.5% (MFN 5% + new 301 12.5%), not 20%.
- 2026-10-26 [product-validator] Amazon sales proof (asinsight, 2026): blackout sleep masks have MZOO ~50k units/mo, and premium masks hold at $38–39 (Nodpod ~8k, Manta ~7k). Top sellers for "gifts for nurses" (2.4k searches/week, April) are $8–14 self-care items, with no kits in the top 10. Gift buyers are anchored low.
- 2026-10-26 [product-scout:gadgets-fun] RankHero (rankhero.com/keywords/<kw-with-dashes>) gives 12-month global monthly volume per keyword: free, readable, good for Q4 seasonality. "book nook kit" Dec 135k vs 33k Apr–Jul; "christmas book nook" 63% of searches in Oct–Dec; "3d wooden puzzle" Dec 40.5k vs ~12k; "crochet kit" Dec 246k vs ~135k. Many asinsight keyword pages 404 (only popular keywords exist: wine-opener, crochet-kit, book-nook-kit, christmas-book-nook, 3d-wooden-puzzle work).
- 2026-10-26 [product-scout:gadgets-fun] Adult wooden miniature kits (book nooks, 3D puzzle houses) sell at $26–55 on Amazon with premium DTC at $90–190 (Anavrin: 724 active Meta ads, est. $0.55–1.0M/mo, BrandSearch). Factory cost $6.72–11.40 at MOQ 60–100 (Made-in-China), but 450–600 g means landed ~$20–26 under the duty assumptions, i.e. 34–44% of a $59 price. LED versions use AAA/AA (not coin cells), batteries not included; age label 14+.
- 2026-10-26 [product-scout:gadgets-fun] brandsearch.co/brands/<store-domain> shows Meta active-ad counts and traffic/revenue estimates for competitor stores without login (ad age usually not shown).
- 2026-10-26 [product-scout/personal-gifts] Printify (developers.printify.com, public API, so it fits a custom site) has US-fulfilled engraved jewelry: bar necklaces by Fulfill Engine, production 1–9 business days, US shipping 2–5; base ~$18.50 free plan, ~$12.76 Premium. ShineOn (message-card jewelry) is Shopify-only and does not fit L-006. Official 2026 holiday cutoffs not published in sources read; verify in the Printify dashboard.
- 2026-10-26 [product-scout/personal-gifts] Satin/silk sleep sets are proven (Amazon silk pillowcase top ASIN ~10k units/mo, satin pillowcase ~37k searches/wk, Kitsch set 2,238 reviews at 4.9 stars, Slip/Blissy sell holiday gift sets), but generic sets sit at $10–16. Only a gift-box version at $35–45 clears L-002 (light ~220 g, landed ~$12.70 estimated). Jewelry travel cases: ASINs 10k and 8k units/mo, December search peak (SaleHoo), but $10–16 anchor.
- 2026-10-26 [product-scout:cozy-home] TikTok Shop public search pages shop.tiktok.com/us/k/<keyword-with-dashes> are readable by agents and list lifetime sold counts, price and rating per listing (no login). Used for aurora projector (OneFire 34.6K sold at $32.37; DESUNIC 22.6K at $12.99), sunset lamp (37.6K at $12.99), fireplace flame diffuser (11.2K at $37), flameless candles (floating 241.8K at $11.99), fuzzy socks. Some slugs 404.
- 2026-10-26 [product-scout:cozy-home] Aurora/northern-lights projector lamp has a measured Q4 spike: RankHero global searches 2,900/mo (Jun–Sep 2025) to 14,800 (Nov) and 18,100 (Dec 2025). Amazon B0B4518KC2 ~9–10k units/mo at $36–44, "northern lights projector" ~33.9k Amazon searches/week (Mar 2026). Commodity floor is $9–13 on Walmart/TikTok, so $39 needs gift packaging or a bundle. CJ product/list pages return a captcha redirect (frontend.cjdropshipping.com/egg/cj/validation.html); US-warehouse status unknown. Lamp family lives on USB; check remote battery (CR2025 coin cell is excluded).
- 2026-10-26 [product-scout:cozy-home] Cozy-home items are almost all $4–15 commodities; only items with a feature stack (aurora + speaker, 3-in-1) hold $35+ on Amazon. Electric flame diffusers ($37–46 on TikTok) fail L-002 (landed ~44%) because of 350–450 g and leak risk.
- 2026-10-26 [product-scout/personal-gifts] Personalized jewelry is crowded: 676k Etsy listings, median $24.39 (ListifyAI), Etsy birth-flower necklace $19.99 with ~27k lifetime sales (FindNiche, third-party). Amazon "personalized name necklace" top ASIN only ~1,000 units/mo. (An earlier McKinsey claim on reduced holiday jewelry spend came from an unretrieved search summary: unverified.) CJ lists a pre-designed "3D Engraved Bar Necklace" at $2.69–3.48 (not customer-personalized); no CJ satin sleep set or travel jewelry case found, CJ US stock unverified.
- 2026-10-26 [product-scout:cozy-home] US-stock route outside CJ: Doba (doba.com/dropshipping/<keyword>.html readable; prices behind sign-up; plans ~$30–60/mo) lists in-stock, ships-from-US aurora/ocean-wave projectors, galaxy projectors with Bluetooth and ~10 sunset lamps; product page shows handling 2 business days (avg 1) and 3–5 day delivery via GOFO. Using it is an L-006 exception (needs owner approval at Gate A). China-route latest order for Dec 23 delivery is Nov 30 (17 bd); Global Sources 14–21 day lead pushes it to Nov 11–18. Add CJ US-warehouse $0.50/parcel fee when using CJ US stock.
- 2026-10-26 [product-scout:cozy-home] Landed-cost rule of thumb on the China route: landed = unit × 1.35 + shipping + $1; for a 250 g item with $6.50 shipping, unit must be <= $4.07 for a $39 price (<= 1/3).
- 2026-10-26 [product-scout/personal-gifts] CORRECTION to the line-75 satin insight: on real quotes the boxed satin set does NOT clear L-002 at $42. Made-in-China search pages (made-in-china.com/products-search/hot-china-products/<Keyword_With_Underscores>.html) are readable and give per-unit quotes. Nan'an Brightpath 3-pc satin set in a magnetic box with logo costs $6.20 (MOQ 20, lead 15 days), which lands at $15.55 = 37% of $42; it passes only at $47. Zibo Daranfang 3-pc set costs $2.94–3.33 (MOQ 50, OPP bag, lead ~30 days, so too slow for Christmas). Components: mask $0.54–0.83 (MOQ 100), scrunchie $0.22–0.32 (MOQ 20), pillowcase $3.49–4.84, rigid magnetic box $1.90–2.90 (MOQ 500), card $0.06–0.13. Travel PU jewelry case costs $2–3 (MOQ 200) or $4.79–5.49 (MOQ 48), plus velvet pouch $0.25. These are bulk MOQs, not dropship prices. CJ search still redirects to a captcha; no CJ SKU found for either.
- 2026-10-26 [product-scout/personal-gifts] The satin sleep set is a commodity at Christmas: Kitsch sells holiday gift sets (Grinch x Kitsch, Kitsch x elf Christmas pillowcase, HOLIDAY20), Brushworks (UK) sells gift-boxed sets, and W7 sells a "Sleep Talk Christmas Gift Set" at £5.99 (UK). A gift box is not a positioning gap for this product.
- 2026-10-26 [product-scout:pets-hobbies] Pets and broad-hobby gifts are a price-floor trap: Amazon dog toys and cat toys top ASINs sell at $4–19 (10–30k units/mo, asinsight Aug 2026), and "gifts for dog/cat lovers" Amazon pages are dominated by $5–15 toys, socks, pens and sticky notes. TikTok pet gifts that sell are $7–15 charms. Only branded players (BARK mystery box $52 4.7K sold, Comfrt hoodie $28.60 8.6K sold) hold $25+.
- 2026-10-26 [product-scout:pets-hobbies] Seasonality (RankHero, estimated, global unless stated): "sourdough starter kit" Nov 60,500, Dec 90,500 vs Jul 18,100, US 100%; "gifts for book lovers" Nov 90,500, Dec 110,000 vs ~19.5k other months; "dog advent calendar" Nov 110,000, Dec 49,500, Jan 1,600 (Nov-only); "cat cave" Nov-Jan 14,800 vs 9,900 low; "camping lantern" no Q4 lift (Nov/Dec 14,800 vs 17.6k average). TikTok Shop sourdough: Starter-To-Loaf Kit 25.8K sold at $56.89, beginner bakeware kit 1.5K at $39.99; Amazon sourdough kits 10k/mo at $19.99–29.99 (asinsight Feb 2026).
- 2026-10-26 [product-scout:pets-hobbies] Made-in-China banneton quotes (low MOQ): Chengdu Olai basket + baking tools $10.80–11.42 (MOQ 1 set), 2-pc 9 inch set $14.17–14.83, single basket $4.21–4.99 (MOQ 2); Xiamen Athome sets $3.88–15.98 (MOQ 200). Book sleeves: Lebon polyester zip $1.29–4.30 (MOQ 200), Runhong waterproof pouch $2.00 (MOQ 300). Listings show no weight or lead time. CJ search for "banneton" redirects to the captcha; CJ blogs (Christmas products, winning products) name no SKUs or US-warehouse items.
- 2026-10-26 [product-scout:pets-hobbies] TikTok Shop "white-elephant-gifts" public page (measured, lifetime sold): Screaming Goat Plush $29.95 15.9K, Gejoy Fake Poop $13.25 18.2K, Middle Finger in a Box $10.99 11.6K, Spider Prank Box $17.99 4.2K, HornBlasters fart spray $25.99 12.1K (branded). Useful lead for funny-gift lanes; not verified for CJ sourcing.
- 2026-10-26 [product-scout:funny-gifts] Funny/gag gifts are a price-floor trap on TikTok Shop US: unbranded funny items that sell are $3-16 (prank boxes, fake poop, crochet "emotional support" doll $9.90 7.9K sold, squeeze toys). Items at $20-45 with 2K+ sold are all brand/IP/battery: Katamco toilet timer, Draft Top Lift can opener (24.2K at $25.99, patented), OTOTO ladles (Katie Cat 2.0K at $24.95), Screaming Goat plush ($29.95, 15.9K), HornBlasters fart spray, farting Santa bubble machine ($42.38). Grips Intelligence: novelty/humorous gifts category only $17M of tracked online sales in 2025, forecast -0% to -5% for 2026 (estimated).
- 2026-10-26 [product-scout:funny-gifts] White-elephant seasonality (RankHero, estimated): "white elephant gifts" Oct 9.9K, Nov 74K, Dec 246K, Jan 8.1K, summer ~1-2K; "secret santa gifts" Oct 27.1K, Nov 246K, Dec 550K, Jan 12.1K. US share shown as 82% and 11% of headline (inconsistent). Gift-exchange "Santa swap" dice: TikTok 17.4K sold at $15.99 (shop.tiktok.com/us/k/best-male-white-elephant-gifts), Walmart $3.46-$9.24 per die (3 in PU foam, 12-sided), so floor is $3-9.
- 2026-10-26 [product-scout:funny-gifts] Bluetooth scroll rings ("TikTok scrolling remote"): TikTok Shop Xring 182.8K sold at $24.69, 48.3K at $24.98, $39.99 listings 41.6K and 7.9K; Amazon page-turner rings 5,000/mo at $15.99 but falling 17-33% MoM; Walmart with charging case $5.69; Global Sources factory $4.82-5.80 (MOQ 50, lead 15-20 days). TikTok Shop tolerates $25-40 for the identical item, Amazon/Walmart do not.
- 2026-10-26 [product-scout:funny-gifts] TikTok Shop gift boxes are where price tolerance is: Mayicivo Christmas self-care box with blanket 129.5K sold at $49.99, spa basket 68.4K at $38.99 (shop.tiktok.com/us/k/gender-neutral-gifts-white-elephant). Bundles that read as one gift beat single novelties in this market.

- 2026-10-26 [useful-daily] INSIGHT: TikTok Shop unbranded men's wallets hold $26-40 at huge volume (GSOIAX $25.80 177.8K sold, TacticalTide $33.59 121.7K, umoven $39.95 39.7K) while Amazon plain slim wallets sit at $8.49-15.99; RankHero "mens wallet" Dec 550K vs Jul 201K. Best price-tolerance category found for light daily-use gifts. Source: shop.tiktok.com/us/k/mens-wallet, asinsight mens-wallet.
- 2026-10-26 [useful-daily] INSIGHT: Made-in-China search pages give factory prices: carbon-fibre money-clip wallets $2.09-2.80 (MOQ 100-500), rolling knife sharpener kits $7.78-11.50 (MOQ 10-1000) at ~500-600 g, so the sharpener fails L-002 on the China route. Tumbler (rolling sharpener original) runs 110 Meta ads (BrandSearch, estimated).

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
- 2026-10-26 Post-Shift Reset Kit for night-shift nurses — owner rejected at Gate B: positioning felt contrived; wants a product with obvious, broad Christmas gift appeal.
- 2026-10-26 Rechargeable milk frother coffee/cocoa set — Amazon anchor $9 (40k units/mo), sales falling in June; $25+ needs a filler bundle; Li-ion.
- 2026-10-26 Electric wine opener gift set — Oster/Secura/Rabbit own it ($21–50), landed 44–52% of $39, Li-ion shipping, Rabbit design-patent risk, no Q4 proof found.
- 2026-10-26 Fidget/desk toys for adults — NeeDoh (Schylling) branded top seller, rest $5–10 squishies, 837 weekly searches.
- 2026-10-26 Diamond painting / embroidery kits — big volume but $7–17 anchor, cannot reach $25+ without contrived bundle.
- 2026-10-26 Mini tabletop Christmas trees — top ASINs sell 100–200/mo, string lights at $10; no proof of volume.
- 2026-10-26 Crochet Christmas ornament kit — kept as weak backup: Woobles owns the $30 design tier, unbranded anchor $8–15, landed ~40%.
- 2026-10-26 Blanket scarf — search ~247/wk, top ASINs down 14–50% MoM (asinsight, Aug 2026).
- 2026-10-26 Valet tray — top-10 average only ~670 units/mo.
- 2026-10-26 Gua sha sets — skin claims plus Kitsch/ANUA/medicube brands dominate.
- 2026-10-26 Passport holder / large jewelry organizer box / jewelry advent calendar — not a gift-obvious item / bulky / must arrive by Dec 1.
- 2026-10-26 ShineOn message-card jewelry — Shopify-only, breaks L-006 (custom site).
- 2026-10-26 Hand-crank wooden music box kit — only generic "3d wooden puzzle" volume, no product-specific sales signals (L-004); landed 40–49% of $42.
- 2026-10-26 Crochet Christmas ornament kit — updated: dropped (appeal 3/5, skill needed).
- 2026-10-26 [cozy-home] Candle-warmer lamps (40–50k units/mo, $10–15) — electric heating product, excluded.
- 2026-10-26 [cozy-home] Flameless/rechargeable LED candle sets — huge demand (floating candles 241.8K sold on TikTok Shop) but button/lithium cells, $9 Amazon anchor; revisit only with a verified AAA or USB-C SKU.
- 2026-10-26 [cozy-home] Throw/sherpa blankets and fuzzy slippers — $9–18 anchor, 600 g+ bulk, S/M/L sizes on slippers; Bedsure brand holds the sherpa top spot.
- 2026-10-26 [cozy-home] Moon lamps, Christmas projector lights, LED curtain lights, tabletop trees — lithium/battery cells, 3.0–4.0 star Christmas-only projectors, thin sales (<400), or fragile ceramic $78 set.
- 2026-10-26 [cozy-home] Fireplace flame diffuser — proven (TikTok 11.2K sold at $37) but landed ~44% of $45 and leak risk; backup only.
- 2026-10-26 Christmas book nook kit — HOLD for Oct 2027 unless a CJ US-warehouse SKU and landed ≤ $19.67 are found; China-only route leaves ~2 weeks and no organic test (L-008).
- 2026-10-26 [orchestrator] Mini Christmas trees (tabletop) — not proven: top ASINs sell only 100–200/mo (asinsight, estimated). Correction to the line-72 insight: book nook landed is $20.45–29.20 (35–50% of $59, estimated), not $20–26 (QA r2 arithmetic fix).
- 2026-10-26 [personal-gifts] Satin sleep set "Christmas gift box for her" as a positioning gap — not a gap: Kitsch, Brushworks and W7 already sell gift-boxed and Christmas sets; on real quotes the set fails L-002 at $42 (landed 34–40%). Kept only as a conditional pick at $47 or with a CJ quote ≤ $5.18 per boxed set.
- 2026-10-26 [personal-gifts] Satin 2-set $75 bundle — Brightpath route lands at 35.9% (fails L-002); the Daranfang route passes at 32.4% but its ~30-day lead time fails L-008 for 2026.
- 2026-10-26 [orchestrator] Wording correction to lines 82 and 129: the satin-set costs were public Made-in-China listing prices at bulk MOQ (estimated), not supplier quotes. Line 75 ("clears L-002, landed ~$12.70") is superseded: landed is $14.24–16.87 at $42, which fails L-002; it passes at $47.
- 2026-10-26 [validator] Aurora lamp via CJ China route ($39) — NO-GO 2026: at a realistic ~450 g (a comparable Doba cube is 1.0 lb), landed is 38–46%; L-002 needs a unit cost ≤ $2.59; latest order Nov 30 leaves no test buffer.
- 2026-10-26 [validator] 3-in-1 sunset lamp ($41, China) — NO-GO 2026: landed $13.58 passes only at ≥ $40.74, above the proven $37, and fails at 450 g (38%); no US-stock 3-in-1 found.
- 2026-10-26 [validator] Satin sleep gift set (Brightpath, $47) — NO-GO for Christmas 2026 (timing 1): needs about $150 of bulk stock paid by Oct 30, before Gate A; about 8–11 selling days; 34.1% landed with inbound freight; commodity. Valentine's MAYBE only with a CJ SKU ≤ $5.18.
- 2026-10-26 [validator] Travel jewelry case gift ($29) — NO-GO: no dropship route (1688 bulk MOQ 200, the $1.08 price is unverified); 39.2% landed on readable quotes; $10–16 anchor.
- 2026-10-26 [validator] CJ pre-engraved bar necklace ($32) — NO-GO: not personalised (appeal 3), no engraved-specific sales proof (L-004), generic bar necklace −20% MoM; landed 33.0% only at ≥ $32.
- 2026-10-26 [validator] Late-Dec/New Year "winter cozy" launch as a standalone plan — rejected: aurora searches fall from 18,100 (Dec) to 5,400 (Jan) (RankHero); usable only as a tail after the Christmas cutoff.
- 2026-10-26 [validator] Fuzzy-sock gift box (6 pairs, $34, China) — NO-GO: landed $11.88 = 34.9% (passes only at ≥ $35.63) against a $9.99 Amazon gift-sock anchor; not sourced; China-only timing.
- 2026-10-26 [scout-xmas-20261026] [owner] Aurora lamp rejected at Gate A: "who will want that?" Commodity with a $13 floor and no clear buyer or reason to use it. Round 2 (scout-xmas2-20261026) searches for funny or useful gifts that can be marketed. Round-1 files stay as reference (Doba route, timing math, rejected list).
- 2026-10-26 [pets-hobbies] Sourdough baking kit — near miss, HOLD: strong Dec demand (90,500 searches) but identical kits at $19.99 (Amazon) / $26.75 (Walmart); basket + tools quote lands ~$22.50 = 58% of $39 on the China route; needs a CJ US-warehouse SKU landed ≤ $13 and a visible difference.
- 2026-10-26 [pets-hobbies] Padded zip book sleeve — near miss, HOLD: appeal 5 but Amazon demand tiny (351 searches/wk), TikTok $5–22 with max 930 sold; a differentiating print is a custom run.
- 2026-10-26 [pets-hobbies] Dog/cat advent calendar (toys) — Nov-only demand (Jan 1,600), tiny TikTok sold counts, Dec 1 deadline, BARK/Frisco brands.
- 2026-10-26 [pets-hobbies] Dog/cat toys, cat caves/beds, suction-cup tug toy, hands-free leash (S/M/L, iYoShop), pet paw-print keepsake kits — $5–20 commodity floors, bulk (beds 500–800 g), low ratings (suction toys 1.7–3.7 stars) or sizes.
- 2026-10-26 [pets-hobbies] Wireless meat thermometer — ThermoPro, Inkbird, ThermoMaven, Meater own it; $13 instant-read floor; Bluetooth/FCC and battery burden.
- 2026-10-26 [pets-hobbies] Retro game stick / handheld emulator consoles ($34–66, 3.1K–12.5K sold on TikTok) — preloaded ROMs infringe IP; Li-ion.
- 2026-10-26 [pets-hobbies] Golf rangefinders ($49.99–79.99; REVASRI 70.8K sold) — laser product (FDA/CDRH), landed over 1/3; golf towels/hats/gag items are $10–18 or branded/printed.
- 2026-10-26 [pets-hobbies] Camping 4-pack LED lanterns ($23.69–29.99, 7k/mo) — no Q4 lift, battery cells, landed ~49%; gamer stands/mouse pads ($5–15); manual coffee grinder (450 g, $18 anchor); griddle/BBQ kits (1.5 kg); meat claws ($10).
- 2026-10-26 [funny-gifts] Toilet timer — Katamco trademarked ("as seen on Shark Tank"), generic sand timers $6-9, low sold counts.
- 2026-10-26 [funny-gifts] Draft Top Lift can opener / steel bottle openers — Draft Top patented and branded; steel openers 150-250 g fail L-002; funny cap-gun openers $5-8 with ~200 sold.
- 2026-10-26 [funny-gifts] Screaming goat plush, Liquid Ass fart spray, farting Santa bubble machine — brand/IP, sound-module button cells, liquid hazmat or kids' toy.
- 2026-10-26 [funny-gifts] OTOTO Katie Cat / Nessie ladles — protected branded designs; funny-and-useful at $25 sells (2.0K) but no safe unbranded source.
- 2026-10-26 [funny-gifts] Prank boxes, fake poop, middle-finger boxes, door knockers, hidden-reveal aprons, ugly sweaters/pajama pants, funny beanies/socks/mugs/blankets/tees — $2-20 floors, crude, size variants or fragile ceramic.
- 2026-10-26 [funny-gifts] Desktop punching bag — near miss: Amazon top ASIN ~900/mo at $23.98, 548 searches/wk, $9 floor; only PU-leather MifLog holds $28.59 (6.1K sold TikTok).
- 2026-10-26 [funny-gifts] Silicone ice molds, taco holders, meat claws, pizza scissors, back scratchers, travel bidet, wine stoppers, koozies — $5-15 anchors, no joke or gap.
- 2026-10-26 [useful-daily] Rejected (data in products/scout-xmas2-20261026/01-scouting-useful-daily.md): retractable car charger ($10.98 TikTok floor, 25 listings), packing cubes, laptop stand, desk mats, magnetic LED pickup tool (4-8 LR44 coin cells, $3-10), universal grip socket ($5-11), chicken shredder ($3-10), manual coffee grinder, 3-in-1 wireless chargers (MagSafe trademark), key organizers, safety razor kits, HotHands-owned hand warmers, winter hat/scarf/glove sets ($9), microwave heat pads, self-care gift boxes (blanket+glass cup heavy/fragile; spa baskets cosmetics, $17-19 identical).
- 2026-10-26 [useful-daily] REVISED after QA r1: no ranked picks. Wallet (tracker pocket + clip, $34.99) is a near miss: tracker wallets already sell at $29.99 (Amazon B0F8QJFWK5, B0DZHBM8KR) and $32.99 (TacticalTide, 34.5K sold), so no differentiator (L-009). Rolling knife sharpener ($44.99) is a near miss: China landed 45.9% (fails L-002), US SKU needs unit <= $9.69 and was not found, Tumbler IP gate open.
- 2026-10-26 [funny-gifts] Gift-swap dice and Bluetooth scroll ring — near misses, NOT picks (fail L-009 floors $3-9 and $5.69; China-only); lane pick: none; see products/scout-xmas2-20261026/01-scouting-funny-gifts.md.
- 2026-10-26 [funny-gifts] CORRECTION to the scroll-ring insight above (QA r1): Xring listings are Scrolling Ring 182.8K at $24.69, Bluetooth 48.3K at $24.98, 5.0 ring 41.6K at $39.99, PUTARE 20.4K at $13.99 and 11.0K at $29.99; Amazon page-turner decline is 16.7-33.3% MoM (not 17-33%). The "$39.99 listings 41.6K and 7.9K" wording merged two listings. Landed uses duty on product cost only: ring $5.57 unit = $11.52 (46% of $24.99).
