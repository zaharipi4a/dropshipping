# Shared Memory

The long-term memory of the studio. Every agent reads this before working and
appends to it after. **Append only** in the logs; the evolver may compact old
entries into `evolution/LEARNINGS.md`.

---

## Owner profile

Fill in once; agents tailor everything to it.

- Target markets / ship-to countries: _TBD (e.g. US, UK, EU)_
- Store language(s): _TBD_
- Starting budget (product samples + store + ads): _TBD_
- Daily ad budget ceiling for tests: _TBD_
- Preferred platform: _Shopify (default) / custom landing page_
- Suppliers / apps already in use: _TBD (e.g. AutoDS, DSers, CJdropshipping, Zendrop)_
- Channels to market on: _TBD (TikTok, Instagram, Facebook, Pinterest, YouTube Shorts)_
- Hard no's (niches, product types): _TBD_
- Brand taste (likes / dislikes): _TBD_

---

## Portfolio

| Slug | Product | Stage | Status | Last update |
|---|---|---|---|---|
| _none yet_ | | | | |

Stage = 0–9 as defined in `CLAUDE.md`. Status = `active`, `waiting-on-human`,
`paused`, `killed`, `scaling`.

---

## Decision log

Format: `- YYYY-MM-DD [slug|global] [agent] DECISION — reason`

---

## Insights

Things learned about markets, products, suppliers, audiences, and creatives that
are worth reusing. Format: `- YYYY-MM-DD [agent] INSIGHT — evidence`

---

## Rejected ideas

Products/niches already evaluated and dropped, so nobody re-researches them.
Format: `- YYYY-MM-DD <product/niche> — why rejected`
