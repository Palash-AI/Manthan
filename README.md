# Manthan

> **Structured Thinking For End-to-End Product Experience Building with AI.**
> A skill by Palash Somani (pAI).

---

## What this is

AI made shipping fast. Clarity didn't get faster with it. *"Make it user-friendly"* still produces guesses. *"Make it intuitive"* still produces decoration. The thing that turns velocity into leverage is **structured thinking** — the discipline applied *before* the prompt, not in place of it.

Manthan is that discipline, made teachable. One worked example, end-to-end: idea → research → JTBD → archetypes → Pareto → direction → working Claude Code prototype.

For the philosophy behind the method, read [`CONCEPT-NOTE.md`](./CONCEPT-NOTE.md).

---

## What you get

| You leave with | Where it lives |
|---|---|
| The concept — why structure beats one-shot prompting | [`CONCEPT-NOTE.md`](./CONCEPT-NOTE.md) |
| The full sequence — seven steps in order | [`lesson-modules/m1-idea-to-prototype/`](./lesson-modules/m1-idea-to-prototype/) |
| The questions to ask at every gate | [`PRINCIPLES.md`](./PRINCIPLES.md) + each module's `CLAUDE.md` |
| The product-thinking glossary, with Swiggy examples | [`GLOSSARY.md`](./GLOSSARY.md) |
| A reproducible method to apply on your own ideas | [`take-home/`](./take-home/) |

---

## How to start

### 1. Install Claude Code

Visit [https://claude.com/claude-code](https://claude.com/claude-code) and install for your OS.

Verify:

```bash
claude --version
# → should show a version number
```

### 2. Clone this repo

```bash
git clone https://github.com/Palash-AI/Manthan.git manthan
cd manthan
```

### 3. Launch Claude Code in this folder

```bash
claude
```

### 4. Read the concept (5 min)

Open [`CONCEPT-NOTE.md`](./CONCEPT-NOTE.md). It frames why the workshop exists and what shifts when you apply it.

### 5. Skim the glossary (3 min)

Open [`GLOSSARY.md`](./GLOSSARY.md). 15 product-thinking terms, each with a Swiggy example. Reference during. Keep after.

### 6. Run the setup check

```
/check-setup
```

You should see **"Manthan ready."**

---

## The seven modules

| # | Command | What you build |
|---|---|---|
| 1 | `/manthan-1` | Idea + scope skeleton |
| 2 | `/manthan-2` | Research blitz (parallel sub-agents) |
| 3 | `/manthan-3` | JTBD grid + 4 archetypes |
| **3.5** | **`/manthan-3-5`** | **User Need Map — 8 dimensions × specific needs. Drives Module 4.** |
| 4 | `/manthan-4` | Pareto v1 lock (cuts traceable to needs) |
| 5 | `/manthan-5` | Direction brief (reference brief + emotion + AI surfaces with rubric depth) |
| 6 | `/manthan-6` | Polished Claude Code HTML prototype (with iteration pass) |

---

## After the workshop

The same seven steps, packaged for self-service use on your own ideas, lives in [`take-home/`](./take-home/). Fork the repo, run `/manthan-1` with your own product idea, and the skill walks you through end-to-end.

---

## License

Licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](./LICENSE). Use it, adapt it, build on it — just keep the credit line.

---

## Brand

Every output produced via Manthan is signed:

> *Built with Manthan by Palash Somani (pAI)*

---

*Manthan: the churning that extracts the essential.*
