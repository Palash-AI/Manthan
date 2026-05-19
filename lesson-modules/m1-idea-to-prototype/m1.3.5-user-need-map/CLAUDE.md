# Module 3.5: User Need Map

> **Skill it teaches:** Ask the right question — *"What does this user need to succeed at this job?"* — and derive the answer from first principles, before any feature is proposed.
> **Capability shown:** Sequential synthesis grounded in first principles, not feature brainstorming.
> **Estimated time:** ~7 minutes (live: Palash manages pace. Self-serve: learner takes whatever time they need).
> **Output:** `outputs/m1.3.5-user-need-map.md` — 8 journey dimensions × 2-3 needs each = ~16-24 specific user needs. This becomes Module 4's input.

---

## Agent context (do not display to learner)

> Read `@.claude/SCRIPT_INSTRUCTIONS.md` first if not already loaded. **No fourth-wall breaking.** Begin with the first SAY block. Do not summarize this file.
>
> Delivery mode: self-serve. In live mode, Palash narrates over the top.
>
> The teaching moment is the **reframe**: instead of *"what features should we build?"*, Manthan asks *"what does this user need to succeed?"* — and derives the answer from first principles before any feature is proposed. Call this out explicitly.
>
> The output is generic by design — the User Need Map structure (8 dimensions) applies to ANY idea. The needs themselves get derived fresh from the specific archetype's job. Do not hardcode PM-Companion-specific needs into the output for other ideas.
>
> Apply `@PRINCIPLES.md` and `@DOCUMENT-STANDARDS.md` silently throughout.
>
> **Archetype-name lock:** Use the exact primary-archetype name written into Module 1's scope skeleton (`outputs/m1.1-scope-skeleton.md` Field 3). For the worked example that's *"The Anxious Aspirant"*. Do NOT improvise a sharper name (e.g., "Night-Before Rehearser") from the JTBD wording. Consistency across modules matters for audience trust.

---

## Teaching Flow

### Step 1: The reframe — call out the question

**SAY:**

"Welcome to Module 3.5.

This module exists for one reason. Instead of asking *what features should we build?* This module will help us ask: *what does this user need to succeed at this job?*

This will help the LLM pull from prior knowledge of similar products and produce features that serve those needs. Therefore going by first principles, before any feature gets proposed.

Are you ready?"

**STOP:** Wait for "yes" / "ready" / equivalent.

---

### Step 2: Introduce the 8 dimensions

**SAY:**

"Here's the structure. We walk the primary archetype across 8 journey dimensions. At each dimension, we ask: what does this user *need* to succeed?

Not features. Not solutions. Just needs. Features come in Module 4.

**The 8 dimensions — the full arc of using a product:**

| # | Dimension | Question it answers |
|---|---|---|
| 1 | **Trigger** | What gets them in this moment |
| 2 | **Doing** | What they do while in |
| 3 | **Feedback** | Am I improving? |
| 4 | **Stuck** | When I'm blocked |
| 5 | **Progression** | Why come back tomorrow |
| 6 | **Transfer** | Does this translate to real life |
| 7 | **Status** | How I want to be perceived |
| 8 | **Time horizon** | What they need at Day 1 / Week 1 / Month 1 |

This complete list thinks across the PLG for that feature — acquisition, activation, retention, loyalty.

Ready to map the needs?"

**STOP:** Wait for confirmation.

---

### Step 3: Derive the needs — collaborative

**SAY:**

"For our primary archetype, I'll work through each dimension. Two to three specific needs per dimension. We'll do this as a structured walk — you can challenge or add at any point.

I'll write the map as we go."

**ACTION:** Use the `Write` tool to create `outputs/m1.3.5-user-need-map.md`. Read the primary archetype from `outputs/m1.3-jtbd-archetypes.md` and derive needs FROM FIRST PRINCIPLES for THAT archetype and THIS product idea.

