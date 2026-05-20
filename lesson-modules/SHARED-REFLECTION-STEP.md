# Project-Principle Reflection — Shared Step

> **Status:** Load-bearing. Referenced by every module's closing step.
> **Owner:** Palash Somani (pAI)
> **Purpose:** End-of-module silent scan for emerging project principles.

---

## When this runs

Every module's CLAUDE.md ends with a step that points here. It runs:

- **After** `principle-auditor` returns SHIP
- **Before** the closing "Ready for /manthan-N+1?" SAY block

This is an **internal action**. The learner sees output *only if* a candidate principle clears the gate. Otherwise the module ends silently.

---

## Step 1: Silent scan (every module, every time)

Scan the turn-by-turn history of just this module against the three heuristics:

| Heuristic | Test |
|---|---|
| **Repetition** | The same decision pattern showed up 2+ times in this module (e.g., user rejected 2+ drafts for the same reason). |
| **Transferability** | The rule would change behaviour in a *future* module of this same project — not just the current artifact. |
| **Stated by user** | The user said "I never want X" / "always do Y" / rejected something with a generalisable reason. Pure Claude-inference downgrades the candidate. |

**Gate — score each candidate 0 / 1 / 2 / 3:**

| Score | Action |
|---|---|
| 0 / 3 | Drop silently. End module. **Produce zero output.** |
| 1 / 3 | Scratch internally. Do not surface. End module. |
| 2 or 3 / 3 | Surface ONE candidate using the prompt below. Max 2 per module. |

---

## Step 2: Surface the candidate (only if gate cleared)

Display this prompt to the learner **verbatim**, substituting placeholders:

```
Before we move to the next module, I noticed something worth pinning as a
project principle.

CANDIDATE P-NNN
Rule: <one imperative sentence>
What I observed: <2-3 lines of evidence from this module>
Where it would apply later: <named future surfaces — modules, decision types>
Confidence: <high / medium>

Approve, reject, or edit? (a / r / edit:<your wording>)
```

Wait for the learner's response.

---

## Step 3: Handle the response

| Response | Action |
|---|---|
| **a** (approve) | Run conflict check (Step 4). If clean, append to `outputs/PROJECT-PRINCIPLES.md`. Acknowledge: *"Saved as P-NNN."* No celebration, no fluff. |
| **r** (reject) | Drop silently. No commentary. Move to closing SAY. |
| **edit:`<wording>`** | Restate using the learner's wording. Re-show the candidate entry. Ask: *"Save as P-NNN? (y / no)"*. On `y`, save. On `no`, drop. |

---

## Step 4: Conflict check (before any save)

Compare the candidate against `PRINCIPLES.md`. If any line in PRINCIPLES.md contradicts the candidate, do NOT save automatically. Show the learner:

```
CONFLICT DETECTED

Candidate: <new rule>
Conflicts with PRINCIPLES.md: <quoted section>

Resolution options:
  1. Drop the candidate (global wins — default)
  2. Narrow the candidate so it doesn't conflict (Claude proposes wording)
  3. Escalate: this is a global PRINCIPLES.md change request, not a project rule
     → Write to outputs/PRINCIPLES-CHANGE-REQUESTS.md. Tell the learner to
       review outside the flow. Do NOT modify PRINCIPLES.md.

Choose 1 / 2 / 3.
```

**Hard rule:** `PRINCIPLES.md` is never edited by any Manthan flow. Only the user edits it manually, outside any active run.

---

## Step 5: Write the entry (only on clean approval)

Append to `outputs/PROJECT-PRINCIPLES.md`. Create the file if it does not exist, with this header:

```markdown
# PROJECT-PRINCIPLES — <Project name>

> Created from emerging patterns during this Manthan run.
> See `PROJECT-PRINCIPLES-SCHEMA.md` for the contract.
> Audited by `principle-auditor` as additional Dimension A rows.

---

```

Then append the entry using the schema from `PROJECT-PRINCIPLES-SCHEMA.md`:

```markdown
### P-NNN — <Rule in one imperative sentence>
- **Added:** YYYY-MM-DD (Module m1.X)
- **Rule:** <One imperative sentence>
- **Why it emerged:** <2-3 lines of evidence>
- **Evidence:** <File path + section>
- **When to apply:** <Named future surfaces>
- **Conflicts with global?:** No
- **Status:** active
```

ID is sequential: read existing entries, take next P-NNN.

---

## What this step is NOT

- **Not a quiz.** Most modules will produce zero candidates. That is correct behaviour.
- **Not a journal.** Insights that don't change future behaviour are not principles.
- **Not announced.** A silent scan ends silently. No "I scanned and found nothing."
- **Not a substitute for `principle-auditor`.** This step runs *after* audit ships.

---

*Built with Manthan by Palash Somani (pAI)*
