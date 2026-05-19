# Visual Scaffold — How to use

> **What this is:** Pre-built CSS foundation + reference pattern library that any Manthan Module 6 prototype inherits.
> **Why it exists:** Reverse-engineered from home.html (Seekho Companion, 14+ design passes). Bakes in ~60% of premium-feel visual decisions so build agents focus on layout and content, not on reinventing typography, spacing, shadows, animation.

---

## Files in this folder

| File | Purpose | When loaded |
|---|---|---|
| [`scaffold.css`](./scaffold.css) | Design tokens, theme presets, component primitives, animation utilities | Copy into the prototype folder at start of Module 6 build (Step 6.2). Linked as first `<link>` in `index.html`. |
| [`reference-patterns.md`](./reference-patterns.md) | 7 reference products × 7 visual patterns each, mapped to scaffold theme presets | Read in Step 6.3 by the visual-study sub-agent |

---

## How the scaffold becomes a prototype

```
Module 5 direction brief                Reference brief (e.g., "Duolingo's daily loop")
       ↓                                       ↓
Module 6 Step 6.2 ─→ scaffold.css copied into outputs/prototype/
       ↓                                       ↓
Module 6 Step 6.3 ─→ visual-study agent reads reference-patterns.md
                     finds Duolingo entry → lists 7 patterns to borrow
                     confirms data-theme="duolingo-like"
       ↓
Module 6 Step 6.4 ─→ per-screen + per-component spec
       ↓
Module 6 Step 6.5 ─→ voice rules locked
       ↓
Module 6 Step 6.6 ─→ parallel build agents construct prototype
                     INSIDE the scaffold, with patterns + spec + voice
                     as constraints
       ↓
Module 6 Step 6.7 ─→ iteration pass: re-read against reference brief
                     2-3 targeted edits
```

---

## Theme presets included in `scaffold.css`

| Preset | Reference | Vibe |
|---|---|---|
| `(default)` | Notion-ish | Cream, restrained, forest-green accent |
| `data-theme="duolingo-like"` | Duolingo | Warm yellow + green, gamified, friendly |
| `data-theme="notion-like"` | Notion | Calm cream, hidden chrome, ink-on-paper |
| `data-theme="linear-like"` | Linear | Cool greys, indigo accent, precision |
| `data-theme="khan-like"` | Khan Academy | Blue + warm orange, earned progression |
| `data-theme="substack-like"` | Substack | Cream + orange, serif headlines, editorial |
| `data-theme="headspace-like"` | Headspace | Peach pastels, breathing animations |

---

## Adding a new theme

When a new reference is used often, add:

1. A `[data-theme="NEW-NAME-like"]` block in `scaffold.css` (override the tokens that should differ from default).
2. A new entry in `reference-patterns.md` following the existing 7-pattern structure.
3. A line in this README's theme presets table.

Each addition compounds the value for all future Manthan runs.

---

## What the scaffold does NOT cover

- Brand-specific assets (logos, illustrations, custom icons)
- Domain-specific layouts (e.g., chat thread vs. dashboard vs. card-feed)
- Backend integration
- Real data fetching

Those live in the per-screen spec (Step 6.4) and the build itself (Step 6.6).

---

*Built with Manthan by Palash Somani (pAI)*
