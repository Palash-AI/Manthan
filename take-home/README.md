# Manthan — Take-Home

> The skill, packaged for self-service on your own ideas after the workshop.
> *Built with Manthan by Palash Somani (pAI).*

---

## Two ways to use the take-home

| Path | When | How |
|---|---|---|
| **Interactive** | When you sit down to actually build | Fork the workshop repo, replace the worked example with your idea, run `/manthan-1` through `/manthan-6` |
| **Reference** | When you're thinking, not building (phone, meeting, flight) | Read [`PLAYBOOK.md`](./PLAYBOOK.md) — the full method in prose |

---

## Interactive path — quick start

```bash
# 1. Fork the workshop repo
git clone [REPO-URL] my-idea
cd my-idea

# 2. Empty the worked-example outputs
rm -rf outputs/*

# 3. Launch Claude Code
claude

# 4. Run Module 1 with your own idea
/manthan-1
```

The sub-agents, gates, and audit pipeline work identically. The only thing that changes is the input — your idea instead of PM Companion.

**Optional but recommended:** replace the dummy data at `reference/sample-data/` with your own:
- Replace `company-context.md` with your team's real context (founder hypothesis, surveys, pricing thoughts).
- Replace `user-call-transcripts.md` with verbatim transcripts from your real user interviews.
- These will dramatically improve Module 2's research output.

---

## What the take-home preserves

| From the workshop | In the take-home | Why |
|---|---|---|
| `PRINCIPLES.md` | ✅ Same file | Gates every artifact |
| `DOCUMENT-STANDARDS.md` | ✅ Same file | Consulting-grade rules |
| `GLOSSARY.md` | ✅ Same file | Reference |
| 7 teaching scripts | ✅ Same scripts | Run with your own inputs |
| 4 sub-agents | ✅ Same agents | Same intelligence, different inputs |
| 4-layer enforcement | ✅ Same layers | Layer 4 hook still injects principles on every prompt |
| Pre-baked fallbacks | ❌ Removed | You're not on a 60-min clock; debugging > falling back |

---

## What changes vs. the workshop

| Aspect | Workshop | Take-home |
|---|---|---|
| Time pressure | 60 min, 50 people watching | Your pace |
| Example | Shared (PM Companion) | Your idea |
| Auditor cadence | After every module | Optional — run when you want a quality check |
| Fallback files | Active | Removed (debug instead) |
| Recording | Not recorded | Whatever you want |

---

## Three reminders for solo runs

1. **Run the principles check honestly.** Solo, nobody's watching. The discipline only works if you actually run it.
2. **Don't skip the user-first push-back.** When Module 1 asks you for a behavioural archetype, *don't* default to a demographic. The push-back is the lesson.
3. **The artifacts together are the PRD.** Don't write a separate Word doc at the end. Let the structured outputs speak.

---

## When to come back to the workshop format

- When you're onboarding a new PM to your team — run them through `/manthan-1` through `/manthan-6` on a real feature.
- When your team is over-scoping a v1 — run `/manthan-4` on the candidate list and watch features get cut.
- When a vibe-coded prototype is going generic — run `/manthan-5` to pin direction first.

---

## Read this

📄 [`PLAYBOOK.md`](./PLAYBOOK.md) — the full method, in prose, in one document.

---

*Built with Manthan by Palash Somani (pAI).*
