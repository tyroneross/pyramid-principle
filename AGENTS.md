# AGENTS.md — pyramid-principle

## What this plugin is

Barbara Minto's Pyramid Principle packaged as five composable writing skills. No commands, no agents, no MCP — skills only. Each skill is independently addressable by its skill ID.

## How Codex accesses this plugin

`.codex-plugin/plugin.json` maps the `./skills` directory. Skills are auto-loaded on install. Invoke by skill ID (e.g., `pyramid-audit`).

## Skills

| Skill ID | Purpose | Load when |
|---|---|---|
| `pyramid-principle-core` | Canonical rule library: SCQA, MECE, deduction/induction, vertical/horizontal logic | Load first; referenced by all siblings |
| `pyramid-short-form` | Draft emails, memos, exec summaries, one-pagers, BLUF notes | Short writing under ~500 words |
| `pyramid-long-form` | Structure reports, briefs, research writeups, multi-section documents | Multi-section or long-form writing |
| `pyramid-presentation` | Deck storyline, slide headline hierarchy, data stories | Presentation / slide structure |
| `pyramid-audit` | Diagnose existing writing against pyramid rules; rule-by-rule findings + fixes | Auditing or critiquing existing content |

## Composition

`pyramid-principle-core` is the rule library — load it first. Siblings cross-reference it via `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/...` so definitions are never duplicated. `docs/source-anchors.md` holds verified verbatim Minto quotes with page citations; skills cite anchors by stable ID (e.g., `minto-p22-scqa`) for auditable grounding.

## Version

0.1.2
