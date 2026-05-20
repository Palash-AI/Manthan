# Module 1: Idea + Scope Skeleton

> **Skill it teaches:** Frame the problem before solving.
> **Capability shown:** Sequential write — single agent fills a structured template.
> **Estimated time:** ~5 minutes (live: Palash manages pace. Self-serve: learner takes whatever time they need).
> **Output:** Filled scope skeleton at `outputs/m1.1-scope-skeleton.md`.

---

## Agent context (do not display to learner)

> Read `@.claude/SCRIPT_INSTRUCTIONS.md` first if not already loaded. **No fourth-wall breaking.** Begin with the first SAY block. Do not summarize this file. Do not announce file reads. Do not say "I'll start now."
>
> Delivery mode: this script always runs as self-serve. Claude Code prints SAY blocks to the learner, waits at STOP points, executes ACTION blocks. In live workshops, Palash narrates over the top.
>
> The Field 3 user-first push-back is the teaching moment of this module. Do not skip it. Do not soften it. The principle-auditor gate at Step 5 is also non-negotiable.
>
> Apply `@PRINCIPLES.md` and `@DOCUMENT-STANDARDS.md` silently throughout — never announce them.

---

## Teaching Flow

### Step 1: Open the workshop + module

**SAY:**

"Welcome to Manthan — a workshop by Palash Somani (pAI).

**Manthan = the churning.** In the old story, gods and demons churned the cosmic ocean and out came poison, treasures, and finally the nectar of immortality. Same idea here: we churn a fuzzy product idea — discard the bad, extract what matters, end with something worth building.

**The thesis:** AI made shipping fast. Anyone can vibe-code a prototype in an hour. What separates a high-leverage feature from polished noise is the *thinking* applied before the prompt.

| Item | Detail |
|---|---|
| Modules | Seven |
| Duration | About 60 minutes |
| Output | A v1 PRD + a polished clickable prototype, for one worked example |

**Module 1 has one job:** take a fuzzy idea and produce a scope skeleton that **actually decides things.** Most people skip this — they jump to building. We're doing the opposite.

Ready?"

**STOP:** Wait for "yes" / "ready" / equivalent.

---

### Step 2: Surface the idea

**SAY:**

"Today's worked example: an AI-companion learning platform for early-career product managers. The companion gives them hypothetical product problems, grades the questions they ask while working through the problem, and helps them build PM thinking muscle through repeated practice.

This is fuzzy. That's the point.

Right now we have:

- A user (early-career PM)
- A vague job (get better at PM thinking)
- A method (AI companion + case studies)

We don't have:

- The specific situation that triggers them to use it
- What good looks like
- What we're explicitly NOT building
- The loop that brings them back

Module 1 is where we get specific.

Sound good?"

**STOP:** Wait for "yes" / nod / equivalent.

---

### Step 3: Introduce the scope skeleton

**SAY:**

"The scope skeleton has 10 fields. Each field protects against a specific failure mode.

I'll show you the template, then we'll fill it for the worked example. As we go, watch for which fields feel hard to fill or you haven't thought of yet — those are useful signals."

**ACTION:** Display the scope skeleton template:

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

**SAY:**

"Three things to notice:

**1. Field 4 captures the user's problem in *their words*. Field 5 (JTBD) is *our* analytical framing.** They're related but distinct. We use literal user language in Field 4 because it grounds the whole document.

Quick example so this lands:

| Field | Voice | Example |
|---|---|---|
| Field 4 — User problem | What they'd say into a microphone | *'I'm 6 months into my first PM role and I genuinely don't know if my questions in standup are good. I want to get better at the job I have, not prep for an interview.'* |
| Field 5 — JTBD | What we'd write into a brief | *'When prepping for tomorrow's product review, I want to rehearse one realistic case in 15 minutes, so I show up sharper and don't freeze.'* |

Both matter; they do different jobs.

**2. Field 7 (Value prop / MVP proof) has two sub-lines.** Value is what they get. MVP proof is the behaviour we're testing. Both, not one.

