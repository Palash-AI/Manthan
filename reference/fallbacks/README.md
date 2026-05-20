# Fallback Files — workshop safety nets

> **What this is:** Pre-baked sample outputs for each module's main artifact. Use ONLY if a live agent stalls during the workshop.
> **Discipline:** These exist so a 15-second technical glitch doesn't kill the demo. They are not a substitute for running the modules.

---

## When to use

| Module | Live agent | Fallback file | Use if... |
|---|---|---|---|
| Module 2 | 3 parallel `manthan-researcher` agents | `m1.2-research-synthesis-FALLBACK.md` | Any of the 3 agents fails or takes >2 min |
| Module 3 | `jtbd-synthesizer` | `m1.3-jtbd-archetypes-FALLBACK.md` | Synthesizer returns weak archetypes or fails |
| Module 4 | `scope-editor` | `m1.4-pareto-v1-lock-FALLBACK.md` | Editor gets confused by feature ambiguity or fails |
| Module 5 | Direct authoring | `m1.5-direction-brief-FALLBACK.md` | The module gets bogged down in vector choices |

---

## How to use during the workshop

1. **Detect:** Live agent has run >2 minutes without progress, or output quality is visibly weak.
2. **Recover:** "Looks like the agent's having a moment — let me show you the version we pre-ran." Switch to the fallback file.
3. **Continue:** Display the fallback as if it were the agent's output. Move to the next step. Total recovery: 15-30 seconds.

---

## Why this is in the workshop, not in the take-home

The take-home runs at the learner's pace. There's no time pressure. If an agent stalls, the learner waits or restarts. No fallback needed.

The workshop has 60 minutes and 50+ people watching. A stall is a different problem. Fallbacks solve it.

---

*Built with Manthan by Palash Somani (pAI)*
