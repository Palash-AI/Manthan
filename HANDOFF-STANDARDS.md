# HANDOFF-STANDARDS — Quality Contract for Audience-Specific Handoffs

> **Status:** Load-bearing. Every handoff file is generated against this contract.
> **Owner:** Palash Somani (pAI)
> **Skill:** Manthan

---

## What this is

By the end of a Manthan run, the learner has artifacts in `outputs/` (scope, research, JTBD, user need map, Pareto, direction brief, visual study, screen spec, prototype). Useful, but they're *Claude's working documents*. They're not ready to hand to a PM, designer, or engineer cold.

This file defines the contract for **regenerated, audience-shaped handoffs** that ARE ready.

Four handoff files (three always, one conditional):

| File | Audience | Purpose | Generated? |
|---|---|---|---|
| `outputs/handoffs/handoff-pm.md` | Product Manager | Strategy + scope spine | Always |
| `outputs/handoffs/handoff-designer.md` | Designer | Feel + screen logic + interaction | Always |
| `outputs/handoffs/handoff-tech.md` | Tech / Frontend Engineer | Build structure + data flows + constraints | Always |
| `outputs/handoffs/handoff-ai-eng.md` | AI / ML Engineer | AI surfaces, rubrics, eval anchors | **Only if** `outputs/m1.5-direction-brief.md` has a populated AI Surface Map with ≥1 surface |

The `handoff-syncer` sub-agent reads source artifacts and regenerates these files — it never edit-merges.

---

## The standard, in one line

**Consulting-grade, audience-specific, ready to share without preamble.** Every handoff passes `DOCUMENT-STANDARDS.md`'s skim test and 30-second test.

---

## Hard rules — every handoff

| Rule | Why |
|---|---|
| **Regenerated, never appended.** | Single source of truth = the artifact set. Editing handoffs creates drift; regeneration cannot drift. |
| **Audience-shaped, not artifact-dumped.** | A PM does not need the full screen spec. A designer does not need the success metric KPI in detail. Slice per audience. |
| **No fluff phrases.** Banned per `DOCUMENT-STANDARDS.md`. | Recipients should be able to skim in 60 seconds. |
| **Citations inline.** Every section ends with `*Source: outputs/m1.X-…md*`. | Recipient can dig deeper without asking. |
| **Schema-fixed per file.** No improvising section order. | Predictable structure across projects → recipient trust. |
| **End with `*Built with Manthan by Palash Somani (pAI)*`.** | Brand line. |
| **No emojis unless explicitly in the source artifact.** | Consulting-grade. |
| **Tables > paragraphs.** Same as DOCUMENT-STANDARDS. | Skimmability. |

---

## Schema — `handoff-pm.md`

Fixed section order:

```markdown
# PM Handoff — <Product Name>

*Generated: YYYY-MM-DD. Source: Manthan artifact set v<n>. Reading time: ~5 min.*

## 1. Product frame
- Product name + one-line idea
*Source: outputs/m1.1-scope-skeleton.md*

## 2. Primary archetype
- Name + behavioural definition
*Source: outputs/m1.1-scope-skeleton.md + outputs/m1.3-jtbd-archetypes.md*

## 3. Job to be done
- JTBD sentence + user-voice quote
*Source: outputs/m1.1-scope-skeleton.md*

## 4. Evidence base
- 3-stream research synthesis: top 5 cuts (user voice + competitive + market)
*Source: outputs/m1.2-research-synthesis.md*

## 5. User Need Map (summary)
- 8 dimensions, one line each
*Source: outputs/m1.3.5-user-need-map.md*

## 6. Pareto v1 — what we ARE building (5 features)
- 5 features + one-line rationale each
*Source: outputs/m1.4-pareto-v1-lock.md*

## 7. Explicitly NOT building
- List from m1.1 Field 9 + items cut at Pareto
*Source: outputs/m1.1-scope-skeleton.md + outputs/m1.4-pareto-v1-lock.md*

## 8. Success metric + top 3 risks
*Source: outputs/m1.1-scope-skeleton.md*

## 9. Positioning
- One-liner from direction brief
*Source: outputs/m1.5-direction-brief.md*

## 10. Open questions / v1.1 queue
- From 5-lens review weaknesses + priority queue triggers
*Source: outputs/m1.4-pareto-v1-lock.md + outputs/prototype/...*

---
*Built with Manthan by Palash Somani (pAI)*
```

