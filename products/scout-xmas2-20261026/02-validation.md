# Validation — 2026-10-26 (Christmas round 2: funny or useful)

## Handoff
- **Honest result: no GO and no realistic MAYBE for Christmas 2026.** I re-scored 7 near misses from both rounds on the full rubric (max 70, with commodity-floor and timing weighted x2). Every one is NO-GO. The binding failure is **L-009 (commodity floor), not cost.** So no CJ quote can turn any of them into a GO this season. The only one a quote could lift is the rolling knife sharpener, and only to a capped, hypothetical MAYBE (44/70), with open HORL patent risk.
- **Wallet (best demand) is NO-GO with or without a waiver** (38/70, or 46/70 with a CJ US SKU). Scores and verdict are unchanged after QA r1; the evidence is now quoted verbatim.
  - **sohochic, $14.99, 15.9K sold** (measured as displayed 2026-10-26, [listing](https://shop.tiktok.com/us/pdp/smart-wallet-for-airtag-leather-rfid-blocking-slim-design/1731176224138826211)). Exact title: "Men's RFID Theft-Proof PU Leather Slim Wallet - PU Card Holder, RFID Organizer, AirTag Holder, ID Window, Cash Slot…". Its URL slug is "smart-wallet-for-airtag". **Correction to the useful-daily lane:** that lane called this listing "not tracker-specific"; the title shows it does have a tracker holder.
  - **Carbon-fibre bifold with tracker pocket and money clip, $10.98, 15 sold** ([listing](https://shop.tiktok.com/us/pdp/1732757710225576164)). Exact title: "Men's Airtag Wallet - Slim RFID Blocking Carbon Fiber Bifold Wallet with Pop Up Card Holder, ID Window & Money Clip". It is the same spec as our wallet, at $10.98.
  - The $12.39 carbon wallet I cited earlier has no tracker in its title, so it is withdrawn as evidence.
  - Result: commodity-floor = 1, which caps the wallet at NO-GO. Two possible differentiators were checked and both fail. Engraved/personalised wallets have thin volume (top TikTok listing 778 sold, engraved floor $8.99). Wallets that come with a tracker card are battery/FCC/"Find My" products with thin volume (924 and 60 sold at $45-52).
- **No additional candidate proposed.** I checked the $39-50 "one-gift" format on TikTok Shop (christmas-gifts-for-men page, 31 listings) and Amazon gifts-for-men (top 10). Everything with volume at $39-50 is either an electronic/battery item, cosmetics or fragrance, glass, a sized item (cowboy slippers 55.3K at $77.99) or a brand. The gender-neutral white-elephant page has since changed: on my fetch it shows only $6-45 trinkets, and the Mayicivo boxes the scout saw are no longer listed (snapshot changed, measured).
- **Recommendation: path (b).** Stop chasing Christmas 2026. Build the store, Stripe, the CJ API and the social accounts now, because they are needed for any product. The CJ account the owner opens for the API also allows a free 20-minute US-warehouse check (owner to-do 1), which is the last lottery ticket for Christmas 2026. Kill date: **Mon Nov 2**. Expect it to find nothing usable.
- **New timing flag for Valentine's 2027:** Chinese New Year is **Sat Feb 6, 2027**. Factories close from about Jan 20-22 and reopen about Feb 20-28 (epicsourcing, estimated). Valentine's on the China route only works if the SKU is already in CJ warehouse stock. The latest safe order is about **Jan 15** (assumed). From a Jan 2 launch that gives **13 selling days** (Jan 2 → Jan 15). It is fragile.
- **Better 2027 targets for "useful" gifts:** **Mother's Day (Sun May 9, 2027)** and **Father's Day (Sun Jun 20, 2027)**. Wallet and knife sharpener are classic Father's Day gifts (`assumed`, no Father's Day sales data checked). With 6+ months of lead time, an owned visible difference (our own design/engraving on a small run, or a bundle we pack) and a CJ stock-in become plannable after CNY.
- Economics basis (all rows): Stripe 4.5% + $0.30 (assumed; a rounded planning rate: 2.9% US base + ~1.5% cross-border/FX = 4.4%, rounded up); returns 5% (assumed); email $0.01 (assumed); China landed = unit x 1.35 + shipping + $1 clearance (assumed). Every unit cost is `estimated`, because CJ is captcha-blocked for agents.
- What could still produce a Christmas 2026 product, and how likely each is:
  - (1) **Possible but unlikely.** The owner's CJ search finds a US-warehouse rolling sharpener whose kit visibly differs from the $19 kit (e.g. includes a strop or a 3000-grit disc), at unit + US shipping <= $14.99 with 50+ in stock. Even then the best outcome is MAYBE plus patent risk.
  - (2) **Not recommended.** The owner overrides L-009 for the wallet. That contradicts FB-006.

## Ranking
Rubric 1-5 (5 = best or safest). The table shows raw scores; columns marked "raw (x2 in total)" are doubled in the total. Max 70.
Bands (the validator's own scale, set for this rubric, not a pipeline rule): GO >= 49 with no cap; MAYBE 42-48; NO-GO < 42.
China-route timing (Nov 30 latest order, 2 bd processing + 15 bd transit) is provisional and unproven under L-008: no CJ processing or transit time has been demonstrated for any of these SKUs.
Caps and hard fails: commodity-floor 1 caps at NO-GO and 2 caps at MAYBE (learned rule). A recipient-test fail means no GO. Failing L-002 on the only evidenced route is a hard fail.
"With waiver" = the hypothetical where the owner finds a CJ US-warehouse SKU at the stated threshold (or accepts a non-CJ US route). Timing then scores 4, and margin uses the US-stock cost.

| # | Candidate (route, price) | Margin raw (x2 in total) | Demand | Appeal raw (x2 in total) | Timing raw (x2 in total) | Floor raw (x2 in total) | Diff | Supplier | Creative | Risk raw (x2 in total) | **Total /70 (no waiver)** | **With waiver** | Landed % | BE ROAS | Latest safe order → selling days (launch Nov 10-15) | Verdict |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Magnetic rolling knife sharpener kit, CJ China, $44.99 | 1 | 5 | 4 | 2 | 2 | 2 | 2 | 5 | 2 | **36** | 44 (US SKU unit <= $9.69, margin 3, timing 4) | 45.9% China / 33.3% at threshold | 2.28 China / 1.77 US | China Nov 30 → 15-20 (8 after test); US Dec 9 → 24-29 | **NO-GO**: fails L-009 as sourced. MAYBE only in the hypothetical with a visible difference (capped by floor 2) |
| 2 | Men's slim RFID wallet, tracker pocket + clip, CJ China, $29.99 (single) / $34.99 | 2 | 5 | 4 | 2 | **1** | 2 | 2 | 3 | 4 | **38** | 46 (US SKU landed $8.80, margin 4, timing 4) | 39.6% / 34.0% China; 29.3% US | 2.01 China / 1.66 US | China Nov 30 → 15-20; US Dec 9 → 24-29 | **NO-GO** (floor 1 cap, with or without waiver) |
| 3 | Gift-swap (white-elephant) dice, China, $15.99 (2-pack $19.99) | 1 | 4 | 5 | 2 | **1** | 2 | 1 | 4 | 5 | **39** | n/a (no US route seen) | 38-43% / 42% | 2.08 | Nov 30, but parties are Dec 10-23 → 15-20 | **NO-GO** (add-on idea only) |
| 4 | Padded zip book sleeve, bulk MOQ 300, $24.99 | 3 | 2 | 4 | 2 | **1** | 2 | 1 | 3 | 5 | **38** | n/a | 32.8% (bulk price, unverified) | 1.77 | no dropship route → 0 | **NO-GO** |
| 5 | Sourdough baking kit, China, $39 | 1 | 5 | 4 | 2 | 2 | 2 | 2 | 4 | 3 | **37** | n/a | 57.7% | **3.13 (red flag > 2.5)** | Nov 30 → 15-20 | **NO-GO** |
| 6 | Aurora lamp, Doba US (round 1), $34.99 | 3 | 5 | **2** | 1 | **1** | 2 | 3 | 5 | 3 | **35** | 41 (Doba waiver, timing 4) | 29.1% | 1.65 | Dec 9 → 24-29 (waiver only) | **NO-GO** (owner rejected; floor 1; appeal 2 by owner's one-photo verdict) |
| 7 | Bluetooth scroll-ring remote, China, $24.99 | 1 | 4 | 4 | 2 | **1** | 1 | 2 | 5 | 2 | **32** | n/a | 46.1% | 2.32 | Nov 30 (factory lead 15-20 d means ~Nov 25) → 10-20 | **NO-GO** |

Totals check (no waiver):
- Row 1: 2+5+8+4+4+2+2+5+4 = 36. With waiver: 6+5+8+8+4+2+2+5+4 = 44.
- Row 2: 4+5+8+4+2+2+2+3+8 = 38. With waiver: 8+5+8+8+2+2+2+3+8 = 46.
- Row 3: 2+4+10+4+2+2+1+4+10 = 39.
- Row 4: 6+2+8+4+2+2+1+3+10 = 38.
- Row 5: 2+5+8+4+4+2+2+4+6 = 37.
- Row 6: 6+5+4+2+2+2+3+5+6 = 35. With waiver: 6+5+4+8+2+2+3+5+6 = 41.
- Row 7: 2+4+8+4+2+1+2+5+4 = 32.

Ranked by best attainable verdict, then score: the sharpener is first because it is the only one a quote could lift to a MAYBE; the dice score highest on paper but are capped.

**Checked by the validator and not proposed** (they fail before scoring):

| Idea | Evidence | Why not |
|---|---|---|
| Engraved / personalised men's wallet (a visible difference for the wallet) | TikTok Shop personalized-wallet page, 30 listings: top DUJO engraved 778 sold at $24.74; next 246, 137 and 123 sold; engraved floor $8.99 (39 sold) and $12.99 (measured as displayed, https://shop.tiktok.com/us/k/personalized-wallet). Etsy engraved wallets $26.99-37.79 (search snippets, https://www.etsy.com/listing/902342819) | Thin volume (L-004 fails on product-level proof); engraved floor $9-13 (L-009); no verified CJ per-order engraving through the API (L-006); China-only timing |
| Wallet with a tracker card included | TikTok tracker-wallet page: leather RFID bifold with tracker 924 sold at $45.49, ExtreLife 60 sold at $51.99; standalone tracker cards $10.87-31.74 (6.7K and 8.2K sold); ESR Geo 39.0K at $55.89 is a brand (measured, https://shop.tiktok.com/us/k/tracker-wallet) | Built-in battery, FCC and "Find My"/MFi trademark claims (excluded by the brief); thin volume for the bundle; the card alone sells at $11-32 |
| A $39-50 gift-box format (light, non-glass, non-cosmetic, non-battery) | TikTok christmas-gifts-for-men page, 31 listings: volume at $28-78 is massagers, trimmers, power banks, game consoles, heated gloves (battery), BellaVita fragrance sets and the hygiene box $45.49 (cosmetic), a whiskey glass (glass), cowboy boot slippers 55.3K at $77.99 (sizes), and branded TacticalTide/BULLCAPTAIN wallets (https://shop.tiktok.com/us/k/christmas-gifts-for-men). Amazon gifts-for-men top 10 (Jun 2026): towelettes, meat thermometer, candle-warmer lamp, nut basket (food), neck fan (battery), whiskey smoker (glass + torch), steel grill basket, bamboo boards (heavy) (https://www.asinsight.com/report/US/gifts-for-men, estimated) | Nothing in the format fits every gate. A kit we assemble from cheap generic parts would repeat the rejected nurse-kit pattern, and its parts would carry $5-15 floors |

## Per-candidate analysis
Common assumptions: Stripe 4.5% + $0.30 (assumed; a rounded planning rate for US 2.9% + ~1.5% cross-border/FX = 4.4%, plus $0.30); returns 5% of price (assumed); email $0.01 (assumed); China landed = unit x 1.35 + shipping + $1.00 (assumed duty 35% + clearance, memory insight 2026-10-14 duty stack). The CJ US-warehouse fee is $0.50 per parcel (knowledge/suppliers.md). The realistic Q4 cold CPA for a $25-45 gift on Meta is $18-30 (assumed), so every BE CPA below $20 means organic-only.

Fixed launch costs (any product, assumed):

| Item | Cost |
|---|---|
| Domain | $12 |
| Hosting (free tier) | $0 |
| Transactional email (free tier) | $0 |
| CJ account and API | $0 |
| Sample + test order | about $25-40 |
| **Total** | **about $37-52** |

The store build itself is owner time.

### 1. Magnetic rolling knife sharpener kit, $44.99: NO-GO (36/70; 44 hypothetical)

| Line | China (unit $9.00, 600 g) | US-stock threshold (hypothetical) |
|---|---|---|
| Unit + duty + ship + clearance | 9.00 + 3.15 + 7.50 + 1.00 = **20.65 (45.9%)** | unit <= 9.69 + 5.30 ship incl. $0.50 fee = **14.99 (33.3%)** |
| Stripe ($2.02 + $0.30) | 2.32 | 2.32 |
| Returns 5% | 2.25 | 2.25 |
| Email | 0.01 | 0.01 |
| **CM = BE CPA** | **19.76** | **25.42** |
| **BE ROAS** | **2.28** | **1.77** |

- **Demand: strong.**
  - TikTok "Newly Upgraded Rolling" set: 17.4K sold at $38.99 (measured, https://shop.tiktok.com/us/k/knife-sharpener).
  - Amazon AIERLIAN rolling kit ~3K/mo at $39.99, with 123.5K searches/wk for "knife sharpener" (estimated, https://www.asinsight.com/report/US/knife-sharpener).
  - Tumbler runs 110 active Meta ads (estimated, https://brandsearch.co/brands/tumblerware.com).
  - Searches peak Nov-Jan (estimated, [RankHero knife-sharpener](https://www.rankhero.com/keywords/knife-sharpener)).
- **Commodity floor, which I found myself:**
  - TikTok rolling kits sell at $18.98-19.99 (scout page above).
  - Walmart rolling diamond kits sell at $28.80-79.95; the cheapest identical-type kits are $28.80-29.99. Example: https://www.walmart.com/ip/18895208204, plus https://www.walmart.com/c/kp/rolling-knife-sharpener. These are measured (search snippet, unverified, 2026-10-26); the snippets are undated and Walmart pages are captcha-blocked.
  - Temu: not readable.
  - The floor is $19, not $10-15, so the score is 2 and the verdict is capped at MAYBE.
- **Recipient test:** passes. Three named recipients ("my dad", "my mom", "my brother-in-law who cooks"). The use moment is the knife sliding through paper or a tomato. The hook lands in 3 seconds.
- **IP risk (new):**
  - HORL 1993 GmbH appears to hold **US 12,157,204**, granted Dec 3, 2024 and filed Sep 8, 2021. It covers a method for producing a rolling sharpener (two rollers, a grip body and a shaft). A related application on the sharpener itself is also listed: publication 20250033165 (application 18/914,419, pending). Sources: [Justia inventor index](https://patents.justia.com/inventor/otmar-horl) and a search snippet.
  - **The patent number and claims are unverified.** I did not open the patent record. The constructed record URL is https://patents.google.com/patent/US12157204B2 (not opened). The lane file could not search patents. The owner gate in to-do 2 stays.
  - Core77 calls Tumbler a knock-off of HORL (https://www.core77.com/posts/117696/Smart-Design-The-Tumbler-Diamond-Rolling-Knife-Sharpener).
  - I found no lawsuit, and whether generic kits infringe is unverified. Risk score 2.
- **Supplier and timing:**
  - No CJ SKU was found, and no CJ US stock (web search returned only eBay and Walmart listings).
  - China latest order Nov 30 (assumed 2 + 15 bd), leaving 8 selling days after a Nov 10-22 organic test.
  - At 600 g the parcel lands at 46% of price, so it fails L-002.
- **Verdict:** NO-GO. It fails L-009 as sourced, because nothing visible separates it from the $19 kit. It becomes a MAYBE only in the hypothetical: a US SKU at the threshold **and** a visible difference. Even then it stays capped, with patent risk. I would not launch it for Christmas.

### 2. Men's slim RFID wallet (tracker pocket + money clip), $29.99 / $34.99: NO-GO (38/70; 46 with waiver, still capped)

| Line | China $29.99 (unit $4.50, 90 g) | China $34.99 | US-stock hypothetical $29.99 |
|---|---|---|---|
| Landed | 4.50 + 1.575 + 4.81 + 1.00 = **11.89 (39.6%)** | 11.89 (34.0%) | 4.50 + 0.50 + 3.80 = **8.80 (29.3%)** |
| Stripe | 1.65 | 1.87 | 1.65 |
| Returns | 1.50 | 1.75 | 1.50 |
| Email | 0.01 | 0.01 | 0.01 |
| **CM = BE CPA** | **14.94** | **19.47** | **18.03** |
| **BE ROAS** | **2.01** | **1.80** | **1.66** |

- **Demand: the strongest found** (TikTok, measured, https://shop.tiktok.com/us/k/mens-wallet).
  - GSOIAX 177.8K sold at $25.80.
  - TacticalTide 121.7K at $33.59, and TacticalTide tracker-pocket 34.5K at $32.99.
  - Amazon B0F8QJFWK5 ($29.99, tracker/clip) shows different figures on two asinsight pages. The [mens-wallet page](https://www.asinsight.com/report/US/mens-wallet) (Jul 2026) gives ~6K/mo. The [airtag-wallet page](https://www.asinsight.com/report/US/airtag-wallet) (Jun 2026) gives ~4K/mo, falling 40-50% MoM. Both are estimated.
  - [RankHero mens-wallet](https://www.rankhero.com/keywords/mens-wallet): Dec 550K vs Jul 201K (estimated).
- **Commodity floor, re-checked after QA r1.** Titles are quoted verbatim from https://shop.tiktok.com/us/k/tracker-wallet (measured as displayed, 2026-10-26). These are tracker-pocket wallets:
  - **sohochic, $14.99, 15.9K sold** ([listing](https://shop.tiktok.com/us/pdp/smart-wallet-for-airtag-leather-rfid-blocking-slim-design/1731176224138826211)). Title: "Men's RFID Theft-Proof PU Leather Slim Wallet - PU Card Holder, RFID Organizer, AirTag Holder, ID Window, Cash Slot…". The URL slug is "smart-wallet-for-airtag". The useful-daily lane said this listing was not tracker-specific; the title shows it is. This file overrides the useful-daily lane on this listing.
  - **Carbon-fibre bifold, $10.98 (list $27.00), 15 sold** ([listing](https://shop.tiktok.com/us/pdp/1732757710225576164)). Title: "Men's Airtag Wallet - Slim RFID Blocking Carbon Fiber Bifold Wallet with Pop Up Card Holder, ID Window & Money Clip". This is our exact spec: tracker pocket, money clip, RFID.
  - Miyozi metal pop-up wallet with AirTag holder and money clip, $16.99, 28 sold ([listing](https://shop.tiktok.com/us/pdp/miyozi-slim-magnetic-flip-airtag-holder-10-slots-rfid-safe/1732736516075524318)).
  - **Withdrawn:** the $12.39 carbon wallet (3.3K sold). Its title mentions no tracker.
  - Walmart's leather slim money-clip wallet at $13.99 is shown for context only: no tracker pocket confirmed. Measured (search snippet, unverified, 2026-10-26), https://www.walmart.com/ip/16660865972.

  So the cheapest identical tracker-pocket wallet is $10.98 (15 sold), and the $14.99 one has volume (15.9K sold). Our only edge would be copy. **Floor = 1, so the wallet is capped at NO-GO regardless of margin. The verdict and scores are unchanged.** The TacticalTide volume at $33 shows that TikTok buyers pay for content and a store name, but L-009 deliberately rules out that kind of edge.
- **Recipient test:** passes the first three cells (dad, husband, brother; daily use; fat wallet vs slim wallet in 3 seconds). It fails the visible-differentiation cell.
- **Risks:**
  - "RFID blocking" claims must be supplier-documented.
  - Never say "AirTag" in the title, the listing or ads (Apple trademark). Say "tracker pocket (tracker sold separately)".
- **Verdict:** NO-GO this season. Hold as a **Father's Day 2027 candidate** (`assumed` fit) if we can own a visible difference, such as our own engraved design on a small run. A custom run is an L-006 exception and needs owner approval of the spend.

### 3. Gift-swap (white-elephant) dice, $15.99 / $19.99 2-pack: NO-GO (39/70)
- **Landed:** $6.12-6.82 (38-43%) on 1 die = unit $1.20 + duty $0.42 + shipping $3.50-4.20 + clearance $1.00. The 2-pack lands at $8.44 (42%).
- **CM at $15.99:** 15.99 − 6.47 (the midpoint of the $6.12-6.82 landed range) − 1.02 − 0.80 − 0.01 = **$7.69**, BE ROAS **2.08**. CM this low cannot carry paid traffic.
- **Demand:**
  - TikTok gift-exchange dice: 17.4K sold at $15.99 (measured, scout).
  - Searches: [RankHero white-elephant-gifts](https://www.rankhero.com/keywords/white-elephant-gifts) Dec 246K; [RankHero secret-santa-gifts](https://www.rankhero.com/keywords/secret-santa-gifts) Dec 550K (both estimated).
  - Walmart has 9+ listings.
- **Floor:** Walmart $3.46-9.24 per die (single die $3.46-5.33, the rest are higher-priced listings; 3-packs up to $13.99). Measured (search snippet, unverified, scout snapshot 2026-10-26), https://www.walmart.com/ip/18764920588. Floor score 1.
- **Supplier:** no confirmed source for the 12-sided gift-exchange die (supplier score 1).
- **Timing:** gift exchanges run Dec 10-23. With a Nov 30 China cutoff, orders after Nov 30 arrive after the parties.
- **Recipient test and appeal:** best in the field (appeal 5).
- **Verdict:** NO-GO as a product. Keep as a future add-on or a free gift with purchase, never as the hero.

### 4. Padded zip book sleeve, $24.99: NO-GO (38/70)
- **Landed:** 2.00 × 1.35 + 4.50 shipping (~150 g, assumed) + 1.00 = **$8.20 (32.8%)**. That uses a bulk MOQ-300 price ($2.00), so there is no dropship route.
- **CM:** 24.99 − 8.20 − 1.42 − 1.25 − 0.01 = $14.11, BE ROAS 1.77.
- **Demand:** thin. Top TikTok listing is 930 sold; Amazon gets 351 searches/wk.
- **Floor:** $5.19 plain on TikTok.
- **Verdict:** NO-GO. A difference would need our own print, which means a custom run.

### 5. Sourdough baking kit, $39: NO-GO (37/70)
- **Landed:** 11.11 (midpoint of the $10.80-11.42 Chengdu Olai set) × 1.35 + 6.50 shipping (~600 g, assumed) + 1.00 = **$22.50 (57.7%)**.
- **CM:** 39 − 22.50 − 2.06 − 1.95 − 0.01 = **$12.48**, BE ROAS **3.13, which is above the 2.5 red flag.**
- **Demand:** strong (Dec 90.5K searches per [RankHero sourdough-starter-kit](https://www.rankhero.com/keywords/sourdough-starter-kit), estimated; Amazon kits 10K/mo, TikTok 25.8K at $56.89).
- **Floor:** a close equivalent sells at $19.99 on Amazon. Floor score 2.
- **Compliance:** food-contact items (banneton, scraper) need food-contact-safe materials. Rattan can also mould in transit.
- **Verdict:** NO-GO.

### 6. Aurora lamp, Doba US stock (round 1), $34.99: NO-GO (35/70; 41 with waiver)
- **Economics unchanged from round 1:** landed $10.17 (29.1%, estimated from a Doba margin hint), CM $21.19, BE ROAS 1.65, latest order Dec 9.
- **Re-scored on L-009:**
  - The identical lamp sells at $12.99 on TikTok (DESUNIC 22.6K sold) and $13.74 on eBay. Floor score 1.
  - The owner's Gate A verdict ("who will want that") puts appeal at 2. A 1-2 appeal is NO-GO.
- **Verdict:** NO-GO and closed.

### 7. Bluetooth scroll-ring remote, $24.99: NO-GO (32/70)
- **Landed:** $11.52 (46.1%).
- **CM:** 24.99 − 11.52 − 1.42 − 1.25 − 0.01 = $10.79, BE ROAS 2.32.
- **Floor:** $5.69 with charging case on Walmart. Floor score 1.
- **Compliance:** Li-ion cell and FCC ID both unverified.
- **Demand trend:** Amazon page-turner sales are down 16.7-33.3% MoM.
- **Verdict:** NO-GO.

## Recommendation
**Path (b), with a free check embedded: stop chasing Christmas 2026 and build the store, brand shell and channels now. Launch for a 2027 gifting date that leaves enough time for real differentiation.**

Why not (a) or (c): every candidate fails on L-009 or L-004, not on cost. A quote can only change cost and timing, so a quote test cannot produce a GO. The single exception is the sharpener's hypothetical, and that is a capped MAYBE with patent risk. Running quote tests "in parallel" would spend the owner's attention on a result that cannot pass. The one free check below costs about 20 minutes, because the owner has to open the CJ account for the API anyway.

**What to expect:** no Christmas 2026 product. The Christmas season becomes the build and warm-up period:
- the custom site;
- Stripe live in the owner's country;
- the CJ API with order creation and a tracking webhook, tested with one real cheap order;
- TikTok and IG accounts with 4-6 weeks of posting history.

All of that is required for any launch, and none of it is wasted.

**2027 launch windows (dates are fixed facts; lead times assumed):**

| Occasion | Date | China-route latest safe order | Notes | Verdict |
|---|---|---|---|---|
| Valentine's | Sun Feb 14, 2027 | ~Jan 15 (assumed). The SKU must already be in CJ warehouse stock because of CNY (Feb 6; factories closed ~Jan 20-Feb 28, estimated, https://www.epicsourcing.co.uk/post/chinese-new-year-2027-uk-importers-factory-deadline-stock-planning-guide) | Launch Jan 2, last order Jan 15: **13 selling days**. Round-1 satin set is NO-GO under the floor-1 cap (probably the case: Kitsch and W7); it becomes MAYBE only at **price >= $42 with a CJ SKU <= $5.18 (with ~$6.00 shipping, assumed)** (or >= $42.72 on the Daranfang route). Under L-009 it is probably floor 1 (Kitsch, W7) | Optional, fragile; scout only if the owner wants it |
| Mother's Day | Sun May 9, 2027 | **Apr 14** (assumed 17 bd). Counted back from a Fri May 7 delivery target with May 6 = day 1, the same method that gives Nov 30 for Dec 23. Counting May 7 as day 1 gives Apr 15 | Post-CNY sourcing in March; time for samples and an owned design | **Primary target** |
| Father's Day | Sun Jun 20, 2027 | **May 25** (assumed 17 bd). Counted from a Fri Jun 18 target with Jun 17 = day 1, skipping the US Memorial Day holiday (May 31). Without skipping it, May 26 | Wallet and sharpener fit the occasion (`assumed`, not checked against Father's Day sales data). An owned visible difference is plannable: our engraved design on a custom run, or a bundle we pack (custom run or POD is an L-006 exception and needs owner approval) | **Primary target** |
| Christmas 2027 | Dec 25, 2027 | Source from Aug 2027 | Book nook on HOLD (round 1); white-elephant demand (Dec 246K) gives time for an owned funny design | Plan in Aug 2027 |

**Positioning lesson for the next scout (for the brief):** proven generic products always have a cheaper identical listing. Visible differentiation therefore has to be owned: our own print or engraving, our own design detail, or a bundle that reads as one natural gift. Each of these needs either a small paid custom run or a POD partner with an API. Both are an **L-006 exception, owner approval required**. The owner should decide which of the two levers is allowed before the next scout runs. Without one of them, L-009 + L-002 + L-004 leave almost nothing to sell.

**Target price:** n/a (no GO).

**Bundle and upsell idea (for later):** gift-exchange dice as a $5-7 add-on to a white-elephant-friendly hero next Christmas.

## Owner to-do (exact, with dates)
1. **By Fri Oct 30 (free, about 20 min):** open the free CJ account; it is needed for the API anyway. Use the US-warehouse filter (the "Ship from: US" / US Warehouse option on CJ listings, per the CJ tutorial https://blog.cjdropshipping.cn/detail/1332244104523776001, dated 2020) and search:
   - "rolling knife sharpener" and "magnetic knife sharpener";
   - "slim wallet money clip" and "tracker wallet";
   - "gift exchange dice";
   - "scroll ring remote".

   For any hit, record SKU, US stock quantity, unit price, US shipping quote to ZIP 60601, processing days and weight, and take screenshots.
2. **Mon Nov 2: kill date for Christmas 2026.** Christmas continues only if a rolling sharpener meets all of these:
   - unit + US shipping including the $0.50 fee <= **$14.99**;
   - stock >= 50;
   - the kit **visibly** differs from the $19 kit (e.g. includes a strop or a 3000-grit disc);
   - the owner accepts the HORL patent risk in writing. US 12,157,204 is unverified: the number came from a search snippet and the record was not opened. Check https://patents.google.com/patent/US12157204B2 before deciding.

   Even then it is a MAYBE (44/70) for the owner to decide on. Otherwise Christmas 2026 is closed. Nothing else found can pass.
3. **Nov 2-Dec 15:** build the custom site, connect Stripe, integrate the CJ API (order create plus tracking), and buy a neutral domain ($12). Place one real cheap CJ test order to a US address to measure processing and transit. Open the TikTok and IG accounts and post 3-5 times a week (behind-the-scenes and gift-guide content, no product claims).
4. **By Mon Nov 23:** decide which differentiation lever is allowed:
   - (i) a small owned-design custom run (state a $ cap, e.g. $150-250 from the $500). This is an L-006 exception, owner approval required; or
   - (ii) a POD partner with an API. This is an L-006 exception, owner approval required; or
   - (iii) neither, accepting that the shortlist will stay very thin.

   Also say whether Valentine's is wanted (fragile because of CNY) or whether to go straight to Mother's Day / Father's Day.
5. **By Dec 5 (only if Valentine's is wanted):** the scout and validator deliver a Valentine's pick that is already in CJ warehouse stock. Order the sample by Dec 10. Without a pick by Dec 5, skip Valentine's.

## What would make us kill it later
- **Christmas 2026:** closed on Nov 2 unless to-do 2 passes in full. If the sharpener does pass and the owner proceeds, any of these kills it:
  - the measured CJ US delivery is more than 7 bd;
  - the sample does not match the listing;
  - organic results by Nov 22 are under 10,000 views across 9+ posts, or 0 add-to-carts;
  - there is any patent or takedown notice.
- **2027 product (Mother's or Father's Day):**
  - kill before the sample if the cheapest identical listing is within $10 of our price and the difference does not show in the photo;
  - kill if landed is more than 1/3 of price on a real CJ quote;
  - kill if there are fewer than 3 product-level sales signals.
- **Organic test:** fewer than 150 store visits or 0 add-to-carts after 9+ posts means no paid spend.
- **Paid:** 3x BE CPA spent with 0 sales means stop.

## Sources
- TikTok Shop listings used for the wallet floor (measured as displayed, 2026-10-26):
  - https://shop.tiktok.com/us/pdp/smart-wallet-for-airtag-leather-rfid-blocking-slim-design/1731176224138826211 (sohochic, $14.99, 15.9K sold)
  - https://shop.tiktok.com/us/pdp/1732757710225576164 (carbon-fibre bifold, $10.98, 15 sold)
  - https://shop.tiktok.com/us/pdp/miyozi-slim-magnetic-flip-airtag-holder-10-slots-rfid-safe/1732736516075524318 (Miyozi, $16.99, 28 sold)
- TikTok Shop public pages (measured as displayed, 2026-10-26): https://shop.tiktok.com/us/k/tracker-wallet (validator-only page, not in the lane sources) ; https://shop.tiktok.com/us/k/personalized-wallet ; https://shop.tiktok.com/us/k/christmas-gifts-for-men ; https://shop.tiktok.com/us/k/gender-neutral-gifts-white-elephant ; plus the lane pages cited (mens-wallet, knife-sharpener, tiktok-scrolling-remote, sourdough-starter-kit, book-sleeve, best-male-white-elephant-gifts, northern-lights-projector).
- asinsight (estimated): https://www.asinsight.com/report/US/gifts-for-men ; https://www.asinsight.com/report/US/knife-sharpener ; https://www.asinsight.com/report/US/mens-wallet ; https://www.asinsight.com/report/US/airtag-wallet ; personalized-wallets-for-men returned 404.
- Walmart (measured, search snippet, unverified, 2026-10-26; pages captcha-blocked):
  - https://www.walmart.com/ip/16660865972: wallet $13.99, context only, no tracker pocket confirmed.
  - https://www.walmart.com/ip/18895208204 and https://www.walmart.com/c/kp/rolling-knife-sharpener: rolling kits $28.80-79.95; the cheapest identical-type kits are $28.80-29.99.
  - https://www.walmart.com/ip/18764920588: dice $3.46-9.24 per die.
- RankHero (estimated): https://www.rankhero.com/keywords/white-elephant-gifts ; https://www.rankhero.com/keywords/secret-santa-gifts ; https://www.rankhero.com/keywords/mens-wallet ; https://www.rankhero.com/keywords/knife-sharpener ; https://www.rankhero.com/keywords/sourdough-starter-kit
- Engraved wallets: https://www.etsy.com/listing/902342819 ; https://divotiusa.com/bisondale-personalized-wallet-for-men-custom-engraved-leather-rfid-blocking-bifold-id-window-11-card-slots-gift-for-him-color
- IP: https://patents.justia.com/inventor/otmar-horl (US 12,157,204 and publication 20250033165 via search snippet; unverified) ; https://patents.google.com/patent/US12157204B2 (constructed URL, not opened) ; https://www.core77.com/posts/117696/Smart-Design-The-Tumbler-Diamond-Rolling-Knife-Sharpener ; https://brandsearch.co/brands/tumblerware.com
- CJ US warehouse: https://blog.cjdropshipping.cn/detail/1332244104523776001 (2020 tutorial); https://hustlegotreal.com/dropshipping-suppliers/us/supplier/cj-dropshipping (US stock on selected SKUs only). No CJ US SKU found for any candidate.
- CNY 2027: https://www.epicsourcing.co.uk/post/chinese-new-year-2027-uk-importers-factory-deadline-stock-planning-guide ; https://www.sekologistics.com/en/resource-hub/knowledge-hub/lunar-new-year-complete-supply-chain-planning-guide-for-asia-sourcing/ ; https://www.dripcapital.com/resources/blog/chinese-new-year-2027
- Round 1 economics: products/scout-xmas-20261026/02-validation.md. Lane data: the three 01-scouting files in this folder.
