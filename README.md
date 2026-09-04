# pyramid-principle

Reports and memos bury the answer under background, so readers must reconstruct the argument and decisions stall. This plugin applies Barbara Minto's Pyramid Principle (answer first, MECE-grouped support) and keeps a separate source-integrity layer that requires a specific source, locator, and confidence for every fact. Your reader gets the decision in the first sentence and can trust every number under it.

## Start here

You do not type a command. Describe the writing task in plain language and the right skill loads itself: "draft this as an exec summary", "structure this report", "audit this memo for structure", "fact-check these claims first". The routing table below shows which phrasing reaches which skill.

To report a bug or request a feature: **`/pyramid-principle:submit-feedback`**.

## What it does

This plugin packages Barbara Minto's Pyramid Principle and an optional source-integrity layer as six discrete, composable skills. The default path is the core plus one writing skill. Add source integrity when the work requires fact checking, material data, or strict source control.

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

The plugin keeps claim integrity separate from communication structure:

1. For ordinary structure-only writing, `pyramid-principle-core` and one format skill build the artifact directly.
2. When facts or data materially affect the output, `pyramid-source-integrity` first gives every data point a specific source and locator, confidence level, and confidence reason.
3. The core and format skill structure the cleared content. A source-integrity recheck then removes or corrects unsupported additions.

Strict trace mode is optional. Use it for `use only these facts`, audit-ready or high-risk work, conflicting sources, or separate verification around a smaller drafting model. It adds claim IDs, a source register, and trace tags. Deterministic tools should verify material calculations.

Canonical Pyramid Principle rules live in `pyramid-principle-core/references/`. Fact and data rules live in `pyramid-source-integrity/SKILL.md`. Each responsibility has one owner, and every skill remains independently addressable by its skill ID.

## Source and confidence contract

When source integrity is active, every factual claim and derived value must retain a specific source, exact locator, confidence level, and reason. A locator identifies the prompt fact, quotation, URL section, file page, sheet and cells, table row, query, or calculation inputs that support the point. Bare labels such as `user input`, `company data`, `derived`, a dash, or a domain name do not pass. Strict mode adds source IDs and a source register only when the trace needs them.

| Confidence | Required drafting action |
|---|---|
| High | State directly without strengthening the source. |
| Medium | State with source attribution or an explicit limitation. |
| Low | Keep out of central support; use only as a limitation or verification lead. |
| Unverified | Exclude from the artifact as fact. |

Every level requires a reason covering source quality, directness of support, corroboration or conflict, and data validation. Confidence is qualitative evidence judgment, not an invented probability. A derived value cannot exceed the confidence of its weakest required input.

Confidence itself controls the drafting action. The plugin does not repeat the same instruction in a separate `permitted use` field.

## Direct writing contract

Every writing skill applies the same parent rules:

- State the answer before support and give each sentence one main claim.
- Name a specific actor, use an active verb, and state a specific outcome.
- Replace vague adjectives and adverbs with validated measures when available; never invent data to sound precise.
- Carry key terms from each parent claim into its supporting statements so the relationship remains visible.
- Connect sentences from given information to new information and make peer bullets grammatically and logically parallel.

## Capability boundary

The plugin can check consistency with supplied material, require source and confidence traces, direct deterministic calculation and research tools, and preserve data scope. It cannot certify that a supplied source is true, access current information without a tool, recover missing data definitions, prove causation from correlation, turn confidence into a defensible probability without a model, or make a small model reliable through instructions alone.

## Source grounding

`docs/source-anchors.md` grounds the framework itself with verified quotations from Barbara Minto's *The Pyramid Principle* (2009 revised edition). These anchors support the structural rules; they do not verify facts in a user's artifact.

## Status

Composable Codex + Claude packaging. 6 source anchors ship today; additional anchors planned next. The plugin manifests omit `version` by design — Claude Code resolves the installed version to the git commit SHA, so every push ships and no hand-pinned number can go stale. `package.json` carries the npm version.

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
