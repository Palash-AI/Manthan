# Manthan Playbook

> The same workshop you ran with Palash, packaged for solo use on your own ideas.
> *Built with Manthan by Palash Somani (pAI).*

---

## What this is

The workshop you attended used a shared example (PM Companion). This playbook is the **same seven-step sequence**, the same gates, the same sub-agents — applied to *your* idea instead of the shared one.

Two ways to use it:

| Mode | When to use | How |
|---|---|---|
| **Interactive** (recommended) | When you're ready to build. You sit with Claude Code, run `/manthan-1` through `/manthan-6` on your own idea. | Fork the repo. Replace the worked example with your idea in Module 1. The sub-agents and gates work the same. |
| **Reference** | When you're thinking, not building. Reading on a phone, in a meeting, on a flight. | Read this playbook end-to-end. The method is here in prose; the tools live in the repo. |

---

## The Manthan story

Samudra Manthan — the cosmic ocean, churned by gods and demons using Mount Mandara as the rod and Vasuki the serpent as the rope. Out came poison (discarded), fourteen ratnas (treasures), and finally Amrit (the nectar of immortality).

This skill maps that arc onto product building:

| Myth | Skill |
|---|---|
| Cosmic ocean | The fuzzy idea space |
| Mount Mandara (the rod) | The structured method |
| Vasuki (the rope) | The discipline of pulling against your own assumptions |
| Halahal (the poison) | The bad ideas you must discard |
| 14 Ratnas | The artifacts produced |
| Amrit | The high-confidence working prototype |

The structured churning extracts the essential. That is the skill.

---

## The non-negotiables

Read these once. They gate every artifact you produce.

| File | What it does |
|---|---|
| [`PRINCIPLES.md`](../PRINCIPLES.md) | Two checks (user-first, why-here-why-now) and the feedback protocol |
| [`DOCUMENT-STANDARDS.md`](../DOCUMENT-STANDARDS.md) | Consulting-grade rules. No fluff. Skim test. 30-second test. |
| [`GLOSSARY.md`](../GLOSSARY.md) | 15 product-thinking terms with Swiggy examples |

---

## The seven-step sequence

| # | Step | Skill | Capability shown |
|---|---|---|---|
| 1 | Idea + scope skeleton (10 fields) | Frame the problem before solving | Sequential write |
| 2 | Research blitz (3 parallel sources) | Get evidence before locking | Parallel sub-agents |
| 3 | Themes → JTBD grid → 4 archetypes | Translate research into user models | Sequential synthesis |
| **3.5** | **User Need Map (8 dimensions)** | **Ask the same question one-shot does — *what does this user need to succeed?* — with discipline** | **First-principles need derivation** |
| 4 | Pareto v1 lock | Cut ruthlessly, traceable to needs | Sequential decision |
| 5 | Direction brief | Pin the feel + AI architecture (with rubric depth) | Sequential, structured choice |
| 6 | Build prototype (polished, with iteration pass) | Working clickable HTML at home.html quality | Sequential build, parallel for screens |

---

## Step 1 — Idea + Scope Skeleton

**Goal:** Convert a fuzzy idea into a structured scope that decides things.

**Output:** A filled scope skeleton — 10 fields.

```
1. Product name
2. One-line product idea
3. Primary user (specific archetype)
4. User problem (in their own words)
5. JTBD (situation + emotion + outcome)
6. Core loop (the action that brings them back)
7. Value prop / MVP proof
   - Value: what value does this deliver?
   - MVP proof: what behaviour are we proving?
8. Success metric
9. What we are NOT building
10. Top 3 risks
```

**Questions to ask yourself at this gate:**

- Is my Field 3 a *behavioural* archetype, or a demographic group?
- Does Field 4 use the user's words, or my paraphrase?
- Does Field 5 have all three: situation + emotion + outcome?
- Is Field 9 specific (named non-goals), or vague?

**Common failure:** writing "early-career PMs" in Field 3. Push to behaviour: what does this person *do*?

---

## Step 2 — Research Blitz (parallel)

**Goal:** Replace your intuition with evidence from three sources, in parallel.

**Output:** A research synthesis with convergent themes, divergent signals, verbatim language, and open questions.

**Three sources:**
1. **Web** — Reddit, X, app reviews, communities. Run `manthan-researcher` in `user-voice` and `competitive-scan` modes.
2. **Company data** — internal surveys, founder hypotheses, sales notes. Feed into `manthan-researcher` (`company-context` mode).
3. **User calls** — verbatim transcripts. Feed into `manthan-researcher` (`user-call` mode).

**The capability:** Spawn all three in a single message. They run simultaneously. You converge their outputs.

**Questions to ask yourself at this gate:**

- Where do 2+ sources agree? Those are your themes.
- Where do they disagree? Those are open questions.
- Did I pull verbatim quotes, or paraphrase?

**Common failure:** doing one source well and skipping the others. The whole point is the parallel triangulation.

---

## Step 3 — Themes → JTBD → 4 Archetypes

**Goal:** Convert evidence into user models that drive design decisions.

**Output:** Actionable themes, JTBD grid (3×3), and 4 behavioural archetypes.

**The actionable-theme test:** finish the sentence — *"Because users feel/do/want X, we should design for Y."* If you can't finish it, the theme is observation, not insight.

**The JTBD grid:**

|   | Functional job | Emotional job | Social job |
|---|---|---|---|
| Before (trigger) | | | |
| During (use) | | | |
| After (outcome) | | | |

The hidden retention lives in emotional and social columns. Most PMs fill only the functional column.

