# pyramid-principle

Turn source material into decision-ready professional writing: validate the claims, state the answer before support, and group the support logically.

## What it does

This plugin packages Barbara Minto's Pyramid Principle and a separate source-integrity layer as six discrete, composable skills. Source integrity checks claims and data. The core and generative skills build the structure and storyline. The audit skill diagnoses structural logic.

## The 6 Skills

| Skill | Role | Example triggers |
|---|---|---|
| `pyramid-source-integrity` | Fact checking, source validation, calculations, data scope, and claim handoff | "fact-check this", "use only these facts", "validate the data" |
| `pyramid-principle-core` | Canonical rule library: SCQA, MECE, deduction vs induction, vertical/horizontal logic | "minto", "pyramid principle", "SCQA", "MECE" |
| `pyramid-short-form` | Emails, memos, exec summaries, one-pagers, BLUF notes | "write an email", "exec summary", "draft a memo" |
| `pyramid-long-form` | Reports, briefs, research writeups, multi-section documents | "structure this report", "outline a brief", "write a whitepaper" |
| `pyramid-presentation` | Deck storyline, slide headline hierarchy, data stories | "structure a deck", "slide flow", "ghost deck" |
| `pyramid-audit` | Diagnostic critique of existing content against pyramid rules | "audit this", "review for structural clarity", "is this well-structured?" |

## Composition

The plugin separates claim integrity from communication structure:

1. A separate `pyramid-source-integrity` pre-check validates supplied claims, calculations, scope, and external facts when tools are available. Every data point receives a specific source and locator, confidence level and reason, and permitted-use action before entering the internal claim packet.
2. `pyramid-principle-core` and a format skill select, group, order, and express only the packet's claims.
3. A separate `pyramid-source-integrity` post-check compares the finished artifact with the original packet and removes or corrects unsupported content.

For smaller drafting models and strict source-bound work, the host should run these as three model calls and use its strongest available verification model for the pre-check and post-check. Deterministic tools should verify material calculations. A capable host may keep the operations as distinct internal stages, but the structure skill never approves its own factual output.

Canonical Pyramid Principle rules live in `pyramid-principle-core/references/`. Fact and data rules live in `pyramid-source-integrity/SKILL.md`. Each responsibility has one owner, and every skill remains independently addressable by its skill ID.

## Source and confidence contract

Every factual claim and derived value must retain a source ID and exact locator. Every source ID resolves to a complete source-register record. A locator identifies the prompt fact, quotation, URL section, file page, sheet and cells, table row, query, or calculation inputs that support the point. Bare labels such as `user input`, `company data`, `derived`, a dash, or a domain name do not pass.

| Confidence | Required drafting action |
|---|---|
| High | State directly with its source trace. |
| Medium | State with source attribution or an explicit limitation. |
| Low | Keep out of central support; use only as a limitation or verification lead. |
| Unverified | Exclude from the artifact as fact. |

Every level requires a reason covering source quality, directness of support, corroboration or conflict, and data validation. Confidence is qualitative evidence judgment, not an invented probability. A derived value cannot exceed the confidence of its weakest required input.

## Capability boundary

The plugin can check consistency with supplied material, require source and confidence traces, direct deterministic calculation and research tools, and preserve data scope. It cannot certify that a supplied source is true, access current information without a tool, recover missing data definitions, prove causation from correlation, turn confidence into a defensible probability without a model, or make a small model reliable through instructions alone.

## Source grounding

`docs/source-anchors.md` grounds the framework itself with verified quotations from Barbara Minto's *The Pyramid Principle* (2009 revised edition). These anchors support the structural rules; they do not verify facts in a user's artifact.

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
