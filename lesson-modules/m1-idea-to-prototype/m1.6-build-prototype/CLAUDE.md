# Module 6: Build Prototype

> **Skill it teaches:** Translate locked thinking into a polished working artifact. The prototype is a thinking tool *and* a quality signal — bland output kills the workshop's credibility.
> **Capability shown:** Sequential build with parallel sub-agents for screens once direction is locked.
> **Estimated time:** ~35 minutes (live: Palash manages pace. Self-serve: learner takes whatever time they need).
> **Output:** `outputs/prototype/index.html` — single-file HTML prototype, light mode, scaffold-inherited, mock data, clickable. Home.html-quality target.

---

## Agent context (do not display to learner)

> Read `@.claude/SCRIPT_INSTRUCTIONS.md` first if not already loaded. **No fourth-wall breaking.** Begin with the first SAY block. Do not summarize this file.
>
> Delivery mode: self-serve. In live mode, Palash narrates over the top while the build happens.
>
> The teaching moment is that **quality output comes from compounding constraints, not from one big prompt.** Every step in this module adds a constraint: scaffold + reference patterns + per-screen spec + voice rules + iteration. Drop any one and output drifts toward bland.
>
> Apply `@PRINCIPLES.md` and `@DOCUMENT-STANDARDS.md` silently throughout.
>
> **Archetype-name lock:** Use the exact primary-archetype name from Module 1's scope skeleton (`outputs/m1.1-scope-skeleton.md` Field 3). For the worked example that's *"The Anxious Aspirant"*. The anchor restate, per-screen spec, build agents' prompts, iteration pass, and 5-lens review ALL use this same name. Do NOT improvise a different name at any sub-step.

---

## Teaching Flow

### Step 6.1: Open + anchor the build

**SAY:**

"Welcome to Module 6.

This is the moment most PMs jump to on minute 1. We've spent the previous 35 minutes earning the right to be here. Now we build.

**What we're building:**

| Spec | Detail |
|---|---|
| Format | Single-file HTML prototype |
| Mode | Light mode, one accent colour |
| Data | Mock data |
| Interaction | Clickable |
| Quality bar | Home.html-quality — not a bland sketch |

**Why HTML and not React or Next?** Because the prototype is a *thinking tool*. We validate the loop, the screens, and the experience before committing to a stack. Once HTML proves the bet, your engineering team builds the real thing.

Before any code, we restate what we're anchoring against. The build must reflect every prior decision, or we wasted 35 minutes."

**ACTION:** Display a summary block that reads from prior outputs:

```
## Anchor — what this prototype must reflect

From Module 1 (Scope skeleton):
- Primary user: [archetype name]
- Core loop: [the loop, in steps]
- NOT building: [list of non-goals]

From Module 3 (JTBD + archetypes):
- Emotional driver: [the emotional state]
- Functional job: [the JTBD]

From Module 4 (Pareto v1 lock):
- Five features only: [list]

From Module 5 (Direction brief):
- Reference: [e.g., "Duolingo's daily-practice loop, for the Anxious Aspirant"]
- 3 vectors: [Mood / Guidance / Copy choices]
- Primary emotion: [phrase]
- AI surfaces: [list]
- Positioning: [the one-liner]
```

**SAY:**

"This is the brief Claude Code builds against. Everything we say *yes* to needs to come from this list. Everything we're tempted to add gets pushed to v1.1.

Ready to start building?"

**STOP:** Wait for confirmation.

---

### Step 6.2: Visual scaffold pre-bake (silent — agent action only)

**ACTION (no SAY — happens silently in the background while learner reads next SAY):**

