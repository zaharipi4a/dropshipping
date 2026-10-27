# Dropshipping Agent Studio

A team of 14 Claude Code agents. They find products that are already proven to
sell, position each one for a segment nobody owns yet, brand it, build the store,
and run the marketing. The system improves itself every time you give feedback
or real numbers come in.

## The strategy

1. **Don't guess. Copy what's proven.** We only shortlist products with 3+
   independent proof-of-sales signals: long-running ads, several stores selling it,
   marketplace sales velocity, TikTok Shop sold counts, steady search demand.
2. **Win on positioning, not product.** Take the proven product and own a segment
   the current sellers ignore: "heatless curlers" → "heatless curl kit for competitive
   dancers and cheerleaders". Same supplier, different market, your own brand.
3. **Marketing is the work.** The store is a one-time build. The ongoing work is a
   weekly loop of angles → creatives → organic test → paid scale → analysis.
4. **The system learns.** Feedback and results become rules that change every agent.

## Architecture

```
                         you
                          │  /pipeline  /feedback  /review  /evolve
                          ▼
              ┌──────────────────────────┐      reads workflow/pipeline.yaml
              │  ORCHESTRATOR (main      │──▶   (stages, parallelism, models, gates)
              │  session, /pipeline)     │
              └────────────┬─────────────┘
   ┌──────────────┬────────┴───────┬──────────────────┬───────────────────┐
   ▼              ▼                ▼                  ▼                   ▼
 SCOUT ×3     VALIDATE        BRAND ∥ GROWTH     COPY ∥ CREATIVES ×N   STORE ∥ SOCIAL ∥ COMPLIANCE
 lanes in     (opus)          (sonnet) (opus)    (sonnet)              (sonnet)
 parallel        │                 │                                       │
 (sonnet)     GATE A            GATE B                          organic test ($0, you post)
                                                                           │
                                                          ADS → COMPLIANCE ─▶ GATE C ─▶ LAUNCH
                                                                           │
                              ┌──────────── weekly loop ◀──────────────────┘
                              ▼
                   ANALYST (opus) ─▶ CREATIVES ×N ∥ ADS ∥ EVOLVER

 After every stage:  stage-qa (haiku, blocks bad output) · librarian (haiku, files knowledge in background)
 Escalation:         an agent that fails QA twice is rerun on opus
```

### Five layers

| Layer | Where | What it is |
|---|---|---|
| **Workflow** | `workflow/pipeline.yaml` | The pipeline as data: stage order, which agents run in parallel or fan out, models, inputs/outputs, gates. The orchestrator executes it and the evolver can edit it. |
| **Orchestrator** | `.claude/skills/pipeline/` | Runs in your main session, because subagents can't start other subagents. It launches agents in parallel, runs QA, logs, and talks to you at gates. |
| **Agents** | `.claude/agents/*.md` | 14 specialists, each with a role, inputs, process, output file, quality bar, model tier and an evolving `## Learned rules` section. Each gets a fresh context window. |
| **Memory** | `memory/`, `products/` | Decisions and state: owner profile, portfolio, decision log, rejected ideas, run log, and one folder per product with one file per stage. |
| **Knowledge** | `knowledge/` | Facts reusable across products: suppliers, competitors, communities, creators, hooks/angles (with measured performance), data sources. The librarian files these after every stage. |

### Agents and model routing

| Agent | Model | Why that tier | Output |
|---|---|---|---|
| product-scout (×3 lanes) | sonnet | lots of web research; volume matters | `01-scouting-<lane>.md` |
| product-validator | **opus** | money math and skepticism | `02-validation.md` |
| brand-strategist | sonnet | creative production | `03-brand.md` |
| growth-strategist | **opus** | the hardest problem: marketing strategy | `04-growth-plan.md` |
| copywriter | sonnet | production writing | `05-copy.md` |
| creative-producer (×N angle groups) | sonnet | production at volume | `06-creatives-<group>.md` |
| store-builder | sonnet | coding and setup | `07-store.md`, `store/` |
| social-manager | sonnet | production | `08-social.md` |
| ads-manager | sonnet | structured planning | `09-ads.md` |
| compliance-officer | sonnet | policy review | `compliance.md` |
| performance-analyst | **opus** | kill/scale decisions with real money | `11-performance.md` |
| evolver | **opus** | rewrites the system itself, so it must be careful | `evolution/*` |
| stage-qa | haiku | checklist checking, fast and cheap | verdict only |
| librarian | haiku | extract, dedupe, file | `knowledge/*` |