---

## Schema — `handoff-designer.md`

```markdown
# Designer Handoff — <Product Name>

*Generated: YYYY-MM-DD. Source: Manthan artifact set v<n>. Reading time: ~6 min.*

## 1. Archetype + emotional driver
- Name + emotion you must design FOR
*Source: outputs/m1.3-jtbd-archetypes.md + outputs/m1.5-direction-brief.md*

## 2. Job + core loop
- JTBD + the loop the design must close
*Source: outputs/m1.1-scope-skeleton.md*

## 3. User Need Map (full 8 dimensions)
- Verbatim from m1.3.5
*Source: outputs/m1.3.5-user-need-map.md*

## 4. Reference brief
- "Feels like X's Y" sentence
*Source: outputs/m1.5-direction-brief.md*

## 4.5 Aesthetic tone (locked)
- Primary tone + secondary accent (if hybrid)
- Implications locked for build: typography family, colour register, spacing density, decoration budget
*Source: outputs/m1.5-direction-brief.md Section 1.5*

## 4.6 Mood board + palette (locked)
- Locked palette: 4 hex tokens (background, surface, primary text, accent) with plain-English names
- Locked visual references (3-5): brand/product + one-line "what to borrow"
- Image-gen prompt (final, copy-paste-ready) for re-test in Nano Banana / Midjourney / DALL-E / Imagen
- "Why this palette won" rationale
- Pointer: see also `outputs/m1.5-mood-board.md` for the 3 candidate palettes considered + their prompts
*Source: outputs/m1.5-direction-brief.md Section 1.5.5 + outputs/m1.5-mood-board.md*

## 5. Design vectors (3)
- Mood / Guidance / Copy
*Source: outputs/m1.5-direction-brief.md*

## 6. Primary emotion
- Phrase the design must evoke
*Source: outputs/m1.5-direction-brief.md*

## 7. Voice & copy rules
- Person form, tone register, banned phrases (full list)
*Source: outputs/m1.6-visual-study.md*

## 8. Visual patterns (5-7)
- Borrowed moves with one-line "how it shows up in our build"
*Source: outputs/m1.6-visual-study.md*

## 9. Screen spec — per screen
- Purpose, first-3-seconds, ASCII layout, components, behaviour
*Source: outputs/prototype/SCREEN-SPEC.md*

## 10. Interaction notes
- Iteration-pass deltas + 5-lens UX/Visual fixes for v1.1
*Source: outputs/prototype/iteration logs + 5-lens review*

---
*Built with Manthan by Palash Somani (pAI)*
```

---

## Schema — `handoff-tech.md`

```markdown
# Tech / Frontend Engineer Handoff — <Product Name>

*Generated: YYYY-MM-DD. Source: Manthan artifact set v<n>. Reading time: ~5 min.*

## 1. Product frame (1-paragraph)
- Name + one-line idea + primary user
*Source: outputs/m1.1-scope-skeleton.md*

## 2. Prototype structure
- File: outputs/prototype/index.html
- Screens: N, each in `<section data-screen="N">`
- Scaffold inheritance: outputs/prototype/scaffold.css (classes, tokens)
- Mobile viewport ranges tested: 320 / 375 / 414 px
*Source: outputs/prototype/index.html*

## 2.5 Color tokens (locked palette — Lovable / Cursor / Figma ready)
- 4 hex tokens with semantic names: `--bg`, `--surface`, `--text`, `--accent`
- Each token's plain-English name (for design discussion)
- Locked image-gen prompt (so any consumer — designer, vibe-coding tool, Figma plugin — can re-render the home screen visualization for sanity-check)
- Pointer to `outputs/m1.5-mood-board.md` for the 3 candidates considered
*Source: outputs/m1.5-direction-brief.md Section 1.5.5*

## 3. Feature → screen mapping
- Each of 5 Pareto features → which screen(s) it lives on
*Source: outputs/m1.4-pareto-v1-lock.md + outputs/prototype/SCREEN-SPEC.md*

## 4. Mock data shapes
- Extracted from prototype + any AI surface inputs
- JSON-like skeleton, no real PII
*Source: outputs/prototype/index.html + outputs/m1.5-direction-brief.md AI Surface Map*

## 5. State + interaction model
- `showScreen(n)` nav function pattern
- Local state slots (streak, case-progress, report-card data)
*Source: outputs/prototype/index.html*

## 6. Build constraints (carry into v1)
- Explicit non-goals from scope skeleton Field 9
- Voice rules (banned phrases)
- Scaffold tokens (do not hard-code)
*Source: outputs/m1.1-scope-skeleton.md + outputs/m1.6-visual-study.md*

## 7. Known risks (tech-relevant)
- Risks from m1.1 Field 10 that intersect with implementation
*Source: outputs/m1.1-scope-skeleton.md*

## 8. v1.1 queue (tech-relevant items)
- From 5-lens "System" and "UX" weaknesses with triggers
*Source: outputs/prototype/5-lens review*

---
*Built with Manthan by Palash Somani (pAI)*
```