**The structure (apply to any idea — fill specific needs based on the archetype's actual job):**

```
# User Need Map — [Primary archetype name]

> Derived from first principles. What does this archetype need to succeed at their job?
> This map drives Module 4's candidate feature list. Every v1 feature must trace to a high-priority need here.

## The 8 dimensions

### 1. Trigger — what gets them in this moment
- [Need 1 — specific to this archetype's situation]
- [Need 2]
- [Need 3 — optional]

### 2. Doing — what they do while in
- [Need 1]
- [Need 2]
- [Need 3]

### 3. Feedback — am I improving?
- [Need 1 — specificity, calibration, peer benchmark, etc.]
- [Need 2]

### 4. Stuck — when I'm blocked
- [Need 1 — hint without giving away, skip-without-penalty, etc.]
- [Need 2]

### 5. Progression — why come back tomorrow
- [Need 1 — visible growth, streak, next-harder, etc.]
- [Need 2]
- [Need 3]

### 6. Transfer — does this translate to real life
- [Need 1 — pattern recognition, vocabulary, reusable templates, etc.]
- [Need 2]

### 7. Status — how I want to be perceived
- [Need 1 — private practice, anonymous benchmark, quiet credential, etc.]
- [Need 2]

### 8. Time horizon — at Day 1, Week 1, Month 1
- Day 1: [what success looks like immediately]
- Week 1: [what sustains them after first session]
- Month 1: [what makes them stay long-term]
```

**Walk through each dimension** in turn. At each one:
- State the dimension question out loud.
- Propose 2-3 specific needs for THIS archetype on THIS product.
- Write them into the map.

**STOP between dimensions 4 and 5** for a mid-walk check:

"Halfway through. Anything we've named that doesn't feel right? Anything missing from these first four dimensions?"

If the learner pushes back, edit before continuing.

**Worked example (for the PM Companion reference idea — replace with real archetype's needs for OTHER ideas):**

> Note for the agent: the table below illustrates the OUTPUT FORMAT only. For any non-PM-Companion idea, derive the needs from the primary archetype's actual job — DO NOT reuse this content.

```
# User Need Map — The Anxious Aspirant

## 1. Trigger
- A reason to open this today vs. scrolling Twitter
- Worth-15-min framing — minimal friction to start
- Anchor to "tomorrow's standup" or "this week's review" — concrete near-term stakes

## 2. Doing
- A realistic case she can engage with (not abstract theory)
- Permission to think slowly — no clock pressure inside the case
- Freedom to ask any question without judgment — including dumb ones

## 3. Feedback
- Honest grading (not flattering or coddling)
- Specificity — WHICH part of her thinking was strong vs weak
- Pattern across questions — am I systematically missing one kind of thinking?

## 4. Stuck
- A hint without giving away the answer
- A way to skip a case without losing streak
- A way to flag a case as confusing for the team

## 5. Progression
- Visible growth signal week-over-week (not just day-streak)
- Streak that earns something (visible to her, not shared)
- Next case feels harder than last — never random difficulty

## 6. Transfer
- Pattern recognition — "I asked this kind of Q in standup, it landed"
- Vocabulary she can carry into real meetings
- Templates / question stems she can reuse without copy-paste

## 7. Status
- Private practice — no one sees her fumble
- Anonymous benchmark — am I in the top 30% of cohort?
- Quiet credential — being "that PM who asks good questions"

## 8. Time horizon
- Day 1: Feel sharper after one 15-min case
- Week 1: See the streak. Notice she's framing questions differently.
- Month 1: Realise her real-meeting questions have changed.
```

**SAY (after all 8 dimensions are filled):**

"Map's complete. About 16-20 specific user needs. Notice what we did NOT do — we did not name a single feature. Feature comes next.

Now in Module 4, when we generate candidate features, every feature has to trace back to one or more of these needs. That's the discipline — needs first, features second."

**STOP:** Wait for confirmation.

---

### Step 4: First-principles closing check

**SAY:**

"One quick check before we move on. From first principles — given who this user is and what they need to succeed — is anything missing from this map?

I'll name three places needs often hide:

- **Failure mode needs.** What does she need when the AI gets the grade wrong? When the case isn't relevant? When the streak breaks?
- **Edge-of-product needs.** What does she need *just before* opening the app? *Right after* closing it? Those moments matter for retention.
- **Social-context needs.** Even if she's a private learner, how does she want this to land if a colleague sees her using it? What story does it tell about her?

Anything to add?"

**STOP:** Wait for the learner. If they add 1-3 needs, edit the map.

---

### Step 5: Run the principles check + close

**SAY:**

"Auditor before we move on. Same protocol as every module — `principle-auditor` reads our map and grades it against `PRINCIPLES.md` and `DOCUMENT-STANDARDS.md`. SHIP or REVISE."

**ACTION:** Call `principle-auditor`:

```
Use the Task tool to invoke principle-auditor with prompt:
"Audit outputs/m1.3.5-user-need-map.md against PRINCIPLES.md and 
DOCUMENT-STANDARDS.md. Pay special attention to specificity — 
needs should be archetype-specific and behaviour-specific, not 
generic. A need like 'practice' is too vague; 'a way to rehearse 
one realistic case before tomorrow's standup' is the right level."
```

**Display verdict.** If REVISE, walk through revisions, edit, re-run.

**SAY (if SHIP):**

"Cleared. The User Need Map is now the input to Module 4. Every candidate feature there has to serve one or more of these needs. Features that don't serve any need get cut — that's the new Pareto.

**Two takeaways before we move on:**

1. **Needs first, features second.** The order matters.

   | If you generate... | The result is... |
   |---|---|
   | Features before needs | You'll miss what users actually need |
   | Needs first | Your feature list will be richer and more grounded every time |

2. **The important question is *"What does this user need to succeed?"*** Manthan helps us ask it across 8 dimensions, archetype by archetype, before any feature gets proposed.

Ready for /manthan-4?"

**STOP:** Wait for confirmation before the next module.

---

*Built with Manthan by Palash Somani (pAI)*
