# Module 5: Direction Brief

> **Skill it teaches:** Pin the directional feel + aesthetic tone + palette + AI architecture + positioning before any code runs.
> **Capability shown:** Sequential decision-making with structured choice (AskUserQuestion when self-serve). Image-gen-prompt generation for visual feedback loop.
> **Estimated time:** ~8 minutes (live: Palash manages pace. Self-serve: learner takes whatever time they need).
> **Output:** `outputs/m1.5-direction-brief.md` (reference brief, aesthetic tone, palette, design vectors, primary emotion, AI surface map, positioning) + `outputs/m1.5-mood-board.md` (3 candidate palettes + visual references + 3 image-gen prompts).

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

### Step 2: Reference brief + aesthetic tone

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

The reference is about the *behaviour*, not the visual. We're not copying Duolingo's owl or Notion's font. We're copying the property that fits our archetype.

Now the aesthetic tone — *which visual extreme* to commit to. The difference between a prototype that looks designed and one that looks AI-generated.

AI defaults to a 'safe modern SaaS' look — light grey background, Inter font, rounded purple cards, blue CTAs. Every AI-generated interface looks the same because the model picks the comfortable middle on every visual axis. **The fix is to commit to ONE extreme, not a comfortable middle.** Anthropic literally shipped a plugin last month to enforce this. We're going to do the same thing manually, now, while it still counts as direction-setting.

Here are 10 visual directions in plain English. Each one decides things — typography, color, layout, spacing — in a coherent way. You don't need to know design jargon to pick one; the metaphor and the real-world example tell you everything."

**ACTION:** Display the tone vocabulary table:

```
| # | Tone | What it looks like | Feels like | Real-world examples |
|---|---|---|---|---|
| 1 | Brutally minimal | Lots of white space. One or two colours. No decoration. Only what's essential. | A clean Apple Store. | Linear, Things 3, Apple Notes |
| 2 | Maximalist chaos | Dense layouts. Bold typography. Multiple competing elements that somehow cohere. | A busy bazaar you eventually learn to navigate. | Bloomberg Terminal, Reddit, Are.na |
| 3 | Retro-futuristic | 80s sci-fi colours — synthwave neon, geometric shapes, CRT-screen vibes. | A Wes Anderson sci-fi movie. | Linear's marketing site, Replicate.com |
| 4 | Organic / natural | Earth tones. Soft curves. Hand-drawn elements. Paper textures. No harsh edges. | A forest cabin. | Headspace, Calm, Day One journal |
| 5 | Luxury / refined | High contrast. Generous spacing. Serif fonts. Deep blacks or muted golds. Restrained but rich. | Walking into a five-star hotel lobby. | Hermès, Aesop, Apple's high-end product pages |
| 6 | Playful / toy-like | Chunky shapes. Rounded corners. Bright primary colours. Bouncy animations. | A candy shop. | Duolingo, Kahoot, Lego.com |
| 7 | Editorial / magazine | Big typography. Generous photography. Asymmetric layouts. Content-first. | A Sunday newspaper supplement. | New York Times app, Substack, Pitchfork |
| 8 | Brutalist / raw | Exposed grids. Monospace fonts. No rounded corners. Sometimes deliberately "ugly." | An unfinished concrete building. | Hacker News, early Are.na, dev portfolios |
| 9 | Soft / pastel | Gentle gradients. Light pinks, lavenders, mints. Rounded everything. Friendly type. | A Korean café. | Hinge, Indian D2C beauty brands like Sugar |
| 10 | Industrial / utilitarian | Gridded. Dense data tables. Monospace where useful. No decoration. Function-first. | A workshop floor. | AWS console, Stripe Dashboard, GitHub |
```

**SAY:**

"Two notes on how to read this:

1. **Hybrids are allowed.** You can pick a *primary* tone with a *secondary accent* — e.g., 'brutally minimal with a Notion-warmth accent' is a valid pick. But the primary has to be one of these — not a vague middle.
2. **'Modern' and 'clean' are not options.** Those are AI's default words for *the comfortable middle.* If you find yourself wanting to pick them, that's the signal you haven't committed yet.

