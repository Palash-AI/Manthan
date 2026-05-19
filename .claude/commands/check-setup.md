---
description: "Verify Manthan repo is ready for the workshop"
---

Run this bash command from the repo root and show only its output. Do NOT narrate, explain, or summarise.

```bash
ok=true
for f in CLAUDE.md PRINCIPLES.md DOCUMENT-STANDARDS.md GLOSSARY.md CONCEPT-NOTE.md README.md course-structure.json; do
  [ -f "$f" ] || { echo "MISSING: $f"; ok=false; }
done
for a in manthan-researcher jtbd-synthesizer scope-editor principle-auditor; do
  [ -f ".claude/agents/${a}.md" ] || { echo "MISSING agent: ${a}"; ok=false; }
done
for c in manthan-1 manthan-2 manthan-3 manthan-3-5 manthan-4 manthan-5 manthan-6; do
  [ -f ".claude/commands/${c}.md" ] || { echo "MISSING command: /${c}"; ok=false; }
done
for m in m1.1-idea-and-scope m1.2-research m1.3-jtbd-archetypes m1.3.5-user-need-map m1.4-pareto m1.5-direction-brief m1.6-build-prototype; do
  [ -f "lesson-modules/m1-idea-to-prototype/${m}/CLAUDE.md" ] || { echo "MISSING module: ${m}"; ok=false; }
done
$ok && echo "Manthan ready."
```

If the output is exactly `Manthan ready.`, the repo is set. Otherwise show the missing items and tell the learner to re-clone or raise it on the workshop channel.
