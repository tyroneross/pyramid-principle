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

`pyramid-principle-core` owns the parent writing rules: answer-first structure, valid grouping, specific nouns, active verbs, evidence-led wording, key-term continuity, and logical sentence flow. Use it with one format skill for ordinary writing. Add `pyramid-source-integrity` when the task requires fact checking, material data, strict source control, or consequential factual output. Its light check gives every data point a specific source and locator, confidence level, and reason; confidence directly determines how the writer treats the point. Use optional strict trace mode for closed source sets, audit-ready or high-risk work, conflicting sources, or separate verification around a smaller model. Strict mode adds claim IDs and a source register, not a redundant permitted-use field. Use deterministic tools for material calculations. `docs/source-anchors.md` grounds the Minto framework; it does not verify user-supplied facts.

## Version

0.1.2