Take a shot first — based on our archetype and reference brief, which tone feels right for our build? Pick one (or one with an accent), and we'll compare against my recommendation."

**STOP:** Wait for the learner's pick.

**ACTION — RUNTIME GENERATION:** After the learner picks, generate a project-specific recommendation by reading the prior artifacts and reasoning from them. **Do not use a static recommendation.** The recommendation must be derived live from:

- `outputs/m1.1-scope-skeleton.md` — Primary archetype (Field 3) and JTBD (Field 5)
- `outputs/m1.3-jtbd-archetypes.md` — Emotional and social jobs of the archetype
- `outputs/m1.5-direction-brief.md` — Section 1 (reference brief just locked)

Format the recommendation as:

```
My recommendation: <Primary tone> [+ <secondary accent>, if a hybrid fits]

Why this fits:
- <1-line reason tied to the archetype's behaviour or emotion>
- <1-line reason tied to the reference brief's implied feel>
- <1-line reason naming what we'd LOSE by picking the most-tempting wrong tone>
```

**Worked example for PM Companion (illustrates the depth — derive fresh for other projects):**

```
My recommendation: Brutally minimal + a Notion-warmth accent.

Why this fits:
- The Anxious Aspirant is a junior professional learning in private — 
  playful/toy-like would feel patronising; luxury would feel pretentious; 
  brutalist would feel hostile.
- 'Sharper, earned not flattered' points toward restraint, not celebration. 
  Brutally minimal lets the *thinking* be the hero, not the UI.
- Pure Linear-style minimalism would feel cold the night before her review. 
  A Notion-warmth accent (cream backgrounds, paper-like texture, one warm 
  muted accent) keeps the seriousness while staying inviting.
```

**SAY:**

"Quick compare — your pick vs my recommendation. Three things can happen:

| | What it means | What to do |
|---|---|---|
| We're aligned | Great — lock it. | Move on. |
| You picked something different and you have a reason | The reason matters. Tell me. | Walk through what your pick gains and what mine gains for the archetype. Pick the stronger one. |
| You picked something different and you're just curious | Either pick is defensible. | Default to my recommendation; we can revisit at iteration. |

What do you want to lock?"

**STOP:** Wait for the learner's final pick.

**ACTION:** Append to `outputs/m1.5-direction-brief.md`:

```
## 1.5 Aesthetic tone

**Primary tone:** <locked tone>
**Secondary accent (if hybrid):** <accent or "none">

**Why this tone:**
- <reason 1 tied to archetype>
- <reason 2 tied to reference brief>
- <reason 3 — what wrong tone we explicitly reject and why>

**What this locks for the build (Module 6):**
- Typography family: <implication — e.g., "serif display + clean sans body" for editorial; "rounded sans throughout" for playful; "monospace + restrained sans" for brutalist>
- Colour register: <implication — e.g., "cream / warm neutrals + one muted accent" for organic; "high contrast + 1 jewel-tone accent" for luxury>
- Spacing density: <implication — e.g., "generous, paragraph-style breathing room" for editorial; "compact, information-rich rows" for industrial>
- Decoration budget: <implication — e.g., "near-zero" for minimal; "intentional layered" for maximalist>
```

**SAY:**

"Locked. This is now the **5th compounding constraint** that flows into Module 6's build agents — alongside scaffold, reference patterns, per-screen spec, and voice rules. Without this lock, build agents drift to AI-default visuals. With it, every visual choice gets pulled toward your committed extreme."

**STOP:** Wait for confirmation.

---

### Step 2.6: Palette + image-gen prompt (mood board)

**SAY:**

"One more direction-setting beat before vectors — and this is where you see your product visually for the first time.

The tone lock told us *which extreme*. The palette tells us *which actual colors*. The image-gen prompt lets you see those colors rendered photorealistically, on a mobile screen, in 10 seconds — before we commit.

Here's the workflow: I'll derive 3 candidate palettes from the locked tone + reference + archetype. For each, I'll write a copy-paste-ready prompt for an image generator — Nano Banana, Midjourney, DALL-E, ChatGPT image, anything. You take any prompt, paste it into your tool, see a real mockup, react. We iterate until one lands.

