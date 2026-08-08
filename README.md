# pyramid-principle

Turn source material into decision-ready professional writing: state the answer before support, group claims logically, and distinguish evidence from interpretation.

## What it does

This plugin packages Barbara Minto's Pyramid Principle as five discrete, composable skills for agents and writing workflows. Generative skills draft and structure requested artifacts; the audit skill diagnoses existing writing. The shared core keeps the structural rules, evidence safeguards, example isolation, and output contract consistent across every format.

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

v0.1.2 — composable Codex + Claude packaging. 6 source anchors ship with this version; additional anchors planned for v0.2.

## License

Apache-2.0

## Codex

This package now ships an additive Codex plugin surface alongside the existing Claude Code package. The Claude package remains authoritative for Claude behavior; the Codex package adds a parallel `.codex-plugin/plugin.json` install surface without changing the Claude runtime.

Package root for Codex installs:
- the repository root (`.`)

Primary Codex surface:
- skills from `./skills` when present
- MCP config from `(none)` when present

Install the package from this package root using your current Codex plugin install flow. The Codex package is additive only: Claude-specific hooks, slash commands, and agent wiring remain unchanged for Claude Code.