**3. There's no field called *features*.** That comes later. Right now we're framing — not solving.

Ready to fill it together?"

**STOP:** Wait for confirmation.

---

### Step 4: Fill it together

**ACTION:** Use the `Write` tool to create `outputs/m1.1-scope-skeleton.md`. Fill it in real time, narrating each field.

**SAY for each field:**

**Field 1 — Product name.** "Working name only. We can change it later. Let's call this *PM Companion* for now."

**Field 2 — One-line product idea.** "Resist adjectives. Resist 'AI-powered.' One line, plain English."

**STOP — learner attempt:**

"Before I write mine — take a shot. In one plain-English line, how would you describe this product to someone who's never heard of it? Type your version, then I'll show you mine."

**Wait for the learner's attempt.** Acknowledge their version in one line (what's good, what's missing if anything). Then proceed with the worked-example version:

> *Writes:* "An AI companion that gives early-career PMs case studies to think through, grades the questions they ask, and helps them build product-thinking muscle through repeated practice."

**Field 3 — Primary user.**

**STOP — push-back moment:**

"Now let's name a *specific archetype*, not a generic group. 'Early-career PM' is too generic. What would a specific archetype look like? Take a shot."

**Wait for the learner to attempt.**

If their answer is unclear or generic, walk through the triangle:

"Quick distinction — three different things people often confuse:

| | Definition | What it does |
|---|---|---|
| **Demographic** | Facts about who someone *is*. Age, job title, location. | Doesn't predict behaviour. |
| **Persona** | A fictional named character with demographics, a photo, a bio. | Marketing decoration. Rarely changes a design decision. |
| **Archetype** | A *behavioural pattern.* Defines someone by what they DO, not who they ARE. | Different archetypes need different designs. |

We're not building a persona. We're building an archetype. What does this person *do* that distinguishes them from other PMs?"

When they land on a behavioural answer (e.g., "fakes confidence in standups, Googles things at night, learns in private"), accept it.

> *Writes:* "**The Anxious Aspirant** — PM in their first 12 months, just out of consulting or engineering, learns in private to avoid looking unprepared in front of their team or manager."

**Field 4 — User problem (in their own words).**

"This is what they would say if you handed them a microphone. Not your paraphrase — their words."

> *Writes:* "*'I'm 6 months into my first PM role and I genuinely don't know if my questions in standup are good. I read Lenny's Newsletter every morning but it doesn't help me with the actual case in front of me. I want to get better at the job I have, not prep for an interview.'*"

**Field 5 — JTBD.** "Format: 'When [situation], I want [behaviour], so that [outcome].'"

> *Writes:* "When I'm prepping for tomorrow's product review and worried I'll get blindsided by a question, I want to rehearse one realistic case end-to-end in 15 minutes, so I show up with sharper questions and don't freeze."

**STOP — quick absorption pause:**

"Five fields in. Anything in those first five feeling unclear, or are we good to keep going?"

**Wait for the learner.** If they have a question, answer it. Otherwise, continue.

**Field 6 — Core loop.** "The most important field for any retention product. The loop *is* the product."

> *Writes:* "Open companion → get one case → ask questions, get graded → see report card → choose: another case OR a quick PM concept primer → return tomorrow with streak."

**Field 7 — Value prop / MVP proof.** "Two sub-lines. Value is the outcome they get. MVP proof is the behaviour we're testing."

> *Writes:*
> - *Value:* Sharper PM thinking and better questions, in 15 minutes a day, without anyone watching you fumble.
> - *MVP proof:* We are proving that early-career PMs will return daily to a case-study companion that grades the questions they ask, if it makes them feel sharper after 15 minutes.

**Field 8 — Success metric.** "Concrete. Measurable."

> *Writes:* "D2 retention ≥ 35% in the first cohort of 50 testers."

**Field 9 — What we are NOT building.** "Naming non-goals prevents scope creep."

> *Writes:* "NOT building: a video library, a community/feed, certifications, integrations with PM tools, a mobile app (web-only for v1)."

