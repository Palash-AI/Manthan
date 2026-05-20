---
description: "Run only selected Manthan modules. Validates dependencies; fills gaps before running."
---

**START IMMEDIATELY. Do NOT narrate.**

Show this to the user:

"Which Manthan modules do you want to run?

| # | Module | Needs (from `outputs/`) |
|---|---|---|
| 1 | Idea + Scope Skeleton | — |
| 2 | Research Blitz | `m1.1-scope-skeleton.md` |
| 3 | JTBD + Archetypes | `m1.2-research-synthesis.md` |
| 3.5 | User Need Map | `m1.3-jtbd-archetypes.md` |
| 4 | Pareto v1 Lock | `m1.3.5-user-need-map.md` (+ `m1.3-jtbd-archetypes.md`) |
| 5 | Direction Brief | `m1.4-pareto-v1-lock.md` |
| 6 | Build Prototype | `m1.1` through `m1.5` |

Type comma-separated numbers — e.g., `3,4,5,6`. Or `all` for the full sequence."

**STOP** for the pick.

Then:

1. **Dependency check.** For the lowest-numbered module picked, verify its `outputs/` inputs exist on disk.
2. **If present:** confirm in one line — *"Running [list] in order. Proceed?"* — and on yes, start.
3. **If missing:** list the missing files. Ask the user to paste each one's content (or describe their version in plain language). Write each as the expected filename in `outputs/`. Then start.

For each picked module, in order, do exactly what `/manthan-N` would do — load `@lesson-modules/m1-idea-to-prototype/m1.X-…/CLAUDE.md` silently and begin with the first **SAY:** block under `## Teaching Flow`. No meta-narration between modules. Apply `principle-auditor` per the existing scripts.

If a module's closing SAY says "Ready for /manthan-N+1?" but `N+1` is NOT in the picked list, replace that line with: *"Picked-mode run complete. Outputs at `outputs/`."*
