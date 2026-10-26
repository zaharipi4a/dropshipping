# Dropshipping Agent Studio

A team of Claude Code agents that finds proven products, positions them for a
segment nobody owns yet, brands them, builds the store, and runs the marketing,
improving itself every time you give feedback or real numbers come in.

## The strategy

1. **Don't guess. Copy what's proven.** We only shortlist products with 3+
   independent proof-of-sales signals: ads running 30+ days, several stores selling
   it, marketplace sales velocity, TikTok Shop sold counts, stable search demand.
2. **Win on positioning, not product.** Take the proven product and own a segment
   the current sellers ignore: "compression socks" → "compression socks for
   night-shift nurses", bundled as a shift-survival kit, in their language, with
   creatives that look like their world. Same supplier, different market.
3. **Marketing is the work.** The store is a one-time build. The ongoing work is a
   loop of angles → creatives → organic test → paid scale → analysis, every week.
4. **The system learns.** Every refinement you give and every result that comes back
   becomes a rule that changes how the agents behave next time.

## Architecture

```
                          ┌──────────────────────────────┐
         you ───────────▶ │  ORCHESTRATOR  (/pipeline)    │  main Claude session
                          │  briefs agents, tracks state, │
                          │  stops at approval gates      │
                          └──────────────┬───────────────┘
        ┌────────────┬──────────────┬────┴─────┬──────────────┬─────────────┐
        ▼            ▼              ▼          ▼              ▼             ▼
  product-scout  product-      brand-      growth-      copywriter ∥    store-builder ∥
  (proven +      validator     strategist  strategist   creative-       social-manager
   segment gap)  (economics,   (name,      (angles,     producer        (store, socials)
                  risk)        identity)   channels)    (copy, video)
                     │             │                                         │
                  GATE A        GATE B                                   ads-manager
                                                                             │
                                                                          GATE C
                                                                             │
                                            ┌──────── weekly loop ───────────┤
                                            ▼                                ▼
                                     performance-analyst ──▶ creative refresh + ads update
                                            │
                     memory/feedback-inbox.md ◀── /feedback (you)
                                            │
                                            ▼
                                         EVOLVER ──▶ evolution/LEARNINGS.md (global rules)
                                                 ──▶ each agent's "Learned rules"
                                                 ──▶ evolution/CHANGELOG.md (audit trail)
```

### Three layers

| Layer | Files | What it is |
|---|---|---|
| **Agents** (workers) | `.claude/agents/*.md` | 11 specialists. Each one is a prompt with its role, what to read, its process, its output file and its quality bar. They run as Claude Code subagents with their own context window, so the main session stays clean. |
| **Skills** (commands) | `.claude/skills/*/SKILL.md` | What you type: `/pipeline`, `/feedback`, `/evolve`, `/review`. `/pipeline` is the orchestrator. |
| **Memory** (state) | `memory/`, `evolution/`, `products/` | Plain markdown. Agents start with no memory of their own, so everything they know comes from these files. |

**Why the orchestrator is a skill and not an agent:** Claude Code subagents can't
start other subagents. The orchestrator runs in your main session so it can
dispatch specialists (including two at once) and talk to you at the gates.

### The agents

| # | Agent | Job | Output |
|---|---|---|---|
| 1 | `product-scout` | Finds proven sellers + the segment gap | `01-scouting.md` |
| 2 | `product-validator` | Full unit economics, break-even ROAS, supplier and legal risk, go/no-go | `02-validation.md` |
| 3 | `brand-strategist` | Avatar, name (domain/handle checks), offer, voice, visual identity | `03-brand.md` |
| 4 | `growth-strategist` | **Marketing brain:** where the segment lives, angle bank, channels, organic-first test, creators/affiliates, weekly loop | `04-growth-plan.md` |
| 5 | `copywriter` | Product page, policies, email flows, ad copy, written per angle | `05-copy.md` |
| 5 | `creative-producer` | Video scripts, hooks, shot lists, UGC briefs, AI image/video prompts, edits | `06-creatives.md` |
| 6 | `store-builder` | Shopify setup kit + product CSV, or a coded landing page | `07-store.md`, `store/` |
| 6 | `social-manager` | Account kits, 30-day calendar, engagement and influencer outreach | `08-social.md` |
| 7 | `ads-manager` | Tracking, campaign structure, test matrix, numeric kill/scale rules, policy check | `09-ads.md` |
| 9 | `performance-analyst` | Funnel diagnosis, per-ad verdicts, P&L, learnings | `11-performance.md` |
| ∞ | `evolver` | Turns feedback and learnings into rule and prompt changes | `evolution/*` |

### Memory and how the system evolves

- **`memory/MEMORY.md`**: the shared brain. It holds your owner profile (budget,
  markets, taste), the portfolio of products and their stage, the decision log, reusable
  insights, and rejected ideas so nothing gets researched twice. Every agent reads it
  first and appends to it at the end.
- **`products/<slug>/`**: one folder per product, one numbered file per stage, plus
  `STATUS.md`. Any agent can pick up where another stopped.
- **The evolution loop:**
  1. You say `/feedback the hooks are too salesy, open with the problem`, or the
     analyst finds that problem-first hooks had 2× CTR.
  2. It lands in `memory/feedback-inbox.md`.
  3. The `evolver` decides the scope:
     - **global**: a rule in `evolution/LEARNINGS.md` that every agent follows
     - **agent-specific**: a bullet in that agent's `## Learned rules`
     - **structural**: it rewrites the agent's or skill's instructions
  4. It checks the change against existing rules and sets a confidence level. Your
     feedback counts as high; one product's data counts as low, rising as the pattern
     repeats on more products.
  5. It logs the change in `evolution/CHANGELOG.md` with a way to revert it, so
     you can see exactly how the system changed and why.

  Your refinement from this session is already in as **FB-001 → CL-001** (rules L-004, L-005).

### Human gates

The agents never spend money, publish, or create accounts. You approve at:
- **Gate A**: which product × segment to pursue
- **Gate B**: the brand
- **Gate C**: budget and go-live

## Using it

```
/pipeline new pet products for the UK     # start; the orchestrator asks for your profile first
/pipeline status                          # where everything is
/pipeline resume <slug>                   # continue
/review <slug>  + paste numbers           # after posting or running ads
/feedback <anything you want changed>     # evolve the system
/evolve                                   # process queued learnings
```

## What's realistic, and where this can go

**Automated today:** research, validation math, branding, the full marketing plan,
all copy, video scripts and AI prompts, Shopify import files or a coded landing
page, ad structures, analysis of the numbers you give it, and self-improvement.

**Still done by you:** creating accounts, paying, filming or hiring UGC creators,
uploading ads, publishing. This is deliberate. It keeps your money and your
identity under your control.

**The most effective way to run it:**
1. **Organic first.** Test 3 angles × 3 hooks on TikTok/Reels for 1–2 weeks before
   spending on ads. Pay only to scale what already worked.
2. **Volume of creatives beats perfect creatives.** Aim for 10–20 new creatives a week.
   The agents write them; you or cheap UGC creators film them.
3. **Creators as the distribution channel.** TikTok Shop affiliates and gifted creators
   in the segment give you reach plus content you can reuse in ads (Spark Ads).
4. **Bundle for the segment.** It raises AOV, makes the offer harder to price-compare,
   and makes it feel like your own brand.
5. **Next automation steps:** connect MCP servers for Shopify (create products
   directly), Meta/TikTok ads (read metrics into `/review` automatically), and an
   image/video generation API. Then a scheduled weekly `/review` closes the loop
   without you pasting numbers.
