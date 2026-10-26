# Dropshipping Agent Pipeline

This repo is an **agentic dropshipping studio**. A main-thread orchestrator drives
specialist subagents through a pipeline: find a product → validate it → brand it →
build the store → produce creatives → set up socials → plan ads → launch → analyze
→ evolve.

## How to run it

| Command | What it does |
|---|---|
| `/pipeline new [niche or idea]` | Start a new product pipeline from scratch |
| `/pipeline resume <slug>` | Continue a product from its current stage |
| `/pipeline status` | Show all products and where they are |
| `/feedback <what to change>` | Record a refinement; the evolver applies it to every relevant agent |
| `/evolve` | Process all pending feedback and performance learnings now |
| `/review <slug>` | Feed in real sales/ad numbers; the analyst decides kill / iterate / scale |

## The pipeline

**Thesis:** sell products that are *already proven* to sell, and win by
positioning them for a specific segment the current sellers ignore. The store is
the easy part; most of the effort goes to marketing (stages 4–9).

The full workflow (stages, parallelism, models, inputs/outputs, gates) is data in
**`workflow/pipeline.yaml`**. That file is the source of truth; this is the picture:

```
 intake ─▶ SCOUT ×3 lanes (parallel, sonnet) ─▶ VALIDATE (opus) ─▶ GATE A
        ─▶ BRAND (sonnet) ∥ GROWTH PLAN (opus) ─▶ GATE B
        ─▶ COPY (sonnet) ∥ CREATIVES ×2–3 angle groups (sonnet)
        ─▶ STORE ∥ SOCIAL ∥ COMPLIANCE (sonnet) ─▶ organic test (owner, $0)
        ─▶ ADS (sonnet) → COMPLIANCE ─▶ GATE C ─▶ LAUNCH
        ─▶ weekly loop: ANALYST (opus) ─▶ CREATIVES ×N ∥ ADS ∥ EVOLVER (opus)

 after every stage:  stage-qa (haiku, blocking) · librarian (haiku, background) · log to memory/runs.md
 on feedback:        evolver (opus)
```

Model tiers: **haiku** = checking/filing, **sonnet** = research/production,
**opus** = judgment, strategy and money decisions. If an agent fails QA twice, it reruns on opus.

## Ground rules for every agent

1. **Read before you work:** `memory/MEMORY.md`, `evolution/LEARNINGS.md`, and the
   product's existing stage files. Never contradict an approved earlier stage
   (e.g. don't rename the brand in the copy stage).
2. **Write to files, not to chat.** Every stage produces its markdown file in
   `products/<slug>/`, starting with a `## Handoff` section (5–10 key facts for
   downstream agents). Return only a short summary to the orchestrator.
2b. **Knowledge first.** Before researching, check `knowledge/` (suppliers,
   competitors, communities, creators, hooks, sources). The librarian files new
   findings there after each stage. Parallel agents write to different files, and
   shared files are append-only (re-read right before editing).
3. **Log to memory.** Append decisions and notable findings to `memory/MEMORY.md`
   (decision log) using the format defined there. Append, don't rewrite history.
4. **Cite evidence.** Market claims need a source URL or a stated assumption.
   Label numbers as `measured`, `estimated`, or `assumed`.
5. **Never spend money, publish, or create accounts on your own.** Agents produce
   ready-to-execute assets and checklists. Anything that costs money, goes public,
   or uses the owner's identity needs explicit human approval at a gate.
6. **Stay compliant.** No fake reviews, no fake scarcity timers, no unverifiable
   health/medical claims, no trademarked brands or lookalike branding, honest
   shipping times. Respect ad platform policies.
7. **Product slugs** are lowercase-kebab (`posture-corrector-pro`). Each product
   lives in `products/<slug>/`. Copy the skeleton from `products/_template/`.

## Where things live

- `.claude/agents/` — the specialist subagents (each ends with a `## Learned rules` section the evolver maintains)
- `.claude/skills/` — the slash commands above
- `workflow/pipeline.yaml` — the pipeline as data (stages, parallelism, models, gates)
- `memory/MEMORY.md` — the shared long-term memory: owner profile, portfolio, decisions, insights
- `memory/runs.md` — one row per agent run (model, mode, QA verdict)
- `knowledge/` — cross-product library: products, suppliers, competitors, communities, creators, hooks, sources
- `memory/feedback-inbox.md` — raw refinements waiting for the evolver
- `evolution/LEARNINGS.md` — global rules every agent must follow
- `evolution/CHANGELOG.md` — every change the evolver made, and why
- `products/` — one folder per product, one file per stage