### Where information goes

| Information | Saved in | Written by |
|---|---|---|
| Stage outputs (each starts with a `## Handoff` summary) | `products/<slug>/NN-*.md` | each agent |
| Product state, checklist | `products/<slug>/STATUS.md` | orchestrator |
| Owner profile, portfolio, decisions, insights, rejected ideas | `memory/MEMORY.md` | all agents (append-only) |
| Which agent ran, model, QA result | `memory/runs.md` | orchestrator |
| Suppliers, competitors, communities, creators, hooks, sources | `knowledge/*.md` | librarian |
| Raw feedback and learnings | `memory/feedback-inbox.md` | you (`/feedback`), analyst |
| Global rules | `evolution/LEARNINGS.md` | evolver |
| Every system change and how to revert it | `evolution/CHANGELOG.md` | evolver |

### How the system evolves

1. Something gets queued in `memory/feedback-inbox.md`: you type `/feedback …`, the
   analyst finds a pattern, or you say "always/never…" at a gate.
2. The `evolver` (opus) classifies it:
   - **global**: a rule in `LEARNINGS.md`
   - **agent-specific**: a bullet in that agent's `## Learned rules`
   - **structural**: it rewrites agent or skill instructions, or edits `pipeline.yaml`
     (new stage, more parallelism, a different model tier)
3. It checks for conflicts and sets confidence. Your feedback counts as high; one product's
   data counts as low, rising as the pattern repeats.
4. It reads `memory/runs.md`. An agent that keeps failing QA gets a fixed prompt or a model upgrade.
5. Everything is logged in `CHANGELOG.md` with a revert path.

## Using it

```
/pipeline new                  # full run, scouting 3 lanes in parallel
/pipeline new pet products     # seeded run, single scout
/pipeline status
/pipeline resume <slug>
/review <slug>  + numbers      # after posting or running ads
/feedback <what to change>
/evolve
```

## Making it even more innovative (roadmap)

What's realistic now, in order of impact:

1. **Close the loop with real data (biggest win).** Meta has an official Ads MCP server
   ([docs](https://developers.facebook.com/documentation/ads-commerce/ads-ai-connectors/ads-mcp-server/ads-mcp-server-overview),
   [announcement](https://developers.facebook.com/blog/post/2026/07/16/meta-ads-mcp-server/)) for insights,
   creating ads (paused) and A/B tests. Connected, `/review` pulls numbers itself, and ads-manager can draft
   campaigns as **paused** for you to approve. The store is a custom-coded, supplier-agnostic site with Stripe payments and
   supplier API fulfillment (CJdropshipping, EU-stock suppliers, print-on-demand), so `/review` can also read revenue
   from Stripe and fulfillment/tracking status from the suppliers (or the store's admin view) with read-only keys.
2. **AI-generated UGC at volume.** Filmed creator UGC runs ~$150–300 per video, while AI variants cost about $1
   ([DropCommerce](https://blog.dropcommerce.com/posts/best-ai-video-tools-for-dropshipping)). Video models like
   Veo, Kling and Seedance can turn creative-producer's scripts into test videos
   ([workflow example](https://nikhil.pro/ai-ugc-ads-seedance-veo-chatgpt/)). This fits a <$500 budget. Rule:
   AI actors are never presented as real customers (the compliance-officer checks this).
3. **Scheduled autonomy.** A weekly scheduled task runs `/review` and the optimize loop, and only pings you at gates.
4. **Creative genome.** `knowledge/hooks-angles.md` accumulates measured hold rate, CTR and CVR per hook and angle
   type. After a few products, the evolver can say *which hook structures work for which segment*. That knowledge
   compounds across products, and competitors can't copy it.
5. **Portfolio mode.** Run 2–3 products through the pipeline in parallel (each in its own folder). Kill fast and
   scale the winner. The orchestrator already supports multiple active products.
6. **Competitor watch.** A scheduled scout re-checks `knowledge/competitors.md` weekly for new angles and new
   entrants in our segments.

**Still deliberately human:** creating accounts, payments, spending, publishing. Agents prepare everything ready to
click; you approve at gates A/B/C.
