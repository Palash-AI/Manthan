# Reference Patterns — Visual Translation Library

> **What this is:** A library of specific visual patterns to borrow from well-known products, mapped to Module 5's reference brief. Used in Module 6 Step 6.3 by the visual-study sub-agent.
> **Why it exists:** Without this, "feels like Duolingo's loop" gets translated into Claude's guess of what Duolingo looks like — which is generic. With this, the prototype borrows *specific* visual moves that compound into recognisable feel.
> **How to use:** In Step 6.3, the agent reads the reference brief from Module 5, finds the matching entry below, and lists the 5-7 patterns to bake into the build.

---

## How a reference becomes a prototype

Three layers compound:

1. **Theme preset** in `scaffold.css` (sets colour palette, type, radius)
2. **Visual patterns** from this file (sets layout moves, signature elements, copy register)
3. **Per-screen spec** from Step 6.4 (sets what each screen needs)

Drop any layer and the output drifts toward generic. All three required.

---

## Reference 1 — Duolingo

> **When to pick:** habit-shaped daily-practice product. Streaks matter. Single focus per session. Audience needs warmth + permission to be a beginner.
> **Scaffold theme:** `data-theme="duolingo-like"`

### 7 visual patterns to borrow

| # | Pattern | How to implement |
|---|---|---|
| 1 | **Streak-as-hero** | Streak pill is the highest-contrast element in the header — yellow background, flame emoji, day count. Always visible. Tells the user "this is the thing that matters." |
| 2 | **Single-task focus card** | Home is dominated by ONE big card for today's task. Everything else is secondary. Don't show a list — show the next action, full-width, primary CTA. |
| 3 | **Chunky drop-shadow buttons** | Primary buttons have a `0 4px 0 rgba(0,0,0,0.10)` flat drop-shadow (not a soft blur). Tactile, game-like. Active state removes the shadow + translates down 4px (press effect). |
| 4 | **Character mascot moment** | One animated character (owl, fox, etc.) appears at a meaningful moment — completion, encouragement, error recovery. NOT decoration; it shows up where humans would. |
| 5 | **Progress nodes, not bars** | Use circular progress nodes connected by a path (like SVG-based level paths), not horizontal progress bars. Each lesson = a node. |
| 6 | **Soft round-everything** | Border radius is generous — buttons, cards, inputs, chips. `--r-lg: 16px`, `--r-xl: 20px`. Nothing has sharp corners. |
| 7 | **Warm celebration moments** | When the user completes something, the whole card glows briefly (`anim-glow`), confetti emoji float, the streak counter ticks up with animation. Earn the dopamine. |

### Voice register
- Encouraging, not condescending. "Great job!" not "Correct."
- Short. 1-2 sentences max.
- Permission to fail. "No worries, let's try again."
- Second-person warm. "You" + active verbs.

### Anti-patterns
- ❌ Dense data tables
- ❌ Multiple equally-weighted CTAs on home
- ❌ Cool greys / corporate palette
- ❌ Sharp / square corners

---

## Reference 2 — Notion

> **When to pick:** thinking / writing / planning product. Calm focus. Audience wants depth without clutter. Restraint > celebration.
> **Scaffold theme:** `data-theme="notion-like"`

### 7 visual patterns to borrow

| # | Pattern | How to implement |
|---|---|---|
| 1 | **Hidden until needed** | Most controls and chrome are hidden until hover or focus. No floating buttons, no permanent toolbars. The content is the interface. |
| 2 | **Dense info architecture** | Information density is high. Multiple cards per row when relevant. No "single hero card" pattern — assume the user is comfortable with detail. |
| 3 | **Slash command / quick action menu** | A `/` keyboard shortcut opens a command palette. Even in HTML prototype, simulate this with a search bar that filters actions. Signals "power user respect." |
| 4 | **Soft cream + paper feel** | Background is warm cream (`#F7F6F3`), cards are pure white. Type feels like ink on paper. Shadows are minimal. |
| 5 | **Inline editing affordances** | Everything looks editable. Titles render as plain text but on hover show a subtle outline. Lists have drag handles. The page IS the editor. |
| 6 | **Sidebar navigation, hierarchical** | If multiple screens, use a collapsible left sidebar with nested items. Not a bottom-nav. Notion = laptop-shaped, not phone-shaped. |
| 7 | **No celebration moments** | Completion is silent. The thing is now checked, the page now shows it. No confetti, no glow, no animation. The user knows what they did. |

### Voice register
- Plain English. Functional.
- Second-person where needed. "Add a column" not "Let's add a column!"
- No exclamation marks.
- Verb-led. "Type to add", "Click to edit".

### Anti-patterns
- ❌ Mascots, characters
- ❌ Bright primary colours
- ❌ Celebration animations
- ❌ Round chunky buttons

---

## Reference 3 — Linear