**The archetypes:**

For each (4 max), produce: name, behaviours (3-4 specific), primary JTBD sentence, emotional driver, anti-archetype, evidence quotes.

**Questions to ask yourself at this gate:**

- Are my archetypes distinct enough that a designer would make different decisions for them?
- Does each one have verbatim research evidence?
- Did I avoid the "demographic decoration" trap?

**Common failure:** producing personas dressed up as archetypes. Personas are who someone *is*. Archetypes are who they *become when using your product.*

---

## Step 4 — Pareto v1 Lock

**Goal:** Cut a candidate feature list (typically 10-15) to a v1 lock (typically 3-6) using a hard test.

**Output:** A v1 lock + a deferred priority queue with measurable triggers.

**The 5-criteria test.** A feature is in v1 *only if* it passes at least one of:

1. Drives the primary success metric
2. Drives D2-D7 retention
3. Enables monetization
4. Required for the thesis to be testable
5. Has zero workaround (can't be faked or done manually)

For AI products, an optional 6th: **eval coverage exists.**

**The priority queue.** Every cut feature must have a *measurable trigger* to revisit. Vague triggers ("nice to have", "maybe later") become graveyards. Measurable triggers ("if D2 retention <40%", "if 30% of users ask for it") fire when they should.

**Questions to ask yourself at this gate:**

- If everything is v1, did I really cut?
- Does each cut have a *measurable* trigger, or a vibes-trigger?
- Does v1 deliver the loop for *all* my archetypes, with the same features?

**Common failure:** over-justifying retention. If a feature feels like it passes 4-5 criteria, you're rationalising. Re-test.

---

## Step 5 — Direction Brief

**Goal:** Pin the directional feel + AI architecture in a short brief, before any code runs.

**Output:** Five micro-fields:

1. **Reference brief** — *"Feels like [product]'s [property], for [archetype] doing [job]."*
2. **3 design vectors** — pick from Mood, Guidance, Copy (the three that express in plain HTML).
3. **Primary emotion** — one line. What should the user feel in the core moment?
4. **AI surface map** — every place an AI does work, named as its own micro-product.
5. **Positioning** — *"For [archetype], [product] is a [category] that [unique value], unlike [alternative] who [limitation]."*

**The AI surface map** is the move most PM curricula skip. For 2026+ products, it's the highest-leverage skill they don't yet have. Each surface gets its own prompt, quality bar, and failure modes.

**Questions to ask yourself at this gate:**

- Does my reference brief beat "generic SaaS" as Claude Code's default?
- Does my AI surface map name 3-5 distinct surfaces, or one mega-surface?
- Does my positioning explicitly name competitors and their limitations?

**Common failure:** vague positioning ("the best learning app for PMs") that doesn't decide anything. Specific positioning enables future cuts.

---

## Step 6 — Build Prototype

**Goal:** Translate locked thinking into a single-file HTML prototype.

**Output:** `index.html` — light mode, one accent, mock data, clickable. 4 screens or fewer.

**The build sequence:**

1. **Sequentially** — write the shell (HTML scaffold, design tokens from the direction brief, navigation logic).
2. **In parallel** — spawn one sub-agent per screen, in a single message. They author screen-specific HTML simultaneously, you merge.

**The 5-lens review.** After the build, apply each lens; name a strength and a weakness for each:

| Lens | Question |
|---|---|
| Product | Does it serve the JTBD? |
| Emotion | Does the user feel what we intended? |
| UX | Is the next action obvious? |
| Visual | Does it feel coherent and on-brief? |
| System | Could a v1 build be built from this? |

Weaknesses become the v1.1 priority queue. Strengths become the things v2 doesn't break.

**Questions to ask yourself at this gate:**

- Did I anchor every visual choice to the direction brief?
- Did I parallelise screens once the shell was locked?
- Did I run the 5-lens review *honestly*?

**Common failure:** treating the prototype as the deliverable. It's a thinking tool. The artifact set together is the deliverable.

---

## The artifact set as your v1 PRD

When all seven modules are done, you have:

- Scope skeleton
- Research synthesis
- JTBD grid + 4 archetypes
- Pareto v1 lock + priority queue
- Direction brief
- Working clickable prototype

**This is your v1 PRD.** Don't write a separate Word document. The structured artifacts together speak. An engineer can build from them. A designer can polish from them. A founder can fundraise from them.

---

## How to use this on your own idea

1. **Fork the workshop repo:**
   ```bash
   git clone [REPO-URL] my-idea
   cd my-idea
   ```
2. **Empty the worked-example outputs:**
   ```bash
   rm -rf outputs/*
   ```
3. **Launch Claude Code:**
   ```bash
   claude
   ```
4. **Run `/manthan-1`** with your own idea instead of PM Companion. The sub-agents, gates, and audit work identically.
5. **Replace the dummy data files** at `reference/sample-data/` with your real data: company context, user calls, etc. (Optional but recommended.)

The workshop's worked example takes 60 minutes. Your own idea will take longer the first time — probably 3-4 hours — because you'll think harder at each gate. That's the point.

---

## Three things to remember

1. **AI made shipping fast. Clarity is what wins.** The prototype isn't the moat. The thinking that produced it is.
2. **Parallel when scope is clear, sequential when it isn't.** This is the single most important Claude Code rule.
3. **The artifacts together are the PRD.** Don't write a separate Word doc. Let the structured outputs speak.

---

*Built with Manthan by Palash Somani (pAI).*

*Manthan: the structured churning that extracts the essential.*