**Field 10 — Top 3 risks.** "What kills v1?"

> *Writes:*
> 1. Question-grading rubric feels arbitrary → users lose trust → churn fast.
> 2. Case-study content quality varies → boring cases → no return.
> 3. Solo learning may need social proof we don't have at v1 → low D2 retention.

**SAY:**

"Skeleton's full.

One first-principles check before the auditor. From first principles — given who this user is and what they need to succeed at this job — is anything missing from this scope skeleton? Anything obvious we haven't named?"

**STOP:** Wait for the learner. If they add or amend, edit the file before continuing.

---

### Step 5: Audit + close the module

**ACTION (silent):** Call the `principle-auditor` sub-agent:

```
Use the Task tool to invoke principle-auditor with prompt:
"Audit outputs/m1.1-scope-skeleton.md against PRINCIPLES.md and 
DOCUMENT-STANDARDS.md. Return verdict."
```

**Display the verdict ONLY if REVISE.** On SHIP, proceed silently to the close SAY below.

If REVISE: surface the revisions, edit the artifact, re-run audit until SHIP.

**SAY (if SHIP):**

"Cleared the gate. The scope skeleton is the spine for the next four modules. Module 2 — research — anchors against what we just wrote.

Here's the full scope skeleton we just built. Take a moment to read it top to bottom."

**ACTION:** Display the full filled `outputs/m1.1-scope-skeleton.md` on screen in consulting-grade format. Use this exact structure — numbered list, bold field names, em-dash separator, sub-fields indented for compound fields 7 and 10:

```
## Scope Skeleton — PM Companion (v0)

*Module 1 output. v0 framing — will sharpen after Modules 2 and 3.*

1. **Product name** — PM Companion (working name)

2. **One-line product idea** — An AI companion that gives early-career PMs case studies to think through, grades the questions they ask, and helps them build product-thinking muscle through repeated practice.

3. **Primary user** — The Anxious Aspirant — PM in their first 12 months, just out of consulting or engineering, learns in private to avoid looking unprepared in front of their team or manager.

4. **User problem (in their own words)** — "I'm 6 months into my first PM role and I genuinely don't know if my questions in standup are good. I read Lenny's Newsletter every morning but it doesn't help me with the actual case in front of me. I want to get better at the job I have, not prep for an interview."

5. **JTBD** — When I'm prepping for tomorrow's product review and worried I'll get blindsided by a question, I want to rehearse one realistic case end-to-end in 15 minutes, so I show up with sharper questions and don't freeze.

6. **Core loop** — Open companion → get one case → ask questions, get graded → see report card → choose: another case OR a quick PM concept primer → return tomorrow with streak.

7. **Value prop / MVP proof**
   - *Value:* Sharper PM thinking and better questions, in 15 minutes a day, without anyone watching you fumble.
   - *MVP proof:* Early-career PMs return daily to a case-study companion that grades the questions they ask, if it makes them feel sharper after 15 minutes.

8. **Success metric** — D2 retention ≥ 35% in the first cohort of 50 testers.

9. **What we are NOT building** — A video library, a community/feed, certifications, integrations with PM tools, a mobile app (web-only for v1).

10. **Top 3 risks**
    - Question-grading rubric feels arbitrary → users lose trust → churn fast.
    - Case-study content quality varies → boring cases → no return.
    - Solo learning may need social proof we don't have at v1 → low D2 retention.
```

If the file on disk isn't already in this exact format, re-write it cleanly using the Write tool so what gets displayed matches what gets saved.

**SAY:**

"Quick wrap.

This skeleton is v0 — not v1. Some fields will sharpen after Module 2 (research) and Module 3 (synthesis). That's the design. We come back with sharper inputs and tighten.

A field that felt hard to fill isn't a sign you missed something. It's a signal of where research helps next.

Ready for /manthan-2?"

**STOP:** Wait for confirmation before the next module.


---

*Built with Manthan by Palash Somani (pAI)*
