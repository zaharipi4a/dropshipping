# Run Log

One line per agent run, appended by the orchestrator. Use it to see what ran,
on which model, how long it took, and whether QA passed. It's also what the
evolver uses to spot agents that keep failing (candidates for a model upgrade
or prompt fix).

| Date | Slug | Stage | Agent | Model | Mode (fg/bg/parallel) | Output | QA | Notes |
|---|---|---|---|---|---|---|---|---|
| 2026-10-26 | scout-20261026 | scout | product-scout | inherit (session model) | bg | 01-scouting.md | n/a (pre-QA) | ~13 min, 94 tool calls; ran before model tiers existed |
| 2026-10-26 | scout-20261026 | validate | product-validator | opus | bg | 02-validation.md | FAIL → sent back | ~7 min; QA: L-004 proof signals not sales-type, L-002 violated by GO verdict, Kitsch misattribution |
| 2026-10-26 | scout-20261026 | file-knowledge | librarian (via general-purpose) | haiku | bg ∥ validator | knowledge/* (10 products, 11 suppliers, 31 competitors, 6 communities, 6 hooks, 31 sources) | n/a | ran in parallel with validation |
| 2026-10-26 | scout-20261026 | qa | stage-qa | haiku | fg | verdict | — | ~74 s; caught 3 blocking + 10 minor issues; arithmetic verified |
| 2026-10-26 | scout-20261026 | validate (fix round 1) | product-validator | opus | bg | 02-validation.md | pending | |
