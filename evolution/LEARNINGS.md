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

### L-002: Pass a candidate on margin only if its break-even ROAS (net price excl. VAT ÷ contribution margin before ads) is ≤ 2.2 and its contribution margin before ads is ≥ EUR 12 per order.
- Applies to: product-scout, product-validator, growth-strategist, ads-manager
- Why: FB-007 (owner-approved 2026-10-27): the 1/3-landed rule plus US duty killed every candidate across ~100 ideas. Contribution margin = net price − landed cost (unit + shipping to the customer + packaging + duty/handling only for non-EU stock) − payment fees − returns allowance − per-order service costs. VAT is never margin: net price = VAT-inclusive price ÷ (1 + VAT rate). This typically allows landed cost up to about 40% of net price. In practice a single item below about EUR 29.90 VAT-inclusive cannot reach EUR 12 contribution (estimated), so cheaper items pass only as bundles. Use the cost block in "Reference: EU/DE economics" below. Ad platforms must receive the same net value (store-builder) so platform ROAS is comparable to this threshold.
- Confidence: high
- Added: seed; revised 2026-10-27 (CL-007)
- Superseded: "Target a landed cost (product + shipping) of at most one third of the selling price." (seed, medium; superseded by CL-007)

### L-003: Never promise shipping times the supplier hasn't demonstrated.
- Applies to: brand-strategist, growth-strategist, copywriter, creative-producer, store-builder, social-manager, ads-manager
- Why: Seed rule. Late deliveries cause chargebacks and payment processor holds. FB-004: the brand stage put a shipping-window claim in its file, so the rule now covers every agent that writes customer-facing words.
- Confidence: high
- Added: seed

### L-004: Only pursue products with at least three independent proof-of-sales signals; never bet on unproven inventions.
- Applies to: product-scout, product-validator
- Why: FB-001 — owner wants products proven to sell. FB-007: the signals may come from the target market (Amazon.de, Otto, Kaufland, idealo, TikTok Shop DE, EU Meta Ad Library) or from another market (e.g. US) when the product is not yet well served in the target market (market arbitrage); an arbitrage pick must also show that gap with target-market sources (few/no German-language sellers, thin Amazon.de/idealo results).
- Confidence: high
- Added: 2026-10-26 (CL-001); refined 2026-10-27 (CL-007)

### L-005: Differentiate through positioning that sharpens a natural, obvious angle (gift, occasion, feeling, self-treat) for a broad buyer, never through an invented micro-niche, and pick only products a normal shopper understands and wants on sight without explanation; the store is secondary to marketing.
- Applies to: all (especially product-scout, product-validator, growth-strategist, brand-strategist)
- Why: FB-001 — owner: "website is the easiest part, marketing is the hardest." FB-005 — owner killed the night-shift-nurse reset kit at Gate B as contrived ("leave this nurse care kit and the other bs"); wants products people buy as a Christmas present or for themselves for the holiday feel. Test: if the product only makes sense once you explain who it's "for", reject it. "Wants on sight" is tested concretely by L-009.
- Confidence: high
- Added: 2026-10-26 (CL-001); refined 2026-10-26 (CL-005, CL-006)

### L-006: Plan every store as a custom-coded, supplier-agnostic site (Stripe checkout plus the payment methods the market expects) and source only from the supplier tiers below, stating each supplier's integration cost; never assume Shopify, its apps, plan costs or CSV imports unless the owner asks.
- Applies to: store-builder, product-scout, product-validator, copywriter, compliance-officer, ads-manager, growth-strategist, orchestrator
- Why: FB-003 — owner: "I will not use Shopify. I'll create my own custom website…" (custom site stays). FB-007 — "the distributor of it who can handle everything": CJ is no longer the only supplier. Tiers, no exception approval needed: (1) CJdropshipping, the default, preferring stock in a CJ EU/DE warehouse where a listed SKU shows it (whether CJ has EU/DE stock for a SKU: to verify per SKU); (2) EU-stock dropship suppliers such as BigBuy (plan cost, API access and DE delivery times: to verify); (3) EU print-on-demand with a public API for our own designs (e.g. Printful, Printify EU providers, Gelato: to verify per product). Anything outside these tiers (US-only routes like Doba, Shopify-only apps, manual-only suppliers) still needs owner approval at a gate. Prefer suppliers with a public order/tracking API. Integration cost = subscription/plan fees + one-off build effort (API or manual) + per-order fees, stated per supplier; every additional supplier in one store adds build and support work.
- Confidence: high
- Added: 2026-10-26 (CL-003); revised 2026-10-27 (CL-007)
- Superseded: "Plan every store as a custom-coded site with Stripe payments and CJdropshipping API fulfillment; never assume Shopify, its apps, plan costs or CSV imports unless the owner asks." (CL-003; superseded by CL-007)

