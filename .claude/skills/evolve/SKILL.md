---
name: evolve
description: Run the evolver to process every pending entry in the feedback inbox (owner refinements and performance learnings), update global learnings and agent instructions, and compact memory. Use for "/evolve", after performance reviews, or when the owner asks the system to improve itself.
---

# Evolve

1. Read `memory/feedback-inbox.md`. If there are no `pending` entries, run the
   `evolver` anyway for housekeeping only (compacting memory, promoting repeated insights),
   and tell the owner there was no new feedback.
2. Otherwise run the `evolver` subagent with: "Process all pending entries in
   memory/feedback-inbox.md and do housekeeping. $ARGUMENTS"
3. Report back: feedback processed (applied/rejected with reasons), files changed,
   new or changed rules in one line each, CL numbers.