---

## Schema — `handoff-ai-eng.md` (conditional)

**Only generated if `outputs/m1.5-direction-brief.md` contains an AI Surface Map with ≥1 surface.**

```markdown
# AI / ML Engineer Handoff — <Product Name>

*Generated: YYYY-MM-DD. Source: Manthan artifact set v<n>. Reading time: ~6 min.*

## 1. Product frame (1-paragraph)
- Name + one-line idea + primary user
*Source: outputs/m1.1-scope-skeleton.md*

## 2. AI Surface Map (full, verbatim)
- One block per surface: { job, rubric, input, output, failure mode, eval examples }
*Source: outputs/m1.5-direction-brief.md*

## 3. Data flows per surface
- Input → model → output → downstream consumer
- Where it surfaces in the prototype
*Source: derived from surface I/O + outputs/prototype/SCREEN-SPEC.md*

## 4. Eval anchors per surface
- Concrete examples of pass/fail outputs from the rubric
*Source: outputs/m1.5-direction-brief.md*

## 5. Feature → surface mapping
- Each of 5 Pareto features → which AI surface(s) it depends on
*Source: outputs/m1.4-pareto-v1-lock.md + outputs/m1.5-direction-brief.md*

## 6. Mock data shapes
- Input schemas, output schemas, edge-case examples
*Source: outputs/m1.5-direction-brief.md*

## 7. Failure mode inventory
- Per surface: what wrong output looks like, what triggers it
*Source: outputs/m1.5-direction-brief.md*

## 8. Known AI-relevant risks
- Risks from m1.1 Field 10 that touch model behaviour or grading
*Source: outputs/m1.1-scope-skeleton.md*

## 9. v1.1 queue (AI-relevant items)
- 5-lens "Product" and "Emotion" weaknesses that map to AI behaviour
*Source: outputs/prototype/5-lens review*

---
*Built with Manthan by Palash Somani (pAI)*
```

---

## What every handoff is NOT

- Not a re-dump of the source artifacts. (Audience-shaped, not artifact-shaped.)
- Not a summary of Manthan as a method. (The recipient doesn't need to know how it was built.)
- Not a place for Claude's commentary. (No "I think this means…" — every claim is sourced.)
- Not editable by hand. (Edits go to source artifacts; handoffs regenerate.)

---

## Phase 2 — current state (per-module sync live)

| When syncer runs | Files regenerated |
|---|---|
| Once at end of m1.6 after the final `principle-auditor` SHIPS | All 4 handoff files regenerated from the full source artifact set |

**Drift prevention:** by regenerating from source at end-of-workshop, drift is mathematically impossible — there is no edit-merge surface. A manifest is not required; the source artifacts themselves are the manifest.

**Routing:** m1.6 invokes the `handoff-syncer` inline within its Step 6.9 (final audit + close). m1.1–m1.5 do not invoke the syncer — handoffs are regenerated once, at the end, against the complete artifact set.

---

*Built with Manthan by Palash Somani (pAI)*