### L-007: When fixing a QA issue list, re-check every section you changed against your quality bar and these rules before returning, so a fix never introduces a new blocker.
- Applies to: all agents that produce stage files
- Why: FB-004 / memory/runs.md — the brand stage's fix rounds introduced new blockers (shipping-window claim, unpriced packaging, overclaimed name uniqueness), costing 3 QA rounds plus an opus escalation; the validator also failed its first QA. Seen on 1 product, 2 agents.
- Confidence: medium
- Added: 2026-10-26 (CL-004)

### L-008: Score every candidate on timing: prefer evergreen products or a demand peak 6–10 weeks away, and count delivery as feasible only when the supplier has demonstrated ≤ 5 business days (processing + transit) to Germany from EU stock; non-EU stock must still demonstrably arrive before any occasion with buffer for the organic test, otherwise reject it or hold it for its next season.
- Applies to: product-scout, product-validator, growth-strategist, ads-manager
- Why: FB-005 — owner wants seasonal/emotional demand and delivery-by-date feasibility weighted heavily. FB-007 — drop "Christmas or nothing": evergreen or the next peak 6–10 weeks out (Q4/winter, then Valentine's/spring, Mother's/Father's Day). "Demonstrated" = a supplier-published SKU-level delivery figure or a test parcel, labelled measured/estimated. Delivery dates are internal planning numbers; customer-facing promises still follow L-003.
- Confidence: high
- Added: 2026-10-26 (CL-005); revised 2026-10-27 (CL-007)
- Superseded: "…its demand peak (season, holiday, gifting window) must still be ahead, and the supplier's demonstrated processing + transit time (prefer stock already in a CJ/US warehouse) must deliver before the occasion's date with buffer for the organic test; otherwise reject it or hold it for its next season." (CL-005; superseded by CL-007)

### L-009: Shortlist a product only if it passes the hard recipient test (3 named recipients or users, it gets used or laughed at, a hook that lands in under 3 seconds per L-001, and it makes sense without explaining per L-005), then score differentiation 1–5 against the cheapest identical listing instead of rejecting on it.
- Applies to: product-scout, product-validator, growth-strategist
- Why: FB-006 — owner rejected the aurora lamp at Gate A despite passing numbers: "I don't know who will want that. I want something which can be marketed and the customers would actually want it and use it." Recipients are named people ("my dad", "a coworker for Secret Santa"), not segments; for self-purchase products the buyer may count once ("me, my sister, my dad"). Useful or funny both pass; a decoration nobody asked for fails. FB-007 — a cheaper identical listing is a risk, not an automatic reject, if we control a reason to pick us: a bundle that reads as one product, a better offer, a guarantee, strong video content, or our own design (print-on-demand). Score: 5 = no identical listing near our price, or a difference visible in the photo; 3 = identical cheaper listing exists but we control one lever above; 1 = identical and much cheaper (mass-market floor around EUR 10–15) with no lever we control, which stays a NO-GO. Packaging or a gift box alone is still not a lever. Price band EUR 15–80 VAT-inclusive, bundles allowed (subject to L-002).
- Confidence: high
- Added: 2026-10-26 (CL-006); revised 2026-10-27 (CL-007)
- Superseded: "Shortlist a product only if it passes the recipient test (…) and it is visibly different from the cheapest identical listing; penalise commodities with a $10–15 mass-market floor and no differentiation." Price band "$19–49" replaced by EUR 15–80. (CL-006; superseded by CL-007)

### L-010: Default every product to the German market (DACH: DE + AT, CH later) with German customer-facing content, EUR prices shown VAT-inclusive, and German/EU law, unless the product's STATUS.md names another market.
- Applies to: all
- Why: FB-007 — owner: "I can manage everything in Europe… I speak fluent German… And I am Germany." Replaces the US default (MEMORY decision 2026-10-26). Internal stage files may stay in English; everything a customer or platform sees (store, emails, policies, ads, captions, video text) is German, with the owner proofreading. US facts in older MEMORY Insights (US duty, de minimis, Stripe cross-border rate, CJ US warehouse) do not apply to DE.
- Confidence: high
- Added: 2026-10-27 (CL-007)

---

## Reference: EU/DE economics and compliance (FB-007, CL-007)

Shared fact block for L-002, L-006, L-008 and L-010, so agents don't keep their own copies.
Items marked **(to verify)** are not confirmed for the current date: check an official source and
cite it before relying on the number, and label it `assumed` until then.

**Landed cost and margin (per order)**
- EU stock (goods already in the EU): landed = unit + shipping to DE + packaging/insert. No customs duty.
- Non-EU stock (China-direct): landed = unit + shipping + customs duty + carrier/customs handling fees.
  The EUR 150 low-value duty exemption is being abolished; an interim flat customs duty of about EUR 3 per item
  in low-value parcels from 2026-07-01 and a separate EU handling fee have been reported, and some member states
  add national fees **(to verify: amounts, start dates, "per item" definition, DE-specific fees)**. Import VAT is
  due on all imports (IOSS for consignments ≤ EUR 150).
- VAT: Germany 19% standard (7% reduced), Austria 20%, Bulgaria 20%. Prices to consumers are shown VAT-inclusive;
  net price = price ÷ 1.19 for DE. Cross-border EU B2C sales above EUR 10,000/year EU-wide are taxed at the
  destination rate, usually declared through the OSS. Which VAT applies below the threshold, registration, and
  small-business rules depend on where the owner's business is registered (Bulgaria vs Germany, open in the Owner
  profile) **(to verify with a tax adviser)**.
