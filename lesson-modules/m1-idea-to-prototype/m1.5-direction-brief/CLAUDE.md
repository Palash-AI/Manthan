# Module 5: Direction Brief

> **Skill it teaches:** Pin the directional feel + AI architecture + positioning before any code runs.
> **Capability shown:** Sequential decision-making with structured choice (AskUserQuestion when self-serve).
> **Estimated time:** ~4 minutes (live: Palash manages pace. Self-serve: learner takes whatever time they need).
> **Output:** `outputs/m1.5-direction-brief.md` containing reference brief, 3 design vectors, primary emotion, AI surface map, and positioning one-liner.

---

## Agent context (do not display to learner)

> Read `@.claude/SCRIPT_INSTRUCTIONS.md` first if not already loaded. **No fourth-wall breaking.** Begin with the first SAY block. Do not summarize this file.
>
> Delivery mode: self-serve. In live mode, Palash narrates over the top.
>
> The teaching moment is **AI surface mapping** — naming every place an AI does work as its own micro-product. Most PM curricula skip this. For 2026+ products it's the highest-leverage skill they don't yet have.
>
> Apply `@PRINCIPLES.md` and `@DOCUMENT-STANDARDS.md` silently throughout.
>
> **Archetype-name lock:** Use the exact primary-archetype name from Module 1's scope skeleton (`outputs/m1.1-scope-skeleton.md` Field 3). For the worked example that's *"The Anxious Aspirant"*. Do NOT improvise a sharper name (e.g., "Night-Before Rehearser") even though the JTBD wording invites it. The positioning sentence, reference brief, emotion paragraph, and AI surface map ALL use this same name.

---

## Teaching Flow

### Step 1: Open the module

**SAY:**

"Welcome to Module 5.

We have scope, evidence, archetypes, and a Pareto-cut v1. We're three minutes from writing code. But if we walk into Claude Code right now and say 'build it', we'll get generic SaaS. Light grey background, blue buttons, no personality.

Module 5 is the small brief that prevents that. Four micro-fields. Four minutes.

Are you ready?"

**STOP:** Wait for "yes" / equivalent.

---

### Step 2: The reference brief

**SAY:**

"First field: the reference brief. One sentence. Format:

> *'Feels like [reference product]'s [property], for [our archetype] doing [their job].'*

This sentence is the anchor for the whole prototype. Claude Code will pick layout, copy energy, and visual restraint based on this one line. It's the cheapest, highest-leverage move in the module.

Take a shot first — what reference comes to mind for PM Companion, given the Anxious Aspirant and what she's hiring this for? Don't overthink. Just one product whose *feel* you'd want to borrow."

**STOP:** Wait for the learner's attempt.

**Acknowledge their answer in one line — what's good about it, what feels missing.** Be specific, not generic.

**SAY:**

"Good. Now let me put three options on the table, so you can compare yours against alternatives. For PM Companion, the strongest candidates are:

| # | Reference brief | The property we'd be borrowing |
|---|---|---|
| 1 | Feels like **Duolingo's daily-practice loop**, for the Anxious Aspirant building professional muscle in 15-min reps | The habit-shaped loop — short, daily, gamified, return-tomorrow |
| 2 | Feels like **Notion's calm precision**, for the Anxious Aspirant thinking carefully without distraction | The visual quiet — hidden until needed, focused workspace, no celebration |
| 3 | Feels like **Khan Academy's earned progression**, for the Anxious Aspirant building from zero with feedback at every step | The mastery framing — feedback per step, earned advancement, no shortcuts |

Each one would produce a different prototype. Duolingo would push us toward streaks and visible progress. Notion would push us toward calm and restraint. Khan Academy would push us toward a step-by-step mastery view.

Which one fits the Anxious Aspirant best — option 1, 2, or 3? Or do you want to lock the version you suggested earlier?"

**STOP:** Wait for the learner's pick.

**ACTION:** Write the chosen reference brief to `outputs/m1.5-direction-brief.md`:

```
# Direction Brief — PM Companion

## 1. Reference brief
"[Whatever the learner picked]"
```

**SAY:**

"Locked.

Here's why this lock matters: that one sentence will quietly steer every visual choice Claude Code makes in Module 6 — layout, spacing, copy register, where progress shows, what's celebrated. Without it, Claude Code defaults to generic SaaS. With it, the prototype directionally reflects the choice you just made.

