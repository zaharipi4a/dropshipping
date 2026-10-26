---
name: review
description: Feed real performance data (organic post stats, ad metrics, store analytics, orders, refunds) for a product into the performance analyst, get kill / iterate / scale decisions, queue learnings for the evolver, and kick off the next marketing loop. Use for "/review <slug>" or whenever the owner shares numbers or screenshots.
---

# Performance review

Arguments: `$ARGUMENTS` — `<slug>` plus optionally pasted numbers.

1. If no slug is given, list the active products from `memory/MEMORY.md` and ask which one.
2. Collect data: anything pasted in this conversation, files in `products/<slug>/data/`,
   or screenshots. Save pasted numbers to `products/<slug>/data/<today>.md` so they're kept.
   If key numbers are missing (spend, impressions, clicks, add-to-carts, purchases, revenue),
   ask for them — don't guess.
3. Run the `performance-analyst` subagent with the slug, the data file paths, and the data window.
4. Show the owner: scoreboard, product decision, top 3 actions.
5. If the analyst queued learnings in `memory/feedback-inbox.md`, run the `evolver`.
6. Next loop: if the decision is ITERATE or SCALE, offer to run `creative-producer` for fresh
   creatives on the winning angles and `ads-manager` to update the test plan (in parallel).
   If KILL, mark the product `killed` in the Portfolio and offer `/pipeline new`.
