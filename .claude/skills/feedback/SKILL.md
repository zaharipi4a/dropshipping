---
name: feedback
description: Record a refinement from the owner (about any agent, stage, output, or the whole studio) and immediately evolve the system with it. Use for "/feedback <text>", or whenever the owner says something like "from now on…", "I don't like how…", "the videos should…", "always/never…".
---

# Feedback

Feedback: `$ARGUMENTS`

1. If the feedback is empty or unclear, ask one short question to clarify what should change.
2. Work out the **scope**: global, a specific agent (e.g. `creative-producer`), or one product only.
   Note the context (which product/stage/file triggered it, if any).
3. Append an entry to `memory/feedback-inbox.md`, numbered after the last entry:
   ```
   ## FB-<n> — <today> — pending
   Source: owner
   Scope: <scope>
   Feedback: <the owner's words, lightly cleaned>
   Context: <product/stage/file, if any>
   ```
4. Run the `evolver` subagent to process the inbox now.
5. Tell the owner in a few lines what changed (rules added, agents updated) and the CL number,
   so they can check `evolution/CHANGELOG.md` or ask to revert it.