The reference is about the *behaviour*, not the visual. We're not copying Duolingo's owl or Notion's font. We're copying the property that fits our archetype."

**STOP:** Wait for confirmation.

---

### Step 3: The 3 design vectors

**SAY:**

"Second: three design vectors from `lite-03` of the source skill. We pick three because plain HTML can express three. Vectors that need motion, color depth, or layout immersion don't translate to an HTML prototype, so we save those for the design phase later.

**Important — each vector is a *scale*, not a binary choice.** You can land anywhere along it. Here are the three scales, with examples of where products land along each so you can see the range before we pick our dot:

### Mood — *Utility ↔ Cinematic*

| Position | Example | Vibe |
|---|---|---|
| Pure utility | Linear | Cool, sharp, no decoration |
| Utility + warmth | Notion | Cream, calm, paper-like |
| Polished functional | Stripe | Trustworthy, restrained |
| Editorial | NYT Cooking | Serif headlines, generous whitespace |
| Cinematic | Apple Music | Immersive, hero-led, theatrical |

### Guidance — *Hidden ↔ Hand-holding*

| Position | Example | Vibe |
|---|---|---|
| Power-user invisible | Vim | Nothing on screen; user knows everything |
| On-demand | Notion | Hints appear when you ask, not before |
| Contextual nudges | Linear | Tiny prompts at the right moment |
| Walkthroughs | Intercom | Step-by-step tours of features |
| Wizard-style | TurboTax | Hand-held through every decision |

### Copy — *Instructional ↔ Dramatic*

| Position | Example | Vibe |
|---|---|---|
| Reference-doc terse | Stripe docs | "GET /v1/charges. Returns charge object." |
| Instructional + warm | Duolingo | "Nice work! Try this next." |
| Conversational | Linear | "Add an issue. Drag to reorder." |
| Opinionated | Basecamp | "Don't do daily standups. Here's why." |
| Dramatic | Self-help apps | "Embark on your journey to better thinking." |

**Each vector is a dot you place on the scale.** Now I'll show you where we land for PM Companion — and why."

**ACTION:** Write the choices to the file:

```
## 2. Design vectors

| Vector | Where we land | Why this dot |
|---|---|---|
| Mood | Utility + warmth (Notion-side) | Anxious Aspirant needs trust the night before her review. Pure utility (Linear) feels cold; cinematic (Apple Music) feels theatrical. Warm-utility builds trust without theatre. |
| Guidance | Hidden until needed (Notion-side) | She wants to think, not be told. Hints on demand; rubric appears only after she answers. |
| Copy | Instructional + friend energy (Duolingo-side) | "Here's a question to try" — not "Embark on your journey." Direct, warm. |
```

Append to the file. Show the file's current state so the learner sees the three dots placed.

**SAY:**

"Three dots placed. Each one rules out a wrong default:

| What we rejected | Why |
|---|---|
| Cinematic | Would feel like inspiration porn for the Anxious Aspirant |
| Hand-holding | Would feel patronising — she's not a beginner |
| Dramatic | Would feel like a self-help book — wrong register |

Naming what we're not is half the job.

**Anything you'd shift?** You can slide any of the three dots along its scale, or argue for a completely different axis if it serves the archetype better (e.g., Density · Pace · Tone · Authority — see below).

Other axes available if relevant (not in the default 3 for HTML, but worth knowing):

| Axis | Range | When it matters |
|---|---|---|
| Density | Sparse ↔ Information-rich | Linear vs Bloomberg Terminal |
| Pace | Slow / contemplative ↔ Fast / kinetic | Calm vs TikTok |
| Tone | Earnest ↔ Playful | Notion vs Slack |
| Authority | Peer ↔ Expert | A friend vs a coach |

These mostly matter at design-detail stage. For the brief, the three baked-in scales (Mood, Guidance, Copy) are the right ones."

**STOP:** Wait for the learner. If they propose shifting a dot OR swapping in a different axis, walk through the trade-off (what gets gained, what gets lost for the archetype), let them decide, then update the file before continuing.

---

### Step 4: Primary emotion + AI surface map

**SAY:**

"Third: one line on primary emotion. What should the user feel in the core moment of the loop?"

