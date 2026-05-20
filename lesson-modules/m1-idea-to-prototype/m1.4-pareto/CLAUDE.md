# Module 4: Pareto v1 Lock

> **Skill it teaches:** Cut ruthlessly. Every cut needs a measurable trigger to revisit.
> **Capability shown:** Sequential decision-making with explicit reasoning, anchored to archetypes and metrics.
> **Estimated time:** ~7 minutes (live: Palash manages pace. Self-serve: learner takes whatever time they need).
> **Output:** `outputs/m1.4-pareto-v1-lock.md` — locked v1 spec + priority queue with triggers.

---

## Agent context (do not display to learner)

> Read `@.claude/SCRIPT_INSTRUCTIONS.md` first if not already loaded. **No fourth-wall breaking.** Begin with the first SAY block. Do not summarize this file.
>
> Delivery mode: self-serve. In live mode, Palash narrates over the top.
>
> The teaching moment is **the cut itself.** Most PMs over-justify retention; the discipline is admitting that "feels important" doesn't pass the test. Push back hard if the learner tries to justify too many features into v1.
>
> Apply `@PRINCIPLES.md` and `@DOCUMENT-STANDARDS.md` silently throughout.
>
> **Archetype-name lock:** Use the exact primary-archetype name from Module 1's scope skeleton (`outputs/m1.1-scope-skeleton.md` Field 3). For the worked example that's *"The Anxious Aspirant"*. Do NOT improvise a sharper name based on JTBD wording. Cross-module consistency matters.

---

## Teaching Flow

### Step 1: Open the module

**SAY:**

"Welcome to Module 4.

We have scope, evidence, archetypes. Now we cut.

Many teams try to build too much for v1. The cost is invisible — features that delay launch, dilute focus, or quietly fail because nobody had bandwidth to do them well. So we need a hard test that produces unambiguous yes/no per feature.

Are you ready?"

**STOP:** Wait for "yes" / equivalent.

---

### Step 2: Surface the candidate features — from the User Need Map

**SAY:**

"Now the candidate features. Here's what's different from how most PMs do this:

| Approach | What it produces |
|---|---|
| **Most PM teams** — brainstorm features (*Should we add X? Should we add Y?*) | A feature list. Naturally misses things. |
| **Manthan** — start from the User Need Map. For each user need, ask: *what 1-3 features could serve this need?* | A candidate list that's traceable — every feature has a reason it exists. |

Then we Pareto-cut:

- Features that don't serve any user need → don't even enter the list.
- Features that serve high-priority needs → likely v1.

I'll write the candidate list now — derived from our User Need Map — then we'll look at it together."