This is the same loop a designer runs in Figma — done in 4 minutes with AI image gen instead of an hour in design tooling."

**ACTION (runtime — DERIVE all values from prior artifacts, do NOT reuse static examples):**

Read:
- `outputs/m1.1-scope-skeleton.md` — Field 3 (archetype name + behaviour), Field 5 (JTBD), Field 6 (core loop)
- `outputs/m1.3-jtbd-archetypes.md` if present — emotional + social jobs
- `outputs/m1.5-direction-brief.md` — §1 (reference brief), §1.5 (locked tone + implications)

Derive:
- **3 candidate palettes** that fit the locked tone + reference + archetype. Each palette has:
  - Named accent (e.g., "Saffron + ivory", "Lacquer red + brass", "Ink + parchment")
  - 4 hex values: background, surface, primary text, accent
  - One-line "why this fits" rationale
- **3-5 named visual references** for the mood board. Each: brand/product name + one-line "what to borrow" (typography move, color move, layout move, motion move).
- **3 image-gen prompts** — one per palette — following the locked template (see below). Each prompt is self-contained and ~150 words.

Write to `outputs/m1.5-mood-board.md` using this structure:

```
# Mood board — [Product name]

**Locked tone:** [from §1.5]
**Reference brief:** [from §1]
**Generated:** YYYY-MM-DD

---

## Three candidate palettes

| # | Accent name | Background | Surface | Primary text | Accent | Why this fits |
|---|---|---|---|---|---|---|
| 1 | [name] | `#XXXXXX` | `#XXXXXX` | `#XXXXXX` | `#XXXXXX` | [one line] |
| 2 | ... | ... | ... | ... | ... | ... |
| 3 | ... | ... | ... | ... | ... | ... |

## Visual references (3-5)

| Reference | What to borrow |
|---|---|
| [Brand/product] | [Typography / color / layout / motion move — one line] |
| ... | ... |

## Image-gen prompts — paste any into Nano Banana / Midjourney / DALL-E / Imagen / ChatGPT image

### Prompt for Palette 1: [Accent name]

[The generated prompt, ~150 words, plain text — no code fences inside]

### Prompt for Palette 2: [Accent name]

[The generated prompt]

### Prompt for Palette 3: [Accent name]

[The generated prompt]
```

**Image-gen prompt template — apply per palette, deriving all bracketed values:**

```
Photorealistic mobile app home screen mockup, vertical 9:19.5 aspect 
ratio, iOS phone frame.