- Payment fees: EEA cards via Stripe are cheaper than the 4.5% + $0.30 US cross-border figure used earlier;
  take the rate from stripe.com pricing for the owner's country; PayPal and Klarna rates likewise
  **(to verify; until then assume 2.5% + EUR 0.30 per order as a planning placeholder, labelled assumed)**.
- Returns allowance: 14-day statutory withdrawal right; plan 8% of net price **(assumed)** until measured
  (higher than the old 5% US assumption). The customer bears return shipping only if the Widerrufsbelehrung says so.
- Supplier integration cost (L-006): plan fees + build effort + per-order fees, per supplier.

**Compliance checklist for DE (compliance-officer owns it; not legal advice)**
- Impressum (§ 5 DDG), Datenschutzerklärung (GDPR), cookie/pixel consent before non-essential tracking (TDDDG),
  AGB, Widerrufsbelehrung + Muster-Widerrufsformular (14 days), order button "zahlungspflichtig bestellen"
  (§ 312j BGB). EU withdrawal-function button required for online contracts from 2026-06-19 **(to verify)**.
  The EU ODR-platform link is no longer required after the platform closed in July 2025 **(to verify)**.
- Price display (PAngV): total price incl. VAT, shipping costs stated near the price, unit price (Grundpreis) for
  goods sold by weight/volume/length, and any price reduction compared with the lowest price of the prior 30 days.
- UWG: no misleading claims, no fake scarcity; reviews must state whether and how they are verified; paid creator
  content labelled "Werbung"/"Anzeige" (not only #ad). Competitor warning letters (Abmahnung) are a real cost risk.
- No health or medical claims (HWG; EU Health Claims Regulation for food).
- GPSR (EU 2023/988): an EU-based responsible economic operator for every product; listings show manufacturer,
  EU responsible person, product identifier and German safety information.
- Packaging (VerpackG): LUCID registration and a dual-system licence before selling packaged goods to DE;
  for dropshipping, who is the obliged party for supplier packaging **(to verify per supplier)**.
- Electrical/electronic goods: WEEE/ElektroG registration with stiftung ear (authorised representative if not
  established in DE); batteries: BattDG registration **(to verify)**; CE marking (LVD/EMC/RED; toys: Toy Safety).
  Textiles: fibre-composition labelling.
- Trademarks: DPMAregister (DE), EUIPO eSearch plus (EU marks cover DE), WIPO Global Brand Database / TMview.

**DE research sources**: Amazon.de ("bought in past month" badges, bestsellers), Otto, Kaufland, idealo (cheapest
identical listing and offer count), Google Trends geo=DE, TikTok Shop DE (launched 2025 **(to verify)**: seller
requirements), the Meta Ad Library (shows all ads delivered in the EU with start dates and EU reach), TikTok
Commercial Content Library.