**ACTION:** Append:

```
## 3. Primary emotion
"Sharper. Earned, not flattered."
```

**SAY:**

"That's it. One adjective and one disclaimer. *Sharper* — the outcome. *Earned, not flattered* — the rejection. We don't want our user to feel falsely good. We want them to feel actually better.

If you'd shift this to a different emotion — say so. *Confident* would push us toward celebration. *Calm* would push us toward minimalism. *Sharper* sits between, which is why it fits the Anxious Aspirant. Want to keep, swap, or land on a new one?"

**STOP:** Wait for the learner. If they propose a swap, walk through what each emotion implies for the build, let them choose, update the file.

**SAY:**

"Fourth, and most important: the AI surface map. For an AI-native product, every place an AI does work is its own micro-product. Naming them now prevents prompt rot later."

**ACTION:** Append. **Push each surface deeper than "what it does" — include rubric / contract / failure modes.** This is what prevents the build from defaulting to thin AI:

```
## 4. AI surface map

For each AI surface, six fields. Shallow specs produce mega-prompts that drift; 
deep specs let each surface be evaluated and improved independently.

### Surface 1: [Name]
- **Job:** [what this AI does, in one line]
- **Rubric / contract:** [the specific criteria the output must meet — 
  not just "good"; the dimensions or schema]
- **Input:** [what gets passed in — be specific about fields]
- **Output:** [the shape — JSON schema / text format / score breakdown]
- **Failure modes:** [3-5 specific ways this can go wrong + how to detect]
- **Eval anchor:** [1-2 example inputs + expected outputs for calibration]

### Surface 2: ...
(same structure)
```

**Worked example for PM Companion's Question grader (illustrates the depth — derive fresh for other ideas):**

```
### Surface: Question grader

- **Job:** Score each user question across PM thinking dimensions; surface 
  which dimensions are strong vs gaps.

- **Rubric / contract:** 
  Five dimensions, each scored 0-3:
  1. Clarification — does the Q clarify scope before solving?
  2. User-Centric — does the Q ground in a specific user or segment?
  3. Metric-Aware — does the Q pair to a measurable outcome?
  4. Segmentation — does the Q break aggregate into cohorts?
  5. Tradeoff Thinking — does the Q surface a real tradeoff?
  
  Overall score = sum / 15, rounded to /10.
  Highlight the 1-2 dimensions this Q hits hardest.

- **Input:**
  { case_context: string,
    user_question: string,
    prior_questions: [string],
    archetype: string }

- **Output:**
  { dim_scores: { clarification: 0-3, user_centric: 0-3, metric: 0-3, 
                  segmentation: 0-3, tradeoff: 0-3 },
    dims_hit: [list of dim names this Q strongest on],
    overall: 0-10,
    one_line_why: "string — what made this strong / what would sharpen it" }

- **Failure modes:**
  - Generic scoring (every Q gets 6/10) — detect: variance < 1.5 across 30 samples
  - Inflated scoring (avg > 8) — detect: avg > 7.5 across cohort
  - Dimension mismatch (Q clearly about clarification, no clarification dim hit) — detect: human-in-loop spot check
  - Why-line doesn't reference the user's actual words — detect: regex check 
    for verbatim phrase overlap

- **Eval anchor:**
  Input Q: "Did anything else change in the same week?"
  Expected: dims_hit = [clarification], dim_scores = 
    { clar: 2, uc: 1, metric: 0, seg: 0, tradeoff: 0 }, overall ≈ 3/10,
    why = "Useful clarification instinct, but generic — the case already 
    says the team shipped a redesign. Sharper: which user segment changed?"
```

**SAY:**

"Notice the depth here. Each surface has six fields, not two — job, rubric, input, output, failure modes, and an eval anchor. This is what separates 'an AI feature' from 'a quality AI feature.'

For PM Companion's grader, the rubric is the five PM thinking dimensions. That depth came from the User Need Map's Feedback dimension — specifically the need 'WHICH part of my thinking was strong vs weak.' If we'd left the grader at 'scores 0-10,' the build agents would have produced a single-number grader and missed the actual moat.

Apply this depth to every surface. For v1 we won't write all four prompts in this workshop — but naming them at this depth means when we do write them in W3, we know exactly what each needs to do.