> **When to pick:** precision / speed / power-user product. Audience cares about keyboard shortcuts. Aesthetic is "expensive but unfussy."
> **Scaffold theme:** `data-theme="linear-like"`

### 7 visual patterns to borrow

| # | Pattern | How to implement |
|---|---|---|
| 1 | **Command-K everywhere** | `Cmd+K` opens a global action menu from any screen. The menu is fuzzy-searchable, keyboard-driven, with action labels + keyboard shortcuts visible. |
| 2 | **Subtle precision** | Border radius is small (`--r-md: 8px`). Shadows are almost invisible. Lines are 1px. Everything feels exact. |
| 3 | **Cool grey-blue palette** | Background nearly white but slightly cool. Accent is indigo (`#5E6AD2`). Text is near-black. Nothing warm. |
| 4 | **Status as pill** | Every item has a status pill — `Backlog` / `In Progress` / `Done`. Pills are small, coloured by status, always visible. |
| 5 | **Inline metadata** | Date, assignee, label, status — all visible inline next to the title. No need to click in. Dense but not cluttered. |
| 6 | **Keyboard shortcut overlay** | Hovering an action shows the keyboard shortcut next to it in a subtle key-cap style. `J` to move down, `K` to move up. Teach the user power. |
| 7 | **Subtle animation discipline** | Transitions are 120-150ms (faster than other refs). Nothing wiggles. Things appear and move with confidence. |

### Voice register
- Terse. One-line action labels.
- Verb-led. "Assign", "Move", "Close".
- No personality. The tool is the personality.
- Avoid greetings. No "Good morning!"

### Anti-patterns
- ❌ Soft / warm tones
- ❌ Big celebration moments
- ❌ Soft round corners
- ❌ Mascots, characters, decorative imagery

---

## Reference 4 — Khan Academy

> **When to pick:** earned-progression learning product. Audience needs to feel they're climbing. Mastery framing is core.
> **Scaffold theme:** `data-theme="khan-like"`

### 7 visual patterns to borrow

| # | Pattern | How to implement |
|---|---|---|
| 1 | **Earned progression bar** | At the top of every learning surface, a progress bar shows where the user is in the current unit/path. Always visible. Fills as they complete. |
| 2 | **Mastery dots** | Each skill has a 5-dot mastery indicator. Empty dots fill as the user masters that skill. Visual proof of growth. |
| 3 | **Blue + warm orange highlight** | Primary palette is calm blue (`#1865F2`), accent is warm orange (`#FFA631`). Blue for default state, orange for "active learning" or "next up." |
| 4 | **Step-by-step reveal** | Lessons are broken into 1-screen-per-concept. Next button reveals the next step. No infinite scroll. Each step earns its own attention. |
| 5 | **Energy points / streak as proof** | Show accumulated effort. "You've practiced 12 days this month." Effort > outcome in messaging. |
| 6 | **Hint ladder** | When user is stuck, hints reveal one at a time: vague hint → specific hint → solution. Each hint is a button. Respects their autonomy. |
| 7 | **Khan-blue celebration** | When a skill levels up, the dots fill with animation, blue background pulses, a one-line "Skill earned!" appears. Calm celebration, not loud. |

### Voice register
- Encouraging but accurate. "Almost! Look at the second term again."
- Second-person warm.
- Effort-praising. "Nice perseverance" not "You're so smart."
- Question-led when teaching. "What happens if...?"

### Anti-patterns
- ❌ Sales-y language
- ❌ Streak shaming ("You broke your streak!")
- ❌ Multiple competing CTAs
- ❌ Dark or moody palettes

---

## Reference 5 — Substack

> **When to pick:** publishing / reading / slow product. Warmth + craft matter. Audience comes for writers, not for software.
> **Scaffold theme:** `data-theme="substack-like"`

### 7 visual patterns to borrow

| # | Pattern | How to implement |
|---|---|---|
| 1 | **Serif headlines, sans body** | Headlines are serif (Iowan, Charter, Georgia). Body is sans-serif. Editorial feel. |
| 2 | **Generous whitespace** | Padding is 24-32px on cards. Type has 1.6 line height. Nothing is cramped. Slow product = slow visual rhythm. |
| 3 | **Warm cream + bold orange accent** | Background is warm cream (`#FFFBF5`). Accent is signature Substack orange (`#FF6719`). High contrast where it matters. |
| 4 | **Single-column reading width** | Content is max ~640px wide. Optimised for reading. No multi-column layouts. |
| 5 | **Author-as-hero** | Author name, photo, and one-line bio appear prominently in every post and at the top of every page. The writer is the brand. |
| 6 | **Subscribe-first CTA** | The single most prominent button is "Subscribe." Always visible. Always orange. The whole UI bends toward this one action. |
| 7 | **No celebration moments** | Like Notion, completion is silent. The post is now read, the comment is now posted. The content is the reward. |

