# Feedback Inbox

Raw refinements from the owner and from performance reviews, waiting for the
evolver. `/feedback` appends here; `/evolve` processes entries and marks them done.

Format:

```
## FB-<number> — YYYY-MM-DD — pending
Source: owner | performance-analyst | <agent>
Scope: global | <agent-name> | <product-slug>
Feedback: <what to change, in the owner's words>
Context: <what triggered it, file/stage it relates to>
```

When processed, the evolver changes `pending` to `applied → CL-<number>` or
`rejected — <reason>`.

---

## FB-001 — 2026-10-26 — applied → CL-001
Source: owner
Scope: global
Feedback: Sell products that are proven to sell, then position ourselves in a specific market and dropship it. Building the website is the easy part; marketing is the hardest and needs the most attention.
Context: Initial design of the pipeline.

## FB-002 — 2026-10-26 — applied → CL-002
Source: owner
Scope: global
Feedback: Run things in parallel wherever possible; use different models (Haiku/Sonnet/Opus) by difficulty; make the whole thing a workflow where everything any agent finds is saved somewhere; make the architecture the best it can be.
Context: After the first scout run.
