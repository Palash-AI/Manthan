# PROJECT-PRINCIPLES — Schema & Operating Contract

> **Status:** Load-bearing. This file defines how project-specific principles work.
> **Owner:** Palash Somani (pAI)
> **Skill:** Manthan

---

## What this is

`PRINCIPLES.md` at repo root is the **workshop floor** — universal, never edited by any Manthan flow.

`outputs/PROJECT-PRINCIPLES.md` is the **project layer** — rules that emerged from the *specific project* being run. Created lazily on the first approved principle. Loaded at every turn alongside `PRINCIPLES.md`. Audited by `principle-auditor` as additional Dimension A rows.

Two layers. Global is sacred. Project is mutable, by user approval only.

---

## When a candidate principle exists

At the end of every module, Claude silently scans the turn-by-turn history of just that module against three heuristics:

| Heuristic | Test |
|---|---|
| **Repetition** | The same decision pattern showed up 2+ times in the module (e.g., user rejected 2+ drafts for the same reason). |
| **Transferability** | The rule would change behaviour in a *future* module of this same project — not just the current artifact. |
| **Stated by user, not inferred** | The user said something like "I never want X" or "always do Y" or rejected something with a generalisable reason. Pure Claude-inferences get downgraded. |

**Gate:**
- 0 / 3 hits → drop silently. Module ends. **No "I scanned and found nothing" announcement.**
- 1 / 3 hits → scratch internally; do not surface.
- 2 or 3 / 3 hits → surface ONE at a time to the user (max 2 per module). Use the prompt in §5.

This guardrail exists for a reason. **Reflection is a sharpening moment, not a quiz.** Most modules will produce zero candidates. That is correct behaviour.

---

## Schema — one entry

Every entry in `outputs/PROJECT-PRINCIPLES.md` follows this exact structure:

```markdown
### P-NNN — <Rule in one imperative sentence>
- **Added:** YYYY-MM-DD (Module m1.X)
- **Rule:** <The rule itself. One sentence. Active voice. Imperative.>
- **Why it emerged:** <2-3 lines of evidence from the module that triggered this.>
- **Evidence:** <File path + section reference where the pattern shows.>
- **When to apply:** <Named future surfaces. "Every Pareto cut", "Every screen copy decision", etc.>
- **Conflicts with global?:** <No / Yes — quoted PRINCIPLES.md section>
- **Status:** active
```

ID format: `P-001`, `P-002`, ... — sequential, project-scoped.

Fields are fixed-order. No extra fields. No commentary outside the schema.

---

## Reflection prompt template

When a candidate clears the 2-of-3 gate, Claude surfaces it to the user using this exact template:

```
Before we move to the next module, I noticed something worth pinning as a
project principle.

CANDIDATE P-NNN
Rule: <one sentence>
What I observed: <2-3 lines of evidence from this module>
Where it would apply later: <named future surfaces>
Confidence: <high / medium — based on heuristics hit>

Approve, reject, or edit? (a / r / edit:<your wording>)
```

One candidate per prompt. Cap: 2 per module.

If reflection finds zero candidates, the module ends silently — straight to "Ready for /manthan-N+1?". **No announcement, no apology, no filler.**

---

## User-invoked add

Trigger phrases (case-insensitive): `"save that as a principle"`, `"add to my project principles"`, `"pin this"`, `"whenever I do X, always Y — save"`.

Protocol:

1. Claude restates the rule in the schema's one-sentence imperative form.
2. Claude fills in the surrounding fields itself (Why, Evidence pointing to the current turn, When-to-apply inferred from context).
3. Run the conflict check (§6) *before* showing the entry.
4. Show the full entry to the user with: *"Save as P-NNN? (y / edit / no)"*
5. On `y`, append to `outputs/PROJECT-PRINCIPLES.md` (create if missing).

**No silent saves.** Every write is shown first.

---

## Conflict with global `PRINCIPLES.md`

A candidate that conflicts with `PRINCIPLES.md` is **blocked, not silently shadowed.**

When Claude detects a conflict during reflection or a user-invoked add:

```
CONFLICT DETECTED

Candidate: <new rule>
Conflicts with PRINCIPLES.md: <quoted section>

Resolution options:
  1. Drop the candidate (global wins — default)
  2. Narrow the candidate so it doesn't conflict (Claude proposes wording)
  3. Escalate: this is a global PRINCIPLES.md change request, not a project rule
     → Claude does NOT modify PRINCIPLES.md. It writes the request to
       outputs/PRINCIPLES-CHANGE-REQUESTS.md and tells the user to review
       outside the flow.

Choose 1 / 2 / 3.
```

**Global PRINCIPLES.md is never edited by any Manthan flow. Only by the user manually, outside any active run.**

---

## File structure

```
new-manthan/
├── PRINCIPLES.md                            ← global, sacred
├── PROJECT-PRINCIPLES-SCHEMA.md             ← this file (the contract)
└── outputs/
    ├── PROJECT-PRINCIPLES.md                ← created lazily on first approval
    └── PRINCIPLES-CHANGE-REQUESTS.md        ← created if user picks resolution 3
```

`outputs/PROJECT-PRINCIPLES.md` does not exist until the user approves a first principle. The hook handles the missing-file case gracefully (silent skip).

---

## Loading at every turn

`outputs/PROJECT-PRINCIPLES.md` is loaded via the existing `UserPromptSubmit` hook in `.claude/settings.json`. If the file exists, its contents are injected into the turn alongside the global `PRINCIPLES.md` reminder. If it doesn't, the hook is silent.

`principle-auditor` reads both files before every audit and treats each project rule as an additional Dimension A check.

---

## What this file is NOT

- Not a list of principles. (Those live in `outputs/PROJECT-PRINCIPLES.md`.)
- Not aspirational. (Every rule here is enforced.)
- Not editable by Manthan flows. (Only the user edits this contract.)

---

*Built with Manthan by Palash Somani (pAI)*