### Voice register
- Editorial. Written like a magazine.
- First-person where appropriate. "I wrote this for you."
- Long-form OK. Don't compress for compression's sake.
- Date-stamped. Every post has a date.

### Anti-patterns
- ❌ Multiple equally-weighted CTAs
- ❌ Cool / corporate tones
- ❌ Compressed reading widths
- ❌ Generic sans-serif headlines

---

## Reference 6 — Headspace

> **When to pick:** wellness / calm / mindfulness product. Audience needs to feel safe, paced, gentle.
> **Scaffold theme:** `data-theme="headspace-like"`

### 7 visual patterns to borrow

| # | Pattern | How to implement |
|---|---|---|
| 1 | **Soft pastel gradients** | Backgrounds use pastel gradients — peach to orange, soft orange to butter yellow. Calming, never sharp. |
| 2 | **Breathing animations** | Hero element gently pulses (slow `idleFloat` animation, 3-4s duration). Mirrors a breath. |
| 3 | **Hand-drawn-feeling illustrations** | Imagery is illustrated, not photographic. Friendly characters or abstract shapes. Personal feel. |
| 4 | **Rounded everything** | Border radius generous (`--r-2xl: 24px`+). Buttons are pill-shaped. Cards are bubble-shaped. Nothing has corners. |
| 5 | **Time-of-day awareness** | UI references time. "Good morning" / "Tonight's wind-down" / "5-minute moment." The product knows when you opened it. |
| 6 | **Generous breathing space** | Padding is 24-32px. Text has 1.6 line height. Whitespace is content, not waste. |
| 7 | **Single focus per screen** | Like Duolingo's single-task pattern, but for wellness. One meditation, one breathing exercise, one moment. Never a list of choices. |

### Voice register
- Gentle. "Let's take a moment together."
- Second-person warm. "You" + gentle verbs.
- Permission to skip. "Whenever you're ready" — never urgent.
- No exclamation marks.

### Anti-patterns
- ❌ Sharp lines / corners
- ❌ Urgent / sales-y CTAs
- ❌ Multiple CTAs competing for attention
- ❌ Cool / corporate palette

---

## Reference 7 — Apple Notes

> **When to pick:** simple / minimal / hierarchy-through-typography product. Audience values clarity above all else.
> **Scaffold theme:** custom (use base `:root` defaults — they're already Notes-adjacent)

### 7 visual patterns to borrow

| # | Pattern | How to implement |
|---|---|---|
| 1 | **Hierarchy through type alone** | No colour, no icons, no chrome. Hierarchy comes from font size and weight only. Title 22px bold. Body 15px regular. Metadata 11px muted. |
| 2 | **Generous left padding** | Body content has 20-24px left margin. Feels like a real notebook page. |
| 3 | **Subtle yellow note-paper** | Background is a faint warm yellow (`#FFFCE8` or similar). Just enough to feel like paper. Not pure white. |
| 4 | **Folder list = sidebar** | If multiple screens, left sidebar with simple folder list. No icons, just labels + counts. |
| 5 | **Native iOS controls everywhere** | Pickers, toggles, sliders use native iOS look. Don't reinvent. |
| 6 | **Search-first** | The primary action is "search." Visible at top of every screen. Replaces filter / sort / category navigation. |
| 7 | **Nothing happens visually** | Transitions are minimal. Items appear. Items disappear. No bouncing, no fading, no celebrating. |

### Voice register
- Empty UI. No marketing copy.
- Labels are nouns. "Folder," "Note," "Tag."
- No greetings.

### Anti-patterns
- ❌ Decorative imagery
- ❌ Coloured CTAs
- ❌ Multiple competing actions per screen
- ❌ Animations beyond fade

---

## How to use this file in Step 6.3 (Visual study)

The script invokes a sub-agent with prompt:

```
Read reference/visual-scaffold/reference-patterns.md.
Find the entry that best matches our direction brief's reference 
("Feels like {X}'s {property}").
List the 5-7 most relevant visual patterns from that entry that 
apply to OUR product's screens.
Output:
- Which 5-7 patterns
- For each, a one-line "how it'll show up in OUR build"
- Confirm the scaffold.css data-theme to set
- Confirm the voice register summary
```

The build agents in Step 6.6 then use this output + the per-screen specs + the scaffold + the voice rules. All four constraints compound.

---

## When the reference doesn't match any entry

If Module 5's reference brief picks a product not in this file (e.g., "Feels like Robinhood's monochrome precision"):

1. The visual-study sub-agent should produce a **bespoke 7-pattern list** following the same structure (visual moves + voice + anti-patterns).
2. The custom list lives at `outputs/m1.5-reference-patterns-{slug}.md` for that run.
3. Optional: contribute the list back here for future Manthan runs.

---

## Maintenance

When a new common reference emerges (a product Palash uses to anchor briefs often), add it here with the same 7-pattern structure. Each addition compounds the value for all future Manthan runs.

---

*Built with Manthan by Palash Somani (pAI)*
