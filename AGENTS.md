# AGENTS.md — pyramid-principle

## What this plugin is

Barbara Minto's Pyramid Principle plus a separate source-integrity layer, packaged as six composable writing skills. No commands, no agents, no MCP — skills only. Each skill is independently addressable by its skill ID.

## How Codex accesses this plugin

`.codex-plugin/plugin.json` maps the `./skills` directory. Skills are auto-loaded on install. Invoke by skill ID (e.g., `pyramid-audit`).

## Skills

| Skill ID | Purpose | Load when |
|---|---|---|
| `pyramid-source-integrity` | Fact checking, source validation, calculations, data scope, and claim handoff | Load before and after structuring source-bound or data-bearing work |
| `pyramid-principle-core` | Canonical rule library: SCQA, MECE, deduction/induction, vertical/horizontal logic | Load for every structure or storyline task |
| `pyramid-short-form` | Draft emails, memos, exec summaries, one-pagers, BLUF notes | Short writing under ~500 words |
| `pyramid-long-form` | Structure reports, briefs, research writeups, multi-section documents | Multi-section or long-form writing |
| `pyramid-presentation` | Deck storyline, slide headline hierarchy, data stories | Presentation / slide structure |
| `pyramid-audit` | Diagnose existing writing against pyramid rules; rule-by-rule findings + fixes | Auditing or critiquing existing content |

## Composition

`pyramid-source-integrity` owns fact checking and data handling. For source-bound work, run it as a separate pre-check that produces an internal claim packet, run the structural skill from that packet, then run source integrity again as a separate post-check. Use the strongest available verification model and deterministic data tools around a smaller drafting model. `pyramid-principle-core` owns only the Pyramid Principle structure and storyline rules. Siblings cross-reference both owners instead of duplicating their contracts. `docs/source-anchors.md` grounds the Minto framework; it does not verify user-supplied facts.

## Version

0.1.2
