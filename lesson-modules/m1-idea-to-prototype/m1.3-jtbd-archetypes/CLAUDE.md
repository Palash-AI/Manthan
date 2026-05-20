# Module 3: Themes → JTBD Grid → 4 Archetypes

> **Skill it teaches:** Translate research into user models that drive design decisions.
> **Capability shown:** Sequential synthesis with project memory — the synthesizer reads research, scope, and prior outputs together.
> **Estimated time:** ~8 minutes (live: Palash manages pace. Self-serve: learner takes whatever time they need).
> **Output:** `outputs/m1.3-jtbd-archetypes.md` containing actionable themes, JTBD grid, and 4 archetypes.

---

## Agent context (do not display to learner)

> Read `@.claude/SCRIPT_INSTRUCTIONS.md` first if not already loaded. **No fourth-wall breaking.** Begin with the first SAY block. Do not summarize this file.
>
> Delivery mode: self-serve. In live mode, Palash narrates over the top.
>
> The teaching moment is **archetypes vs. personas.** Personas are demographic decoration; archetypes are decision tools. Make this distinction visible.
>
> Apply `@PRINCIPLES.md` and `@DOCUMENT-STANDARDS.md` silently throughout.
>
> **Archetype-name lock:** When the worked example is PM Companion, the primary archetype is *"The Anxious Aspirant"* (locked in Module 1's scope skeleton). Use this exact name throughout — do NOT improvise a sharper name (e.g., "Night-Before Rehearser") based on the JTBD. Consistency across modules matters for audience trust. If the user explicitly chooses a different name in Module 1, propagate that choice — never re-name silently.

---

## Teaching Flow

### Step 1: Open the module

**SAY:**

"Welcome to Module 3.

We have evidence from Module 2 (web, company, user calls — synthesised into themes, divergent signals, verbatim language). Module 3 turns that evidence into something a designer can build for:

- Actionable themes
- A JTBD grid
- Four behavioural archetypes

**Before we start, one important distinction:**

| | Persona | Archetype |
|---|---|---|
| Defines someone by | Who they *are* (name, age, job title, photo) | Who they *become when using your product* (behaviour) |
| Used for | Marketing slide decks | Design decisions |
| Why it matters | Not highly relevant for design — choices hardly change based on whether a user is 28 or 32 | We're building these |

Are you ready?"

**STOP:** Wait for "yes" / equivalent.

---

### Step 2: Surface actionable themes (explicit step)

**SAY:**

"Step one: themes.

The research synthesis from Module 2 gave us convergent themes — places where 2+ streams agree. We need to turn those into *actionable* themes — themes that imply a product move.

A theme is actionable if you can finish this sentence with it:

> *'Because users feel/do/want X, we should design for Y.'*

If you can't finish the sentence, the theme is still observation, not insight.

Here's how this step works: I'll generate the themes from our research synthesis. You watch them appear and challenge any that don't pass the *because/we should* test. If a theme feels weak or missing, call it out and we'll adjust before moving on."

**ACTION:** Use the `Write` tool to create `outputs/m1.3-jtbd-archetypes.md` with the section:

```
# Themes / JTBD Grid / Archetypes — PM Companion

## Actionable themes

| # | Theme | Evidence | Implies |
|---|---|---|---|
| 1 | [Theme] | [streams + verbatim] | [design move] |
| 2 | ... | | |
```

Pull from the synthesis at `outputs/m1.2-research-synthesis.md`. Aim for 4-6 themes.

Example themes (worked example):

| # | Theme | Evidence | Implies |
|---|---|---|---|
| 1 | Generic content fails them at the moment of need | Calls 1, 4, 5; Web (Reddit) | Product must be situational, not curricular |
| 2 | They want a feedback signal on their own thinking | Calls 1, 4 | Grading is core, not optional |
| 3 | Daily, short, habit-shaped beats course-shaped | Calls 5, 3; Company survey | 15-min sessions, daily streak, no certifications |
| 4 | ChatGPT is a competitor — and a weak one | Calls 1, 4 | Differentiate on calibrated grading + structure |
| 5 | Solo learning is the preference, not a constraint | Calls 1, 2, 3 | No community layer needed for v1 |

**SAY:**

"Six themes, each one points to a product move. This is now the foundation for the archetypes.

Anything in this list that feels weak or wrong? Anything missing? Now's the time to flag it before we move on."

**STOP:** Wait for feedback. If the learner flags a theme as weak or proposes a missing one, edit the file before continuing. If they're satisfied, proceed.

**SAY:**

"Ready for the JTBD grid?"

**STOP:** Wait for confirmation.

---

### Step 3: Build the JTBD grid

**SAY:**

"Step two: the JTBD grid.

A JTBD has three stages — before (the trigger), during (the use), after (the outcome) — and three dimensions — functional, emotional, social.

Most PMs only think about the *functional* job. The hidden ones — emotional and social — are usually where retention lives."

**ACTION:** Append to the output file:

```
## JTBD Grid

|   | Functional job | Emotional job | Social job |
|---|---|---|---|
| Before (trigger) | ... | ... | ... |
| During (use) | ... | ... | ... |
| After (outcome) | ... | ... | ... |
```

Worked example:

|   | Functional job | Emotional job | Social job |
|---|---|---|---|
| **Before (trigger)** | "I have a meeting tomorrow and want to think clearer." | "I'm anxious about looking unprepared." | "I don't want to ask my manager dumb questions." |
| **During (use)** | "Practise asking questions and get feedback." | "Feel sharper, less faking it." | "Private practice — nobody's watching me fumble." |
| **After (outcome)** | "Show up to the meeting with better questions." | "Confidence that's earned, not faked." | "Look like the PM I want to be." |

**SAY:**

"Notice the social job is *not* about community or social features. It's about how the user wants to be *perceived*. That's a different lens. Most PMs miss this.

Ready for the archetypes?"

**STOP:** Wait for confirmation.

---

### Step 4: Generate 4 archetypes (call the synthesizer)

**SAY:**

"Step three: archetypes. Up to 4. Each grounded in research. Each distinct enough that a designer would make different decisions for them.

I'll call the `jtbd-synthesizer` sub-agent — it specialises in this."

**ACTION:** Call the sub-agent:

```
Use the Task tool to invoke jtbd-synthesizer with prompt:
"Read outputs/m1.1-scope-skeleton.md, outputs/m1.2-research-synthesis.md, 
and outputs/m1.3-jtbd-archetypes.md (the themes + JTBD grid sections). 
Generate 4 behavioural archetypes for PM Companion. Each archetype must 
have: name, behavioural pattern (3-4 specific behaviours), primary JTBD 
sentence, emotional driver, anti-archetype (who this person is NOT), and 
2 verbatim quotes from the research as evidence."
```

**Append all 4 archetypes (full detail) to `outputs/m1.3-jtbd-archetypes.md`.**

**Display in chat:** show the 3 most differentiating archetypes in full. For the 4th, show only name + one-line primary JTBD + a pointer that the full entry is in the file. This compresses live walk-through without reducing the artifact. The downstream Pareto and Direction Brief still consume all 4 from the file.

Example compressed display:

```
### Archetype 1: [name]  — full detail
### Archetype 2: [name]  — full detail
### Archetype 3: [name]  — full detail

### Archetype 4: [name]
Primary JTBD: "[one-line JTBD]"
*(Full archetype in outputs/m1.3-jtbd-archetypes.md.)*
```

Worked-example archetypes (what should land):

```
## Four Archetypes

### Archetype 1: The Anxious Aspirant
- Behaviours: Reads Lenny religiously; Googles questions at night; 
  doesn't ask in standup; bookmarks ChatGPT chats for weekends.
- Primary JTBD: "When prepping for tomorrow's product review, I want 
  to rehearse one realistic case in 15 min, so I don't freeze."
- Emotional driver: Imposter syndrome; private learner.
- Anti-archetype: Not the PM who asks dumb questions confidently. 
  This person learns in shadow.
- Evidence: Riya (Call 1), Karan (Call 4).

### Archetype 2: The Ex-Engineer in Crisis
- Behaviours: Came from engineering; great at answering, weak at asking; 
  gets blindsided in user interviews; wants reps not theory.
- Primary JTBD: "When I'm about to do a user interview, I want to 
  practise the questioning muscle, so I don't miss the insight."
- Emotional driver: Identity shift anxiety — "what have I done."
- Anti-archetype: Not the natural-talker PM. This person needs reps.
- Evidence: Dev (Call 2).

### Archetype 3: The Self-Improver
- Behaviours: Has a job already; rejects course-shaped learning; wants 
  habit-shaped daily practice; pays for tools that compress feedback loops.
- Primary JTBD: "When I have 15 minutes, I want to do one practice 
  rep, so I'm sharper next week than this week."
- Emotional driver: Compound improvement; allergic to wasted time.
- Anti-archetype: Not the certification-collector. This person is 
  optimising for skill, not credentials.
- Evidence: Aakash (Call 5), Shreya (Call 3).

### Archetype 4: The Burned-Out Reader
- Behaviours: Subscribed to 5 PM newsletters; reads them all; nothing 
  changes in their behaviour; tired of inspiration porn.
- Primary JTBD: "When I notice I've consumed 50 PM articles and 
  improved nothing, I want a behavioural product, so consumption 
  becomes practice."
- Emotional driver: Frustration with passive learning.
- Anti-archetype: Not the casual reader. This person wants change.
- Evidence: Aakash (Call 5).
```

**SAY:**

"Four archetypes, each from research, each distinct. A designer can now make different decisions for the Anxious Aspirant vs the Ex-Engineer.

In Module 4 we'll Pareto-cut features against these archetypes — 'does this feature serve archetype 1? archetype 2?' The cuts get sharper because the archetypes are sharper."

**STOP:** Wait for confirmation.

---

### Step 5: Run the principles check

**SAY:**

"One first-principles check before the auditor. From first principles — given the research we've seen — is there an archetype missing from this set? An anti-archetype we should explicitly NOT design for? Anything in the JTBD grid where we filled functional but left emotional or social thin?"

**STOP:** Wait for the learner. If they add or amend, edit the file.

**ACTION (silent):** Call `principle-auditor`:

```
Use the Task tool to invoke principle-auditor with prompt:
"Audit outputs/m1.3-jtbd-archetypes.md against PRINCIPLES.md and 
DOCUMENT-STANDARDS.md. Return verdict."
```

**Display verdict ONLY if REVISE.** On SHIP, proceed silently to the close SAY below.

**SAY (if SHIP):**

"Cleared.

**Two takeaways before we move on:**

1. **Archetypes outperform personas** because they're built on *behaviours*, not demographics. A behaviour can be designed for. A demographic can't.
2. **The JTBD grid forces you to look at emotional and social jobs, not just functional.** The hidden retention lives in the emotional and social columns. Most people miss them.

Ready for /manthan-4 — the Pareto cut?"

**STOP:** Wait for confirmation.


---

*Built with Manthan by Palash Somani (pAI)*
