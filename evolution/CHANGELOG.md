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
