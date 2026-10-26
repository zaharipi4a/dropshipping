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

```
 0 INTAKE      orchestrator             → products/<slug>/STATUS.md
 1 SCOUT       product-scout            → 01-scouting.md     proven sellers + segment gap
 2 VALIDATE    product-validator        → 02-validation.md   economics, risk, go/no-go
   ── GATE A: human picks product × segment ──
 3 BRAND       brand-strategist         → 03-brand.md
   ── GATE B: human approves the brand ──
 4 GROWTH      growth-strategist        → 04-growth-plan.md  angles, channels, organic test
 5 CONTENT     copywriter        ┐ parallel → 05-copy.md
               creative-producer ┘          → 06-creatives.md (+ creatives/)
 6 BUILD       store-builder     ┐ parallel → 07-store.md (+ store/)
               social-manager    ┘          → 08-social.md
   ── organic test runs here (no ad spend) ──
 7 ADS         ads-manager              → 09-ads.md          scale organic winners
   ── GATE C: human approves budget + go-live ──
 8 LAUNCH      orchestrator checklist   → 10-launch.md
 9 OPTIMIZE    performance-analyst      → 11-performance.md  weekly loop:
               → creative-producer refreshes creatives → ads-manager → analyst …
 ∞ EVOLVE      evolver                  → evolution/*, agent "Learned rules"
```

## Ground rules for every agent

1. **Read before you work:** `memory/MEMORY.md`, `evolution/LEARNINGS.md`, and the
   product's existing stage files. Never contradict an approved earlier stage
   (e.g. don't rename the brand in the copy stage).
2. **Write to files, not to chat.** Every stage produces its markdown file in
   `products/<slug>/`. Return only a short summary to the orchestrator.
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
- `memory/MEMORY.md` — the shared long-term memory: portfolio, decisions, insights
- `memory/feedback-inbox.md` — raw refinements waiting for the evolver
- `evolution/LEARNINGS.md` — global rules every agent must follow
- `evolution/CHANGELOG.md` — every change the evolver made, and why
- `products/` — one folder per product, one file per stage
