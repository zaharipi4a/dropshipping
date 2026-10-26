# Run Log

One line per agent run, appended by the orchestrator. Use it to see what ran,
on which model, how long it took, and whether QA passed. It's also what the
evolver uses to spot agents that keep failing (candidates for a model upgrade
or prompt fix).

| Date | Slug | Stage | Agent | Model | Mode (fg/bg/parallel) | Output | QA | Notes |
|---|---|---|---|---|---|---|---|---|
| 2026-10-26 | scout-20261026 | scout | product-scout | inherit (session model) | bg | 01-scouting.md | n/a (pre-QA) | ~13 min, 94 tool calls; ran before model tiers existed |
| 2026-10-26 | scout-20261026 | validate | product-validator | opus | bg | 02-validation.md | pending | ran in parallel with the architecture upgrade |