Any AI surface you'd add, remove, or merge? Any surface where the rubric feels shallow? Argue with me, or move on."

**STOP:** Wait for the learner. If they propose a change (different rubric, missing failure mode, merged/split surface), walk through the trade-off and update the file before continuing.

---

### Step 5: The positioning one-liner

**SAY:**

"One last addition: positioning. One sentence — but it does double duty as a strategic decision AND a marketing input.

**Here's the framework** — six slots:

| Slot in framework | Question it answers | Our answer |
|---|---|---|
| **For [archetype]** | Who is this for? | The Anxious Aspirant PM |
| **[Product] is a [category]** | What is it? | PM Companion is a *daily practice gym* |
| **that [unique value]** | What's the unique value? | Gives calibrated feedback on her thinking |
| **unlike [alternative #1]** | Who does it beat? | Lenny's Newsletter |
| **who [limitation #1]** | What do they fail at? | Consumption-only |
| **...and [alternative #2]** | + another? | ChatGPT |
| **who [limitation #2]** | What do they fail at? | Doesn't push back |

**The assembled sentence — the artifact that ships into the v1 PRD:**

> *'For the Anxious Aspirant PM, PM Companion is a daily practice gym that gives calibrated feedback on her thinking, unlike Lenny's Newsletter which is consumption-only and ChatGPT which doesn't push back.'*

**Why this works — and what failure looks like for contrast:**

| Type | Example | Problem |
|---|---|---|
| ❌ Vague | *'The best learning app for PMs'* | Doesn't decide anything. No user, no value, no competitor. |
| ❌ Aspirational | *'We help PMs reach their potential'* | No measurable claim. No named alternative. |
| ✅ Specific (ours) | [the sentence above] | Names archetype, category, unique value, AND two competitors with their specific limitations |

Specific positioning makes feature cuts easier in v2 — when a feature debate comes up, you ask *'does this strengthen our daily-practice-gym claim, or weaken it against ChatGPT?'* That decides things."

**ACTION:** Append the assembled sentence to `outputs/m1.5-direction-brief.md`:

```
## 5. Positioning

"For the Anxious Aspirant PM, PM Companion is a daily practice gym 
that gives calibrated feedback on her thinking, unlike Lenny's 
Newsletter which is consumption-only and ChatGPT which doesn't 
push back."
```

**SAY:**

"Anything you'd swap?

| Possible swap | What it'd change |
|---|---|
| Different competitor (Reforge instead of Lenny? Notion's templates?) | Shifts the comparison axis — Reforge = depth-vs-daily; Notion templates = structure-vs-practice |
| Different category framing (gym vs. coach vs. studio) | Shifts the metaphor — gym = effort; coach = guidance; studio = creation |
| Different limitation framing | Shifts what we claim to do better |

Quick override moment before we audit."

**STOP:** Wait for the learner. If they propose a swap, walk through the trade-off (e.g., positioning against Notion vs. Lenny implies different feature priorities). Update the file if they decide to swap.

---

### Step 6: Run the principles check

**SAY:**

"One first-principles check before the auditor. From first principles — given who this user is and what they need to succeed — does this direction brief give the build agents enough to make every visual + AI decision? Anywhere the brief feels thin? Any AI surface where the rubric is still too generic?"

**STOP:** Wait for the learner. If they push deeper on any field, edit the file.

**SAY:**

"Now the auditor."

**ACTION:** Call `principle-auditor`:

```
Use the Task tool to invoke principle-auditor with prompt:
"Audit outputs/m1.5-direction-brief.md against PRINCIPLES.md and 
DOCUMENT-STANDARDS.md. Confirm the AI surface map is concrete and 
the positioning explicitly names competitors and limitations."
```

**Display verdict.** If REVISE: walk through, edit, re-run. If SHIP: proceed.

**SAY (if SHIP):**

"Cleared.

**Two takeaways before we move on:**

1. **The reference brief is the cheapest leverage in the entire workshop.** One sentence prevents the prototype from defaulting to generic SaaS. Use it on every project.
2. **The AI surface map is the move most PM curricula skip and that 2026+ products demand.** Every user-facing AI moment is its own micro-product. Name them; don't merge them.

Ready for /manthan-6 — the build?"

**STOP:** Wait for confirmation.

---

*Built with Manthan by Palash Somani (pAI)*
