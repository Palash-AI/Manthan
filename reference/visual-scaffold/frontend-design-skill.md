---
name: frontend-design
description: Create distinctive, production-grade frontend interfaces with high design quality. Use this skill when the user asks to build web components, pages, or applications. Generates creative, polished code that avoids generic AI aesthetics.
license: Complete terms in LICENSE.txt
source: Vendored from anthropics/claude-code · plugins/frontend-design/skills/frontend-design/SKILL.md
vendored_for: Manthan m1.6 — anti-slop constraint for parallel build agents in Step 6.6
---

> **Vendored copy.** Original lives at `github.com/anthropics/claude-code/plugins/frontend-design/skills/frontend-design/SKILL.md`. Refresh manually on Manthan releases. Do not edit.

---

This skill guides creation of distinctive, production-grade frontend interfaces that avoid generic "AI slop" aesthetics. Implement real working code with exceptional attention to aesthetic details and creative choices.

The user provides frontend requirements: a component, page, application, or interface to build. They may include context about the purpose, audience, or technical constraints.

## Design Thinking

Before coding, understand the context and commit to a BOLD aesthetic direction:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Tone**: Pick an extreme: brutally minimal, maximalist chaos, retro-futuristic, organic/natural, luxury/refined, playful/toy-like, editorial/magazine, brutalist/raw, art deco/geometric, soft/pastel, industrial/utilitarian, etc. There are so many flavors to choose from. Use these for inspiration but design one that is true to the aesthetic direction.
- **Constraints**: Technical requirements (framework, performance, accessibility).
- **Differentiation**: What makes this UNFORGETTABLE? What's the one thing someone will remember?

**CRITICAL**: Choose a clear conceptual direction and execute it with precision. Bold maximalism and refined minimalism both work - the key is intentionality, not intensity.

Then implement working code (HTML/CSS/JS, React, Vue, etc.) that is:
- Production-grade and functional
- Visually striking and memorable
- Cohesive with a clear aesthetic point-of-view
- Meticulously refined in every detail

## Frontend Aesthetics Guidelines

Focus on:
- **Typography**: Choose fonts that are beautiful, unique, and interesting. Avoid generic fonts like Arial and Inter; opt instead for distinctive choices that elevate the frontend's aesthetics; unexpected, characterful font choices. Pair a distinctive display font with a refined body font.
- **Color & Theme**: Commit to a cohesive aesthetic. Use CSS variables for consistency. Dominant colors with sharp accents outperform timid, evenly-distributed palettes.
- **Motion**: Use animations for effects and micro-interactions. Prioritize CSS-only solutions for HTML. Use Motion library for React when available. Focus on high-impact moments: one well-orchestrated page load with staggered reveals (animation-delay) creates more delight than scattered micro-interactions. Use scroll-triggering and hover states that surprise.
- **Spatial Composition**: Unexpected layouts. Asymmetry. Overlap. Diagonal flow. Grid-breaking elements. Generous negative space OR controlled density.
- **Backgrounds & Visual Details**: Create atmosphere and depth rather than defaulting to solid colors. Add contextual effects and textures that match the overall aesthetic. Apply creative forms like gradient meshes, noise textures, geometric patterns, layered transparencies, dramatic shadows, decorative borders, custom cursors, and grain overlays.

NEVER use generic AI-generated aesthetics like overused font families (Inter, Roboto, Arial, system fonts), cliched color schemes (particularly purple gradients on white backgrounds), predictable layouts and component patterns, and cookie-cutter design that lacks context-specific character.

Interpret creatively and make unexpected choices that feel genuinely designed for the context. No design should be the same. Vary between light and dark themes, different fonts, different aesthetics. NEVER converge on common choices (Space Grotesk, for example) across generations.

**IMPORTANT**: Match implementation complexity to the aesthetic vision. Maximalist designs need elaborate code with extensive animations and effects. Minimalist or refined designs need restraint, precision, and careful attention to spacing, typography, and subtle details. Elegance comes from executing the vision well.

Remember: Claude is capable of extraordinary creative work. Don't hold back, show what can truly be created when thinking outside the box and committing fully to a distinctive vision.

---

## Manthan integration notes (not part of Anthropic's original SKILL)

This file is referenced as the **5th compounding constraint** in `m1.6-build-prototype` Step 6.6. The other four constraints — scaffold.css, reference-patterns, per-screen spec, voice rules — already provide structure, content, and tone. This file's role is narrow but specific: **block default visual slop** at code-generation time.

In Manthan's context:
- **Aesthetic direction is NOT free.** Bold-maximalism vs refined-minimalism is determined upstream by the direction brief's reference (Module 5) — not by the build agent. The build agent inherits the direction from the reference brief and uses this file to avoid slopping toward defaults *within* the chosen direction.
- **Typography:** the scaffold's `--font-display` and `--font-body` tokens already constrain the family. This file ensures the agent doesn't override them with Inter/Roboto/Arial under pressure.
- **Color:** the scaffold's data-theme tokens are the source of truth. This file reinforces "no purple gradient on white" as a slop guard.
- **Spatial composition + motion + backgrounds:** the build agent gets these freedoms from this file, bounded by the per-screen spec's component table.

If an agent's output drifts toward generic SaaS in Step 6.7 (iteration pass), the drift-check row added to the iteration table catches it explicitly against this file's forbidden list.

---

*Vendored for Manthan by Palash Somani (pAI). Original © Anthropic.*