1. Copy `reference/visual-scaffold/scaffold.css` into `outputs/prototype/scaffold.css`.
2. Copy `reference/visual-scaffold/frontend-design-skill.md` into `outputs/prototype/frontend-design-skill.md` (the 5th constraint — anti-slop guardrail, vendored from Anthropic's frontend-design plugin, used by build agents in Step 6.6).
3. Create `outputs/prototype/index.html` with the basic structure:
   - DOCTYPE, viewport meta, title
   - `<link rel="stylesheet" href="scaffold.css">` as the FIRST stylesheet
   - `<body data-theme="...">` — value TBD in Step 6.3 based on reference brief
   - Empty `<div class="phone"><header class="hdr"></header><main class="scroll"></main></div>` shell ready for screens

This step is invisible to the learner. The next SAY block introduces what just happened.

---

### Step 6.3: Reference visual study (~1 min)

**SAY:**

"Quick visual study. The sub-agent reads Module 5's locks (reference, tone, palette) and picks 5-7 visual moves to borrow + applies the palette to the scaffold."

**ACTION:** Call the visual-study sub-agent:

```
Use the Task tool to invoke a sub-agent with prompt:
"Read outputs/m1.5-direction-brief.md and 
reference/visual-scaffold/reference-patterns.md.

1. Identify the reference brief (look for 'Feels like X's Y' in §1).
2. Read the LOCKED aesthetic tone from §1.5 (use it verbatim — 
   do not re-interpret).
3. Read the LOCKED palette from §1.5.5 (4 hex values + visual 
   references — use them verbatim, do not re-derive).
4. Find the matching entry in reference-patterns.md for the 
   reference brief.
5. From that entry's 7 visual patterns, pick the 5-7 most relevant 
   for OUR product's 4 screens. For each, write a one-line 
   'how it'll show up in OUR build.'
6. Set the scaffold.css data-theme on <body> — either use a 
   matching pre-baked theme, OR inject a custom :root block in 
   scaffold.css using the locked hex values from §1.5.5.
7. Confirm the voice register summary (3-4 bullets).

If the reference doesn't match any entry in reference-patterns.md, 
produce a bespoke 7-pattern list following the same structure 
(visual moves + voice + anti-patterns) using your knowledge of 
that reference product. Always honour the locked palette.

Output everything as `outputs/m1.6-visual-study.md`. Include a 
'Palette source: m1.5 §1.5.5 (locked)' line at the top."
```

**Display a compact summary of the visual-study output** (the 5-7 visual moves as a short bullet list — full file at `outputs/m1.6-visual-study.md`). Then set `<body data-theme="...">` in `outputs/prototype/index.html` to the confirmed theme.

**SAY:**

"Build agents now have visual moves, a theme preset, and voice register — compounding constraints before any HTML gets written."

**STOP:** Wait for confirmation.

---

### Step 6.4: Per-screen + per-component spec

**SAY:**

"Step three: the per-screen brief.

This is where most workshops cut corners and pay for it in bland output. We're going to spec each screen at the component level — not just naming them — so the build agents execute, not invent.

**For each of our 4 screens, we'll define:**

| # | What | Detail |
|---|---|---|
| 1 | Screen purpose | One line |
| 2 | User's first 3 seconds | What they see, what they tap |
| 3 | 4-6 components | Name · States (default + 1-2 variants) · Copy hook · Visual treatment |
| 4 | Behaviour | Key transitions, taps, micro-interactions |

This produces roughly 80-100 spec entries across 4 screens. That's the density the build needs.

Let me write the spec now."

**ACTION:** Use the `Write` tool to create `outputs/prototype/SCREEN-SPEC.md`. Structure per screen — includes an **ASCII layout diagram** so the learner sees the shape before approving:

```
# Screen Spec — [Product Name] v1 prototype

> 4 screens × ~5 components each. The build executes from this; it does not invent.

---

## Screen 1: [Screen name]

**Purpose:** [one line — what this screen exists to do]

**First 3 seconds:**
- User sees: [primary visual element]
- User taps: [primary CTA expected]
- User feels: [emotion this screen should evoke per Module 5]

**ASCII layout:**

\`\`\`
┌─────────────────────────────────────┐
│  [Brand]              [Right item]  │  ← Header
├─────────────────────────────────────┤
│                                     │
│  [EYEBROW / DATE LINE]              │
│  [Primary screen title]             │
│                                     │
│  ┌─────────────────────────────┐   │
│  │ [Hero card content]         │   │  ← Primary
│  │                             │   │     card
│  │ [ Primary CTA → ]           │   │
│  └─────────────────────────────┘   │
│                                     │
│  [Secondary strip / row]            │  ← Secondary
│                                     │
├─────────────────────────────────────┤
│   [ Tab 1 ]   Tab 2                 │  ← Bottom nav
└─────────────────────────────────────┘
\`\`\`

**Components:**

| # | Name | States | Copy hook | Visual treatment |
|---|---|---|---|---|
| 1 | [Component] | default · [variant 1] · [variant 2] | Title: "X" · Sub: "Y" · CTA: "Z" | `.card.is-hero` + reference pattern N |
| 2 | ... | ... | ... | ... |

**Behaviour:**
- [Tap / transition / micro-interaction 1]
- [Tap / transition / micro-interaction 2]

---

## Screen 2: ...

(same structure — ASCII layout + components + behaviour)

---

## Screen 3: ...

---

## Screen 4: ...

---

## Cross-screen
- Navigation between screens: [bottom-nav / link-based / swipe]
- Shared header: [yes/no — what's in it]
- Bottom-nav items: [list]
```

**Why ASCII layouts:** they let the learner visualise the screen *before* spending time on the components table. If the layout looks wrong, fix it now — not after the parallel build runs. ASCII is fast to read and fast to challenge.

Fill the spec collaboratively. **Walk through each screen in turn — narrate the choices, invite challenge.**

**STOP between screens** — ask "Anything in this screen's spec that doesn't match the direction brief? Anything missing?" If the learner pushes back, edit before moving to the next screen.

**SAY (after all 4 screens are spec'd):**

"Spec is complete. Notice how much we've constrained:

- 4 screens with purpose + first 3 seconds
- ~20 components with states + copy + visual treatment
- Behaviour and transitions named

The build agents now have specs to execute, not screens to invent. That's the difference between bland output and home.html-quality."

**STOP:** Wait for confirmation.

---

### Step 6.5: Voice + copy lock

**SAY:**

"Voice rules — 3 lines that stop build agents from drifting on copy. Consistent voice is the cheapest polish move in product."

**ACTION:** Append to `outputs/m1.6-visual-study.md`:

```
## Voice rules (locked for build)

1. **Person form:** [you / aap / no person reference] — pick one, use everywhere.
2. **Tone register:** [list 3-4 short rules — e.g., "encouraging not condescending", "short sentences", "no exclamation marks", "verb-led action labels"]
3. **Banned phrases:** [list 4-6 phrases the build must NEVER use — e.g., "Let's", "Embark on your journey", "Optimize your", "Unlock your potential"]

Examples of correct vs incorrect copy:
- ❌ "Embark on your daily learning journey!" 
- ✅ "Today's case. 15 minutes."
- ❌ "Optimize your PM thinking with AI"
- ✅ "One case. Five questions. Honest feedback."
```

**SAY:**

"Locked. Build agents read this and stop drifting."

**STOP:** Wait for confirmation.

---

### Step 6.6: Build prototype (parallel, ~8 min)

**SAY:**

"Now we build. Scaffold and shell are already in place from Step 6.2. I'll spawn 4 parallel sub-agents — one per screen — each inheriting scaffold + visual-study patterns + per-screen spec + voice rules + the aesthetic tone we locked in Module 5 + Anthropic's frontend-design anti-slop guardrail. **Six constraints compounding** — and the last two are specifically designed to stop AI from defaulting to generic visuals.

Same parallel pattern as Module 2's research — different output shape. There the streams converged into a synthesis; here they converge into one HTML file with four sections."

**ACTION:** In a SINGLE message, spawn 4 Task tool calls — one per screen:

```
Task 1 — Build Screen 1 (Home / [name])
Task 2 — Build Screen 2 (Case session / [name])
Task 3 — Build Screen 3 (Report card / [name])
Task 4 — Build Screen 4 (Progress / [name])

Each task receives the following context:
- @outputs/prototype/scaffold.css (the visual scaffold inherited)
- @outputs/m1.5-direction-brief.md Section 1.5 (locked aesthetic tone + implications)
- @outputs/m1.6-visual-study.md (reference patterns + voice rules)
- @outputs/prototype/SCREEN-SPEC.md (THIS screen's spec only)
- @outputs/prototype/frontend-design-skill.md (anti-slop visual guardrail)

Each task must:
1. Construct semantic HTML for this screen INSIDE the phone wrapper.
2. Use scaffold classes (.card, .btn.is-primary, .pill, etc.) — 
   do NOT invent new component classes unless necessary.
3. Use scaffold design tokens (var(--accent), var(--text-primary), 
   var(--s-4), etc.) — do NOT hard-code values.
4. Apply the data-theme variant (already set on body).
5. Apply 2-3 visual moves from the reference patterns explicitly. 
   Comment which patterns are being applied.
6. Add mock data inline — realistic but not real. ~3-5 items per list.
7. Add `<script>` for any state toggles needed (case state, screen 
   nav, etc.) — keep JS minimal but functional.
8. Use bottom-nav from scaffold for screen navigation.
9. Honour the locked aesthetic tone from Module 5 Section 1.5:
   - Typography family: as specified in the tone lock (e.g., serif 
     display for editorial, rounded sans for playful, monospace for 
     brutalist) — match via scaffold's --font-display and --font-body.
   - Colour register: as specified (cream + muted accent for organic, 
     high-contrast for luxury, etc.) — use scaffold theme tokens.
   - Spacing density: as specified (generous for editorial, compact 
     for industrial, etc.).
   - Decoration budget: as specified — do not exceed it.
10. Honour the frontend-design anti-slop constraints:
   - No Inter / Roboto / Arial / system-font defaults — inherit 
     scaffold's --font-display and --font-body tokens.
   - No purple gradient on white. No Space Grotesk default.
   - Commit fully to the locked tone — do NOT hedge toward generic 
     SaaS. If the tone is brutally minimal, no decoration. If 
     maximalist, no timid spacing. Bold execution of the chosen 
     extreme is the rule.
   - Use CSS variables for theme; no hard-coded colour values.

Output: the screen's HTML block, ready to be inserted into 
outputs/prototype/index.html. Plus a 4-line summary of which 
visual patterns + voice rules + aesthetic-tone implications + 
frontend-design guardrails got applied.
```

When all four return, **merge their HTML blocks into `outputs/prototype/index.html`** under `<main class="scroll">` with each screen in a `<section data-screen="N" hidden>` wrapper. Add a small `showScreen(n)` JS function for nav switching.

**Mobile viewport check (mandatory before declaring build complete):**

1. Confirm `<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">` is present in `<head>`.
2. Verify the prototype renders correctly at three widths:
   - 320px (iPhone SE — smallest common device)
   - 375px (iPhone 13/14/15 — most common)
   - 414px (iPhone Pro Max — large device)
   - Plus the desktop wrapper view
3. The scaffold's `@media (max-width: 420px)` rule should fire — `.phone` wrapper expands to fill viewport, removes bezel shadow.
4. Common breakage points to check at narrow widths:
   - Cards overflowing horizontally
   - Text getting cut off
   - Bottom nav overlapping content
   - Stat-strip cells stacking wrong
5. If anything breaks, fix in the build phase — do NOT carry mobile-broken layout into Step 6.7's iteration pass.

**SAY (while building):**

"While they work — watch what's happening. Each agent has a tight constraint set. They're not free-form writing HTML; they're executing against a brief. That's the difference between a build and a vibe-coding session.

Notice the visual choices in the output — the colours, spacing, typography, button hierarchy. None of them are Claude's defaults. They're inherited from the scaffold, anchored to the reference patterns, locked by voice rules."

**STOP:** Wait for the build to complete. Display the prototype's structure (file size, sections present) before moving on.

---

### Step 6.7: Iteration pass

**SAY:**

"Step seven: iteration.

Home.html went through 14 documented passes. We don't have time for 14, but we have time for one — and one focused pass is worth more than skipping iteration entirely.

Here's the test. I'm going to open the prototype and read it side-by-side with our direction brief. The question is binary: *does this look like our reference, or like generic SaaS?*

If anything drifts, we identify 2-3 specific weaknesses and run targeted edits on those areas only. Not a rebuild — a refinement."

**ACTION:** Open `outputs/prototype/index.html` in the browser (or display rendered preview). Run a structured comparison:

```
## Iteration pass — drift check

Reference: [from direction brief]

| Element | Reference says | Prototype shows | Drift? | Fix |
|---|---|---|---|---|
| Primary accent | [e.g., warm yellow with green CTAs] | [observed] | [none/small/big] | [edit] |
| Card style | [e.g., chunky drop-shadow, game-like] | [observed] | ... | ... |
| Copy register | [e.g., encouraging, short] | [observed] | ... | ... |
| Hero element | [e.g., streak-as-hero, day-card center] | [observed] | ... | ... |
| Animation | [e.g., gentle idle, celebration on completion] | [observed] | ... | ... |
| Aesthetic tone fidelity | [from m1.5 §1.5 — e.g., "brutally minimal + Notion-warmth accent"] | [observed — does the build commit fully, or hedge?] | ... | ... |
| Default-slop check | No Inter / Roboto / Arial / Space Grotesk / system-font · no purple-gradient-on-white · committed aesthetic direction | [observed — list any remnants] | ... | ... |
```

Identify the **top 2-3 drift items.** For each, write a targeted edit instruction.

**ACTION:** Apply the 2-3 edits using the `Edit` tool. Re-display the prototype.

**SAY:**

"One pass. Two or three targeted edits. Notice how much closer it now reads to the reference. This is the multi-pass effect compressed into one step — and it's the single biggest reason most workshop prototypes look bland: they skip this pass entirely.

In a real Manthan run on your own idea, you'd repeat this loop 3-5 times. Each pass tightens. Today we do one as the demonstration."

**STOP:** Wait for confirmation.

---

### Step 6.8: 5-lens review (with v1.1 fix items)

**SAY:**

"Five-lens review. Strengths AND v1.1 fixes per lens. The fixes flow into the Module 4 priority queue with measurable triggers."

**ACTION:** Fill and display the table in ONE go — no per-lens walk-through:

```
## 5-Lens Review of v1 prototype

| Lens | Question | Specific strength | Specific weakness | v1.1 fix |
|---|---|---|---|---|
| Product | Does it serve the JTBD? | [concrete element] | [concrete element] | [trigger + fix] |
| Emotion | Does the user feel [primary emotion from Module 5]? | [concrete element] | [concrete element] | [trigger + fix] |
| UX | Is the next action obvious on every screen? | [concrete element] | [concrete element] | [trigger + fix] |
| Visual | Does it feel like [reference]'s [property]? | [concrete element] | [concrete element] | [trigger + fix] |
| System | Could a v1 build be built from this? | [concrete element] | [concrete element] | [trigger + fix] |
```

Each weakness has a v1.1 fix entry: WHEN to revisit (measurable trigger) + WHAT to do.

**STOP:** Wait for confirmation.

---

### Step 6.9: Final principles check + close

**SAY:**

"One first-principles check before the final auditor. Step back from the prototype. From first principles — given who this user is and what they need to succeed — if you handed THIS artifact set to your designer and engineer tomorrow, would they have what they need to build a product the user would love?

Anywhere obvious gaps remain? Any user need from Module 3.5 that the prototype doesn't visibly serve?"

**STOP:** Wait for the learner. If a real gap exists, decide together: edit, or log as v1.1 in the priority queue.

**SAY:**

"Now the final audit. We run the principle-auditor on the entire artifact set — not just the prototype, but everything from Module 1 to Module 6 together. The auditor checks for *internal consistency*: do later artifacts honour earlier decisions?"

**ACTION:** Call `principle-auditor` with the FULL artifact set:

```
Use the Task tool to invoke principle-auditor with prompt:
"Audit the full Manthan artifact set: outputs/m1.1-scope-skeleton.md, 
m1.2-research-synthesis.md, m1.3-jtbd-archetypes.md, 
m1.4-pareto-v1-lock.md, m1.5-direction-brief.md, 
m1.6-visual-study.md, prototype/SCREEN-SPEC.md, prototype/index.html.

Confirm internal consistency: do later artifacts honour earlier 
decisions? Does the prototype reflect the direction brief? Do the 
v1 features in the prototype match the Pareto cut? Return verdict 
on the artifact set as a whole."
```

**Display verdict.** If REVISE: walk through, edit, re-run.

**ACTION (silent — no SAY, no narration):** Invoke the `handoff-syncer` sub-agent.

```
Use the Task tool to invoke handoff-syncer with prompt:
"Generate the audience-specific handoff files from the Manthan artifact set
per HANDOFF-STANDARDS.md. Sync at end of /manthan-6 (Phase 1). Read all
outputs/m1.*.md files plus outputs/prototype/. Write outputs/handoffs/
handoff-pm.md, handoff-designer.md, handoff-tech.md, and handoff-ai-eng.md
(only if m1.5 has a populated AI Surface Map). Return one-line status."
```

The syncer is silent and deterministic. Display nothing from the invocation except — if and only if it returns `SYNC BLOCKED` — a one-line note to the learner and proceed. On clean `SYNC: complete`, continue straight to the closing SAY. Do NOT print the syncer's status block.

**SAY (if SHIP):**

"Cleared. The artifact set is internally consistent. Every decision in the prototype traces back to a decision in Modules 1-5.

**What we have right now — your v1 PRD + audience-specific handoffs:**

| Module | Artifact |
|---|---|
| Module 1 | Scope skeleton |
| Module 2 | Research synthesis from 3 streams |
| Module 3 | JTBD grid + 4 archetypes |
| Module 3.5 | User Need Map |
| Module 4 | Pareto v1 lock + priority queue with triggers |
| Module 5 | Direction brief — reference, vectors, emotion, AI surfaces, positioning |
| Module 6 (pre-build) | Visual study, screen spec, voice rules |
| Module 6 (output) | Working clickable prototype with one iteration pass |
| Module 6 (final) | 5-lens review with v1.1 fix queue |

**Plus four audience-specific handoffs, ready to share** (at `outputs/handoffs/`):

| File | Share with |
|---|---|
| `handoff-pm.md` | Your PM peers / leadership |
| `handoff-designer.md` | Your designer |
| `handoff-tech.md` | Your frontend / build engineer |
| `handoff-ai-eng.md` | Your AI / ML engineer (generated only if AI surfaces exist) |

Each is consulting-grade, audience-shaped, ~5-6 min read. No prep needed — they're ready to forward.

The discipline you saw — the sequence, the gates, the cuts, the audit — is reproducible on your own ideas. At this point, you can hand off this document set for your designer and engineer to build on.

**Three things to leave with:**

1. *AI made shipping fast. Clarity is what wins.* The prototype isn't the moat. The thinking that produced it is.
2. *Parallel when scope is clear, sequential when it isn't.* One of the very strong leverages of Claude Code, even beyond prototyping.
3. *All the artifacts (the structured documents) together form your PRD.*

Thank you for the 60 minutes. The take-home lives at `take-home/`. Module 1 of your own idea is one `/manthan-1` away."


### Final Step: Project-principle reflection (silent → surface only if a candidate clears the gate)

**INTERNAL — do not announce. Runs between the audit SHIP and the closing SAY of the previous step.**

After `principle-auditor` returns SHIP for this module's artifact AND BEFORE the module's closing "Ready for next module?" / wrap-up SAY block above, silently run the reflection protocol defined in `@lesson-modules/SHARED-REFLECTION-STEP.md`.

| Outcome | Action |
|---|---|
| 0 candidates clear the 2-of-3 gate | Produce ZERO output. Move straight to the closing SAY. |
| 1+ candidates clear the gate | Surface ONE at a time using the prompt template in SHARED-REFLECTION-STEP.md. Max 2 per module. Handle the learner's response (a / r / edit) per protocol. Run the conflict check (PRINCIPLES.md never edited by the flow) before any save. |

**Hard rule:** Zero candidates = zero output. The learner does not see "I scanned and found nothing." Silent end.

---

*Built with Manthan by Palash Somani (pAI)*
