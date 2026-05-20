# Manthan — Project Memory

> **Skill:** Manthan by Palash Somani (pAI)
> **Purpose:** A playbook for putting structured thinking back into AI-assisted product building.
> **For:** Product managers and builders going from a fuzzy idea to a high-confidence working prototype.

---

## Operating Rules — read every turn

Before producing ANY substantive output in this project, you must:

1. **Read `@PRINCIPLES.md`** — the two checks (user-first, why-here-why-now) and the feedback protocol. The global floor.
2. **Read `@DOCUMENT-STANDARDS.md`** — the consulting-grade rules for every artifact.
3. **Read `@.claude/SCRIPT_INSTRUCTIONS.md`** — the no-fourth-wall rules for `/manthan-N` modules.
4. **Read `@PROJECT-PRINCIPLES-SCHEMA.md`** — the contract for project-specific principles (loaded automatically when present at `outputs/PROJECT-PRINCIPLES.md`).
5. **Run the checks silently.** State the answers in your reasoning before producing the artifact.
6. **For high-stakes outputs in direct conversation with Palash** (drafts, plans, critiques), lead with: "Applied principles: [user-first answer] / [why-now answer] / [feedback re-questioned: yes/no]."

**Two principle layers — both are gates:**

| Layer | File | Edited by |
|---|---|---|
| Global | `PRINCIPLES.md` | User only, manually, outside any flow. **Never edited by Manthan.** |
| Project | `outputs/PROJECT-PRINCIPLES.md` | Reflection step at end of the workshop (after m1.6), only on user approval. |

If `outputs/PROJECT-PRINCIPLES.md` exists, its contents auto-load via the UserPromptSubmit hook and apply alongside global principles. `principle-auditor` audits against both.

**Inside `/manthan-N` flows: principles run silently.** No "Applied principles" declaration. No file-load narration. The learner sees the lesson, not the backend.

These are gates, not aspirations. Artifacts that fail them are revised before delivery.

---

## What Manthan is

The Samudra Manthan myth: gods and demons churned the cosmic ocean using Mount Mandara as the rod and Vasuki the serpent as the rope. Out came poison (discarded), fourteen ratnas (treasures), and finally Amrit (the nectar of immortality).

Manthan-the-skill maps that arc onto product building:

| Myth | Skill |
|---|---|
| Cosmic ocean | The fuzzy idea space |
| Mount Mandara (the rod) | The structured method |
| Vasuki (the rope) | The discipline of pulling against your own assumptions |
| Halahal (the poison) | The bad ideas you must discard |
| 14 Ratnas | The artifacts produced (scope, JTBD grid, archetypes, Pareto cut, direction brief) |
| Amrit | The high-confidence working prototype |

---

## The seven-step sequence

> **The spine question** (asked across the chain with discipline): *what does this user need to succeed at this job?*

| # | Step | Skill it teaches | Claude Code capability it showcases |
|---|---|---|---|
| 1 | Idea + scope skeleton | Frame the problem before solving | Sequential write |
| 2 | Research blitz | Get evidence before locking | **Parallel sub-agents** |
| 3 | JTBD + 4 archetypes | Translate research into user models | Sequential synthesis |
| **3.5** | **User Need Map (8 dimensions)** | **Derive user needs from first principles BEFORE features. The structural reframe that makes Manthan beat one-shot prompting.** | **First-principles synthesis** |
| 4 | Pareto v1 lock | Cut ruthlessly, traceable to user needs | Sequential decision |
| 5 | Direction brief | Pin the feel + AI architecture with rubric depth | Sequential, AskUserQuestion |
| 6 | Build prototype (polished, with iteration pass) | Compounding constraints → home.html-quality output | Sequential build, parallel for screens |

---

## Sub-agents

| Agent | When to call |
|---|---|
| `manthan-researcher` | Step 2 — parallel research (user voice + competitive scan + market context) |
| `jtbd-synthesizer` | Step 3 — convert research into JTBD grid + archetypes |
| `scope-editor` | Step 4 — apply 5-criteria Pareto |
| `principle-auditor` | After every artifact — gate against `PRINCIPLES.md` |

---

## Folder structure

```
manthan/
├── README.md                          ← public-facing intro
├── CLAUDE.md                          ← this file
├── PRINCIPLES.md                      ← the two checks + feedback protocol (global, sacred)
├── DOCUMENT-STANDARDS.md              ← consulting-grade rules
├── PROJECT-PRINCIPLES-SCHEMA.md       ← contract for project-specific principles
├── GLOSSARY.md                        ← 15 product-lens terms (Swiggy examples)
├── course-structure.json              ← module manifest
├── .claude/
│   ├── commands/                      ← /manthan-1 ... /manthan-6, /manthan-pick (selective run)
│   ├── agents/                        ← researcher, jtbd-synthesizer, scope-editor, principle-auditor, handoff-syncer
│   └── settings.json                  ← UserPromptSubmit hook (loads global + project principles)
├── lesson-modules/
│   ├── SHARED-REFLECTION-STEP.md      ← end-of-workshop project-principle reflection protocol (runs once after m1.6)
│   └── m1-idea-to-prototype/
│       ├── m1.1-idea-and-scope/CLAUDE.md
│       ├── m1.2-research/CLAUDE.md
│       ├── m1.3-jtbd-archetypes/CLAUDE.md
│       ├── m1.3.5-user-need-map/CLAUDE.md      ← spine reframe
│       ├── m1.4-pareto/CLAUDE.md
│       ├── m1.5-direction-brief/CLAUDE.md
│       └── m1.6-build-prototype/CLAUDE.md
├── reference/                         ← pre-baked fallback files (safety nets)
├── outputs/                           ← learner artifacts (gitignored)
│   └── PROJECT-PRINCIPLES.md          ← created lazily on first approval (project-specific rules)
└── take-home/                         ← post-workshop skill for self-service use
```

---

## Brand line

Every output produced via Manthan ends with:

```
Built with Manthan by Palash Somani (pAI)
```

---

*Read `PRINCIPLES.md` and `DOCUMENT-STANDARDS.md` now if you have not already. They are the floor.*
