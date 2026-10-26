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
