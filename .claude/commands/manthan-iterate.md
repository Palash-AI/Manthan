---
description: "Iterate Manthan on a launched project. Audits original artifacts against post-launch data, recommends a minimal re-run path, then executes."
---

**START IMMEDIATELY. Do NOT narrate.**

Show this:

"Welcome back to Manthan — iteration mode.

I'll audit your original artifacts against your post-launch observations, then recommend the minimum re-run path.

Do you have `outputs/POST-LAUNCH-OBSERVATIONS.md`? (y / n)"

**STOP** for response.

---

**If `n`:**

Say: *"Let's create it. Paste or describe your observations — cover metrics (D2/D7/D30 retention, feature usage), user feedback (verbatim quotes from support, reviews, calls), and what surprised you vs your original hypotheses. Don't worry about structure; I'll organise it."*

**STOP** for content.

Write `outputs/POST-LAUNCH-OBSERVATIONS.md` with the user's input, organised into sections: *Metrics / Verbatim user signals / Feature usage / Surprises*.

**If `y`:** confirm the file is populated. If sparse, ask for more before proceeding.

---

**Then — run the audit:**

```
Use the Task tool to invoke iteration-auditor with prompt:
"Audit the Manthan project against post-launch observations.
Read all outputs/m1.*.md (original artifacts), outputs/POST-LAUNCH-OBSERVATIONS.md
(new data), and ITERATION-PROTOCOL.md (taxonomy). Return contradictions found,
recommended re-run path, modules to skip, and confidence — in the exact output
format specified in your system prompt."
```

Display the audit report verbatim.

If the report's `confidence` is `low` and includes Follow-up questions, put those questions to the user, then update `POST-LAUNCH-OBSERVATIONS.md` with their answers and re-invoke the auditor before proceeding.

---

**Then — confirm before re-running:**

Say:

*"Two things before we proceed:*

*1. **Back up your current `outputs/` folder** — rename to `outputs-v1/` (or your convention). The re-runs will overwrite refreshed artifacts.*

*2. **Confirm the re-run path.** The audit recommends `[path]`. You can: accept, modify (e.g., 'add m1.2 also'), or cancel.*

*Type:*
*- `backed up, proceed` to start the re-run*
*- `modify [your path]` to change the path*
*- `cancel` to stop"*

**STOP** for response.

**Refuse to proceed unless the user explicitly says they've backed up.** No exceptions.

---

**On `backed up, proceed`:**

For each module in the re-run path, in order, do exactly what `/manthan-N` would do — load `@lesson-modules/m1-idea-to-prototype/m1.X-…/CLAUDE.md` silently and run from the first **SAY:** block.

**Critical augmentation at each principle-auditor call:** add to the auditor's prompt: *"ALSO verify the new artifact addresses the contradictions logged in `outputs/POST-LAUNCH-OBSERVATIONS.md`. SHIP only if the relevant contradiction is resolved by this artifact."*

No meta-narration between modules. If the path ends mid-chain, replace the last module's "Ready for /manthan-N+1?" closing with: *"Iteration re-run complete. Compare new outputs against your backup to see what changed."*