**ACTION:** Read `outputs/m1.3.5-user-need-map.md`. For each user need across the 8 dimensions, propose 1-3 candidate features that could serve it. Compile into a single candidate-feature list. Use the `Write` tool to create `outputs/m1.4-pareto-v1-lock.md` containing the FULL list (artifact must be complete — Step 3's scope-editor reads the full file).

**Display in chat: a 5-row PREVIEW + pointer to file** — not the full table. The artifact stays untouched; we just don't dump 25 rows to screen.

```
# Pareto v1 Lock — [Product]

## Candidate features (derived from User Need Map) — preview

| # | Feature | Serves user need(s) from M3.5 |
|---|---|---|
| 1 | [Feature] | Trigger (a) + Doing (b) |
| 2 | [Feature] | Feedback (b) — specificity |
| 3 | [Feature] | Stuck (a) — hint without giving away |
| 4 | [Feature] | Progression (a) |
| 5 | [Feature] | Status (b) |

*(Full list of ~25 candidates in `outputs/m1.4-pareto-v1-lock.md` — Step 3's scope-editor reads them all.)*
```

**Generate the full list (~20-30 candidates) by walking each of the 8 User Need Map dimensions and proposing features.** Each feature line cites which need(s) it serves.

**Worked example (for PM Companion reference — replace with real candidates for other ideas):**

```
1. AI companion that runs case studies — Doing (a)(b)
2. Question-quality grader, multi-dimensional rubric (5 PM thinking dims, 0-3 each) — Feedback (a)(b)(c)
3. Per-question dimension chips (which dim this Q hit) — Feedback (b)
4. Session-level dimension scores (0/3 per dim) — Feedback (c) + Progression (a)
5. Coach's Note panel ("Gap spotted: Clarification — you haven't touched this") — Feedback (c) + Stuck
6. Per-case report card (strengths + gaps) — Feedback (a)(b)
7. Streaks + daily reminders — Progression (b) + Trigger (a)
8. Difficulty levels per case (easy/medium/hard) — Progression (c)
9. "Propose Direction" alt-CTA — Doing (b) — permission to commit a hypothesis
10. Hint ladder (vague → specific → solution) — Stuck (a)
11. Skip-without-penalty option — Stuck (b)
12. Case-was-confusing flag — Stuck (c)
13. Concept primer (60-sec explainer when stuck) — Stuck (a) + Doing (c)
14. Question stem library (templates to reuse) — Transfer (c)
15. Vocabulary cards (PM terms used in cases) — Transfer (b)
16. Weekly growth digest ("Your questions are sharper this week") — Progression (a) + Time-horizon (Week)
17. Anonymous peer benchmark — Status (b)
18. Onboarding (capture archetype, level, goal) — Trigger (b) + Time-horizon (Day 1)
19. Case study library (5+ at launch) — Doing (a)
20. Domain selector (consumer / B2B / etc.) — Time-horizon (Month) — Status (c)
21. Friend leaderboard — Status (negative — most archetypes prefer private)
22. Pro paywall (₹499/mo) — Monetization
23. Mobile-responsive UI — Doing (b) — friction
24. Pause + End-and-Review affordances — Stuck (b)(c)
25. "Best question this week" highlight — Progression (a) + Status (c)
```

**SAY:**

"That's 25 candidate features. Up from the ~15 a pure feature-brainstorm would produce — because needs-first thinking surfaces features you wouldn't otherwise have named.

If we shipped all 25, v1 launches in 8 months and probably misses. We cut to 5-7 by the end of this module."

---

### Step 3: Apply the 5-criteria test

**SAY:**

"A feature is in v1 *only if* it passes at least one of these criteria:

| # | Criterion | Question it asks |
|---|---|---|
| 1 | **Drives the primary success metric** | Without it, do we hit our metric (D2 retention ≥ 35%)? |
| 2 | **Drives D2-D7 retention** | Does it make the user come back? |
| 3 | **Enables monetization** | Does it unlock the paid path? |
| 4 | **Required for thesis to be testable** | Without it, does the experiment fail? |
| 5 | **Has zero workaround** | Can it be faked or done manually for early users? |

For AI products there's an optional 6th — *eval coverage exists*. For v1 I'll flag it but not make it mandatory.

Now: I'll call the `scope-editor` sub-agent to do the scoring. Watch how it argues with the inputs."

**ACTION:** Call the sub-agent:

```
Use the Task tool to invoke scope-editor with prompt:
"Read outputs/m1.1-scope-skeleton.md, outputs/m1.3-jtbd-archetypes.md, 
and outputs/m1.4-pareto-v1-lock.md (the candidate list). Apply the 
5-criteria Pareto test to all 15 features. Output the master decision 
table and the v1 lock + deferred priority queue with measurable triggers."
```

**Display the agent's output in three clearly labeled sections.** Use these exact section headers and tables so the learner can see picked / deferred / killed at a glance:

```
## v1 — Picked

| Feature | Criteria passed | User needs served (M3.5) | Why it's in v1 |
|---|---|---|---|
| AI companion + case-study session | C1, C2, C4 | Doing (a)(b) | Without this there's no product to test |
| Question grader — multi-dim rubric (5 PM thinking dims, 0-3 each) | C1, C2, C4 (eval-gated) | Feedback (a)(b)(c) | The depth IS the moat. Single-score grading = ChatGPT |
| Coach's Note panel — gap-spotting | C2, C4 | Feedback (c) + Stuck | "What am I systematically missing?" answer — the meta-coaching layer |
| Per-case report card (dim strengths + gaps) | C2, C4 | Feedback (a)(b) + Progression (a) | Closes the feedback loop, shows growth shape |
| Streaks + daily reminders | C2 | Progression (b) + Trigger (a) | Single biggest retention lever for habit products |
| Pro paywall (₹499/mo) | C3 | Monetization | Required to test the thesis |

## Deferred — priority queue (with measurable triggers)

| Feature | Cut reason | Needs partially served | Lands in | Trigger to revisit |
|---|---|---|---|---|
| Onboarding (role/level/goal) | Adds friction; v1 defaults to primary archetype | Trigger (b) | v1.1 | If 25%+ users churn before first case |
| Case study library (5+) | Start with 3 cases; watch repeat-rate | Doing (a) | v1.1 | If 60%+ users repeat the same case |
| Concept primer | Workaround: link out to existing articles | Stuck (a) | v1.1 | If 40%+ users hit "I don't get this concept" mid-case |
| Hint ladder | One-paragraph hint covers most cases for v1 | Stuck (a) | v1.1 | If 30%+ users stall at Q3+ |
| Difficulty levels | Single difficulty validates the loop first | Progression (c) | v1.1 | If repeat-rate >50% (cases too easy) |
| "Propose Direction" alt CTA | "Ask" alone validates Q-asking muscle | Doing (b) | v1.1 | If users frequently ask for "tell me your hypothesis" affordance |
| Weekly growth digest | Streak + report card carry Week-1 retention | Progression (a) + Time-horizon | v1.1 | If D7 retention <40% |
| Anonymous peer benchmark | Needs sample size first | Status (b) | v2 | After 500 DAU |
| Question stem library | Build after we know which stems land | Transfer (c) | v2 | After 1k sessions |
| Vocabulary cards | Adjacent to core loop | Transfer (b) | v2 | After core retention is locked |
| Bookmark / save case | Behaviour we haven't validated | (low) | v2 | If 30%+ users ask for it in feedback |
| Domain selector | Personalisation > selection | Time-horizon (Month) | v2 | After 1k DAU |
| Mobile-responsive UI | Only matters if mobile traffic >40% | Doing (b) | v1.1 | If web mobile traffic >40% |
| Mobile native app | Heavy build; web works for now | (none unique) | v2 | After PMF on web |

## Killed — no trigger; don't revisit without new evidence

| Feature | Why killed |
|---|---|
| Friend leaderboard | All four archetypes prefer private learning. Status (a) explicitly says "no one sees her fumble" — leaderboard violates this. |
| Founder Q&A community | Out of scope — we're a behavioural-practice product, not a community product. Conflicting product DNA. |
| Quiz mode | Different mode, different product. Doesn't serve any high-priority need on the User Need Map. |
```

**SAY:**

"Three sections — picked, deferred with measurable triggers, killed. Vague triggers become graveyards; measurable triggers stay alive. And killing a feature with no trigger is a strategic move, not laziness."

**STOP:** Wait for confirmation.

---

### Step 4: Sanity-check — does v1 deliver every archetype's loop?

**ACTION (silent):** Run the archetype walkthrough internally — for each of the 4 archetypes, verify the v1 cut delivers their primary loop. Write the walkthrough table into `outputs/m1.4-pareto-v1-lock.md` (artifact must include it).

**Display in chat ONLY if a gap is found** (any archetype's loop NOT fully delivered by v1). On clean pass, proceed silently to Step 5.

If a gap surfaces, display:

```
## Archetype Walkthrough — gap found

| Archetype | Loop they need | v1 delivers? |
|---|---|---|
| **[Archetype]** | [loop] | ❌ Missing — [what's needed] |
```

Then **SAY:** "v1 doesn't fully serve [archetype]. We either add the missing piece or accept that [archetype] is post-v1. Which?"

**STOP** for the learner's call. Edit the cut accordingly.

---

### Step 5: Run the principles check

**SAY:**

"One first-principles check before the auditor. From first principles — given who this user is and what they need to succeed — does this v1 cut deliver enough to be worth using on Day 1? If we shipped exactly this, would the user feel the product served their primary needs from the User Need Map? Anything we cut that they'd genuinely miss on Day 1?"

**STOP:** Wait for the learner. If they argue a cut feature back into v1, re-test against the 5-criteria and update the file.

**ACTION (silent):** Call `principle-auditor`:

```
Use the Task tool to invoke principle-auditor with prompt:
"Audit outputs/m1.4-pareto-v1-lock.md against PRINCIPLES.md and 
DOCUMENT-STANDARDS.md. Pay special attention to whether cuts have 
measurable triggers and whether v1 stays under 6 features."
```

**Display verdict ONLY if REVISE.** On SHIP, proceed silently to the close SAY below.

**SAY (if SHIP):**

"Cleared.

**Two takeaways before we move on:**

1. **If everything is v1, nothing is v1.** Five features that ship and work beat fifteen features that ship and don't.
2. **Every cut feature needs a *measurable signal* to come back** — not just a future sprint label.

   | Trigger type | Example | Outcome |
   |---|---|---|
   | Future sprint label | "Build it in v1.1" | Just kicking the can |
   | Measurable signal | "Build it when 30% of users hit the missing-concept moment" | Only fires when evidence demands it |

   Without measurable triggers, the priority queue becomes a graveyard.

Ready for /manthan-5 — the direction brief?"

**STOP:** Wait for confirmation.


---

*Built with Manthan by Palash Somani (pAI)*
