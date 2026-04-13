# pyramid-principle

Barbara Minto's Pyramid Principle as composable skills for professional writing.

## What it does

This plugin packages the Pyramid Principle as five discrete, composable skills designed to be invoked by larger writing workflows — agents, plugins, or directly by Claude Code. Skills operate in two modes: generative (draft, outline, structure) and evaluative (audit, diagnose, critique). Each skill is independently addressable by external agents using its skill ID, and they share canonical source material through `pyramid-principle-core`.

## The 5 Skills

| Skill | Role | Example triggers |
|---|---|---|
| `pyramid-principle-core` | Canonical rule library: SCQA, MECE, deduction vs induction, vertical/horizontal logic | "minto", "pyramid principle", "SCQA", "MECE" |
| `pyramid-short-form` | Emails, memos, exec summaries, one-pagers, BLUF notes | "write an email", "exec summary", "draft a memo" |
| `pyramid-long-form` | Reports, briefs, research writeups, multi-section documents | "structure this report", "outline a brief", "write a whitepaper" |
| `pyramid-presentation` | Deck storyline, slide headline hierarchy, data stories | "structure a deck", "slide flow", "ghost deck" |
| `pyramid-audit` | Diagnostic critique of existing content against pyramid rules | "audit this", "review for structural clarity", "is this well-structured?" |

## Composition

Canonical rules and definitions live in `pyramid-principle-core/references/` — a single source of truth for all structural principles. Sibling skills cross-reference this material using the path `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/...` so rule definitions are never duplicated. External agents address skills by their skill ID (e.g., `pyramid-audit`) without needing to know internal file layout. This makes it safe to update rule definitions in one place and have all skills reflect the change.

## Source grounding

`docs/source-anchors.md` holds verified verbatim quotes from Barbara Minto's *The Pyramid Principle* (2009 revised edition) with exact page citations. Each anchor has a stable ID (e.g., `minto-p22-scqa`) that skills cite directly, making source grounding visible and auditable without embedding raw quotes in every skill file.

## Status

v0.1.0 — initial release. 5 source anchors ship with this version; additional anchors planned for v0.2.

## License

MIT
