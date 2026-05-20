# Module 2: Research Blitz (Parallel Multi-Agent)

> **Skill it teaches:** Get evidence before locking. Borrow user language; don't invent it.
> **Capability shown:** **Parallel sub-agents.** Three independent research streams run simultaneously and converge.
> **Estimated time:** ~8 minutes when web research is pre-cached (workshop default). ~11 minutes when live web search runs (take-home / self-serve default).
> **Output:** Research synthesis at `outputs/m1.2-research-synthesis.md`.

---

## Agent context (do not display to learner)

> Read `@.claude/SCRIPT_INSTRUCTIONS.md` first if not already loaded. **No fourth-wall breaking.** Begin with the first SAY block. Do not summarize this file. Do not announce file reads.
>
> Delivery mode: self-serve. In live workshops, Palash narrates over the top while the parallel agents run on screen.
>
> The teaching moment of this module is **showing parallel agents in action.** When Step 3 spawns three agents in one message, the learner sees three streams of work happen at once — not sequentially. Make it visible.
>
> Apply `@PRINCIPLES.md` and `@DOCUMENT-STANDARDS.md` silently throughout.

---

## Teaching Flow

### Step 1: Open the module

**SAY:**

"Welcome to Module 2.

We have a scope skeleton from Module 1. It captures *our* thinking about the user. Module 2 replaces our thinking with *evidence*.

Here's the principle: you do not lock scope on intuition. You lock it on what users actually said, what competitors actually do, and what the market actually shows.

Are you ready?"

**STOP:** Wait for "yes" / equivalent.

---

### Step 2: Spawn three parallel agents

**SAY:**

"Now the capability that earns this module its time: **parallel sub-agents.**

Good research draws from three sources, run in parallel:

1. **Web research** — public user voice (Reddit, X, app reviews), competitive scans, market signals.
2. **Company data** — what your team already knows. Internal surveys, founder hypotheses, sales notes.
3. **User calls** — verbatim transcripts from real conversations.

For today's time budget, web research is pre-cached from yesterday's actual searches — the parallel-spawn capability is what we're showing.

| When work is... | You should... |
|---|---|
| Breakable into independent streams | Run them in **parallel** |
| Dependent — each step needs the prior | **Sequence** them |

Research is the cleanest parallel example — three sources, three streams, no interdependence.

Watch this. I'm spawning three `manthan-researcher` agents in a single message. They'll run simultaneously."

**ACTION:** In a SINGLE message, spawn three Task tool calls in parallel:

```
Task 1 — manthan-researcher (mode: user-voice, PRE-BAKED)
Prompt: "Read reference/sample-data/web-research-prebaked.md. This 
file is the pre-cached output of a live web-research run on the 
product idea: 'An AI companion that gives early-career PMs case 
studies to think through, grades their questions, and helps them 
build product-thinking muscle.'

Return the file's contents — themes, verbatim quotes, anti-patterns, 
competitive gap map — as your Stream A output. Do NOT do additional 
live searching; the cache contains the actual web findings from 
2026-05-11.

Note in your output: 'Stream A served from pre-cached web research 
(2026-05-11 searches). 7 queries logged.'"

Task 2 — manthan-researcher (mode: company-context)
Prompt: "Read reference/sample-data/company-context.md. Extract: 
(a) what the team already knows, (b) the open strategic 
questions, (c) the team's risk hypotheses. Output a structured 
synthesis."

Task 3 — manthan-researcher (mode: user-call)
Prompt: "Read reference/sample-data/user-call-transcripts.md. 
Extract verbatim user-voice quotes from all 5 calls. Cluster 
into 3-5 themes. For each theme, list 2-3 verbatim quotes with 
the speaker name. No paraphrasing."
```

While agents run, **SAY:**

"While they work — notice what just happened. One message, three jobs, three workers. The capability is the parallel spawn. In a real run with live web search, you'd see this finish in 2-3 minutes total instead of 8-10 sequential."

---

### Step 3: Display all three outputs (compact)

**ACTION:** When all three agents return, display a **compact summary** of each — not the full output. For each stream, show: top 3–5 findings as bullets + 1 verbatim quote (where applicable). Full outputs remain in agent memory and feed Step 4's synthesis untouched.

```
=== Stream A: Web (User Voice Extractor) ===
- [Finding 1]
- [Finding 2]
- [Finding 3]
Verbatim: "[quote]"

=== Stream B: Company Context ===
- [Finding 1]
- [Finding 2]
- [Finding 3]

=== Stream C: User Call Transcripts ===
- [Finding 1]
- [Finding 2]
- [Finding 3]
Verbatim: "[quote]"
```

**SAY:**

"Three streams, three angles. Web = what users say publicly. Company = what your team already believes. User calls = what users said when nobody else was listening.

The insight is at the **intersection** — agreement = signal, disagreement = question to investigate.

The synthesis next is where this turns into something you can act on. Ready?"

**STOP:** Wait for confirmation.

---

### Step 4: Synthesise the three streams

**ACTION:** Use the `Write` tool to create `outputs/m1.2-research-synthesis.md`. Structure:

```
# Research Synthesis — PM Companion

## Convergent themes (where 2+ streams agree)
1. [Theme] — Evidence from: [streams]. Verbatim: [quote].
2. ...

## Divergent signals (where streams disagree)
1. [Question] — Web says X; user calls say Y. Worth investigating.
2. ...

## Verbatim user language to remember
- [Direct quote 1]
- [Direct quote 2]
- ...
(For Module 4 — Field 4 of scope skeleton uses these.)

## Open questions for the team
- [Question 1]
- [Question 2]

## Anti-patterns to avoid (from competitive scan)
- [Pattern 1] — competitor doing this; users complain; we don't.
- ...
```

**SAY (as you fill it):**

"Notice how the synthesis structure does the thinking:

| Section | Where it feeds in next |
|---|---|
| Convergent themes (evidence stacks up) | Becomes archetypes in Module 3 |
| Divergent signals (open questions) | Becomes triggers in Module 4's priority queue |
| Verbatim language | Goes back into the scope skeleton's User Problem field |
"

---

### Step 5: Run the principles check

**SAY:**

"One first-principles check before the auditor. From first principles — given who this user is and what they need to succeed — is anything missing from this synthesis? Any signal we'd expect to see that's not there? Any divergent question we should have flagged?"

**STOP:** Wait for the learner. If they add or amend, edit the file.

**ACTION (silent):** Call the `principle-auditor`:

```
Use the Task tool to invoke principle-auditor with prompt:
"Audit outputs/m1.2-research-synthesis.md against PRINCIPLES.md 
and DOCUMENT-STANDARDS.md. Return verdict."
```

**Display verdict ONLY if REVISE.** On SHIP, proceed silently to Step 6.

---

### Step 6: Close the module

**SAY:**

"Parallel sub-agents — the highest-leverage Claude Code move for any research-heavy work: deal review, market sizing, competitive teardown, pre-meeting briefing. Anywhere work decomposes into independent streams, parallelise.

Ready for /manthan-3?"

**STOP:** Wait for confirmation.


---

*Built with Manthan by Palash Somani (pAI)*