Aesthetic: [locked tone from §1.5 in prose, with the implications spelled 
out — e.g., "brutally minimal with warm paper-cream undertones, generous 
white space, restrained typography, zero decoration"].

Palette: [bg color name + hex] background, [surface color name + hex] 
for cards, [text color name + hex] primary text, [accent name + hex] 
used sparingly on one CTA only.

Typography: [implied from tone — e.g., "refined serif display for titles, 
clean sans-serif for body" / "monospace throughout" / "rounded geometric 
sans"].

Layout top-to-bottom:
1. Header bar: [app name from m1.1 Field 1, treatment derived from tone]
2. Hero: [the core-loop entry point from m1.1 Field 6 — the action the 
   user takes in the first 3 seconds, with primary button]
3. Secondary strip: [a supporting element — streak, progress, recent 
   item, derived from the loop]
4. Bottom nav: [3 text labels derived from probable screen flow — 
   no icons]

Exclusions: no logos, no brand marks, no purple gradients, no glossy 
effects, no 3D shading, no Inter/Roboto/Arial/Space Grotesk defaults.

Mood: [derived from archetype behaviour + reference brief implied feel — 
one phrase + one contrast — e.g., "quiet, serious, professional — a 
thoughtful work tool, not a consumer app"].
```

**SAY (after writing the file):**

"File written to `outputs/m1.5-mood-board.md`. Open it with `open outputs/m1.5-mood-board.md` (Mac), `start outputs\\m1.5-mood-board.md` (Windows), or your file viewer.

Pick any of the 3 prompts. Paste into your image gen of choice. Wait ~10 seconds. You'll see a photorealistic mobile mockup of your home screen in that palette.

Then come back with reactions. Examples:
- 'Lock palette 2.'
- 'Palette 2 but the accent feels too bright — try 30% darker.'
- 'Hate palette 1. Palette 3 closer but too cold.'
- 'None work — try direction X.'

I'll adjust hex values, regenerate the prompt, swap a palette, or remix until one lands."

**STOP:** Wait for the learner. They test in their image gen, return with reactions.

**Handle feedback:**

| Reaction | Move |
|---|---|
| "Lock palette N" | Proceed to lock action below |
| "Palette N but tweak X" | Adjust hex values in palette N. Regenerate that one prompt. Re-write `mood-board.md` with the adjusted palette. Ask them to re-test. STOP. |
| "Try direction Y instead" | Derive 3 new palettes in direction Y. Re-write `mood-board.md`. STOP. |
| "Combine 1 and 2" | Generate a hybrid palette as a new option. Write a new prompt. Ask them to test the hybrid. STOP. |

**ACTION (once locked):** Append to `outputs/m1.5-direction-brief.md`:

```
## 1.5.5 Mood board + palette

**Locked palette:** [name]

| Token | Hex | Plain-English name |
|---|---|---|
| Background | `#XXXXXX` | [name] |
| Surface | `#XXXXXX` | [name] |
| Primary text | `#XXXXXX` | [name] |
| Accent | `#XXXXXX` | [name] |

**Visual references locked:**
- [reference 1]: [what to borrow]
- [reference 2]: [what to borrow]
- ...

**Image-gen prompt (final — for designer / Lovable re-test):**

[The locked, final prompt — plain text, ~150 words]

**Why this palette won:** [one-line — what locked the choice; e.g., "accent saturation matched the urgency without becoming aggressive"]
```

**SAY:**

"Palette locked. Two things just got unlocked downstream:

1. **Module 6 Step 6.3** no longer infers the visual theme — it reads §1.5.5 directly. Less drift, faster build.
2. **Designer + Lovable handoffs** get the exact hex values + a re-test-ready image-gen prompt. They can re-run the visualization themselves without asking you.

The full mood-board file at `outputs/m1.5-mood-board.md` stays. The designer can open it from their handoff link."

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

"Three dots placed. Naming what we're NOT (cinematic, hand-holding, dramatic) is half the job — each was a wrong default for this archetype.

**Anything you'd shift?** You can slide any dot along its scale, or swap in a different axis if it serves the archetype better."

**STOP:** Wait for the learner. If they propose a shift or swap, walk through the trade-off briefly, let them decide, then update the file before continuing.

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
DOCUMENT-STANDARDS.md. Confirm: (a) the aesthetic tone lock commits to 
a concrete extreme (not 'modern' or 'clean'), (b) §1.5.5 has 4 concrete 
hex values + a locked image-gen prompt, (c) the AI surface map is 
concrete with rubric + failure modes per surface, (d) positioning 
explicitly names competitors and limitations."
```

**Display verdict.** If REVISE: walk through, edit, re-run. If SHIP: proceed.

**SAY (if SHIP):**

"Cleared.

**Four takeaways before we move on:**

1. **The reference brief is the cheapest leverage in the entire workshop.** One sentence prevents the prototype from defaulting to generic SaaS. Use it on every project.
2. **The aesthetic tone lock is the visual commitment AI hates making.** Models default to the comfortable middle on every axis. Committing to one extreme — even a hybrid extreme — is what makes the prototype look designed, not generated.
3. **The image-gen-prompt mood board is the cheapest design-review you'll ever run.** Ten seconds in any image generator gives you a photorealistic mockup. Use it before locking palette on every project — it surfaces visual mistakes that text-only direction briefs hide.
4. **The AI surface map is the move most PM curricula skip and that 2026+ products demand.** Every user-facing AI moment is its own micro-product. Name them; don't merge them.

Ready for /manthan-6 — the build?"

**STOP:** Wait for confirmation.


---

*Built with Manthan by Palash Somani (pAI)*
