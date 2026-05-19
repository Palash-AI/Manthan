# Sample Data — for Module 2 multi-agent research demo

> **What this is:** Two dummy data files used in Module 2 to demonstrate parallel multi-agent research with realistic inputs.
> **Why it exists:** In a real Manthan run, research draws from **three sources** — web (public), company data (internal), and user calls (interviews). For the workshop's worked example (PM Companion), no real proprietary data exists. These files stand in.

---

## Files

| File | Stands in for | Used by which agent |
|---|---|---|
| `company-context.md` | Internal docs a PM lead would have after weeks of thinking — survey data, founder hypothesis, pricing thoughts, competitive notes | `manthan-researcher` (mode: company-context) |
| `user-call-transcripts.md` | 5 verbatim user-interview snippets with early-career PMs | `manthan-researcher` (mode: user-call) |
| Web research | Real searches (Reddit, X, app stores, communities) | `manthan-researcher` (mode: user-voice + competitive-scan + market-context) |

---

## How Module 2 uses these

The researcher sub-agent runs in **three parallel instances**, one per source:

| Instance | Input | Output |
|---|---|---|
| Agent A | `company-context.md` | Themes from internal context — what the team already knows, what the open questions are |
| Agent B | `user-call-transcripts.md` | Verbatim user-voice quotes, clustered into themes |
| Agent C | Real web search | External user voice + competitive scan + market signals |

All three converge into a single research synthesis that Module 3 (`jtbd-synthesizer`) consumes.

This mirrors the CCforPMs course pattern — dummy data files for exercises — and demonstrates a real Claude Code capability (parallel sub-agents) on real-feeling inputs.

---

## Authoring notes

- Files are written to feel like working artifacts, not polished collateral.
- User-call transcripts include verbatim language with hesitations and half-thoughts (like real calls).
- Company-context includes open strategic questions (not all answers locked) — so the research has tension to surface.

---

*Built with Manthan by Palash Somani (pAI)*
