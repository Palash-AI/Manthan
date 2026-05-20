# Iteration Protocol — Manthan post-launch re-runs

> Maps post-launch signals to the modules that need re-running.
> Read by the `iteration-auditor` agent. Update when new failure patterns emerge.

---

## The signal → modules taxonomy

| Signal (in post-launch data) | What's contradicted | Modules to re-run |
|---|---|---|
| Low retention (D2 / D7 / D30 below target) | Pareto missed a retention lever; or User Need Map missed a need | `m1.3.5` → `m1.4` → `m1.6` |
| Wrong demographic actually signing up | Archetype hypothesis wrong | `m1.3` → `m1.3.5` → `m1.4` → `m1.5` → `m1.6` |
| Right users, wrong job being hired | JTBD framing wrong | `m1.2` (light re-scan) → `m1.3` → downstream |
| Feature usage skewed (one dominant, others dead) | Pareto over-included | `m1.4` → `m1.6` |
| Loop works but UX friction high | Direction brief or build quality | `m1.5` → `m1.6` |
| Visual feels off | Aesthetic tone wrong | `m1.5` → `m1.6` |
| AI surface broken ("feels arbitrary", "responses random", "doesn't match my context") | AI architecture wrong | `m1.5` (AI surface map) → `m1.6` |
| New competitor or market shift | Reference brief stale | `m1.2` (competitive re-scan) → `m1.5` → `m1.6` |
| Solving the wrong problem entirely | Scope / foundation wrong | `m1.1` onwards (fresh run) |

---

## How to read the signal

1. The signal must be **specific** — backed by a number or a quote, not a vibe.
2. If a signal touches multiple rows, list ALL affected modules; take the union of re-run paths.
3. If a signal doesn't match any row cleanly, the auditor returns `confidence: low` with follow-up questions for the orchestrator to put to the user before mapping.
4. The taxonomy is **opinionated, not exhaustive.** When you encounter a new failure pattern, log it here so future iterations get sharper.

---

## What the re-run looks like

After the audit, the orchestrator (`/manthan-iterate`) runs the affected modules in dependency order — same execution path as `/manthan-pick`. Each module's `principle-auditor` gate gets an augmented prompt: *"ALSO verify the new artifact addresses the contradictions in `outputs/POST-LAUNCH-OBSERVATIONS.md`. SHIP only if the relevant contradiction is resolved by this artifact."*

This is what keeps the iteration loop closed: nothing ships until the contradiction it was triggered by is actually addressed.

---

*Built with Manthan by Palash Somani (pAI)*
