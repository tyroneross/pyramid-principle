---
name: pyramid-principle-core
description: Use when user asks about the Pyramid Principle, Minto, SCQA, MECE, governing thought, key line, vertical or horizontal logic, deductive or inductive reasoning, or answer-first structure. Canonical rule library for sibling writing skills.
version: 0.1.0
---

# Pyramid Principle Core

## Purpose

Supply the canonical structural rules shared by every skill in this plugin. This skill explains and governs the framework. It does not draft or audit a finished artifact.

Source material: Barbara Minto, *The Pyramid Principle* (2009 revised edition). Verified quotations and page citations live in `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`.

## Route the Request

Load this skill for any Pyramid Principle structure or storyline task. When the task also uses sources, facts, or data, `pyramid-source-integrity` clears those claims first. Hand off when:

- the user wants fact checking, source validation, or data handling → `pyramid-source-integrity`
- the user wants an email, memo, executive summary, one-pager, BLUF, Slack update, or status note → `pyramid-short-form`
- the user wants a report, brief, proposal, or multi-section document → `pyramid-long-form`
- the user wants a deck or presentation storyline → `pyramid-presentation`
- the user wants existing writing diagnosed → `pyramid-audit`

## Structural Contract for Generated Output

Every sibling skill applies these rules before its medium-specific guidance:

1. **The agent states the main answer before its supporting points.** If the reader cannot understand the answer without context, the agent gives only the context required to understand it, then states the answer before evidence or detail.
2. **The agent groups peers only when they answer the same parent question and perform the same logical role.** It groups reasons with reasons, evidence with evidence, steps with steps, findings with findings, and risks with risks. Different topics may remain peers when one accurate role label describes every point.
3. **The agent treats counts and positions as format defaults, not correctness tests.** It adjusts them to the reader, medium, evidence, and complexity while preserving answer-first structure and valid grouping.
4. **The agent uses examples as structural patterns, not task content.** It does not copy an example's names, facts, scenario, terminology, or conclusion unless the user supplied them for the current task.
5. **The agent returns the requested artifact by default.** It does not include framework labels, drafting notes, assumptions, or self-check commentary unless the user requests them or unresolved ambiguity prevents a reliable artifact.

`pyramid-source-integrity` separately owns fact checking, source validation, calculations, data scope, and the pre-draft claim ledger. The structural layer uses the cleared claim set but does not reclassify or strengthen its claims.

## Three Rules of a Valid Pyramid

Every grouping must satisfy all three rules.

### 1. The parent summarizes its children

The parent is a substantive claim that the points below collectively prove, explain, or support. It is not a topic or container label. The governing thought is the apex claim, and every lower level directly supports the claim above it. (`minto-p5-pyramid-sorting`)

### 2. Peers perform the same logical role

Every peer answers the same parent question and belongs to one named kind. The agent tests the parent question and role before separating different topics. A set fails only when no accurate parent question and role label describes every peer. (`minto-p5-pyramid-sorting`, `minto-p96-mece`)

### 3. Peers follow one logical order

The agent chooses the order that matches what the set represents and does not mix order rules within one peer set. (`minto-p5-pyramid-sorting`)

## Four Logical Orders

- **Deductive:** Each point derives from the prior point and ends in a conclusion.
- **Chronological:** Steps or events follow time or process sequence.
- **Structural:** Points are explicit parts of a whole or categories within a defined structure.
- **Comparative:** Points are ranked by an explicit criterion.

The text must show the order. List position alone does not establish comparative order.

## Vertical Logic: Question and Answer

Every asserted point raises a reader question. The next level answers that exact question:

- `Why?` asks for reasons.
- `How?` asks for steps or a mechanism.
- `Why do you say that?` asks for evidence.

Material that answers a different question belongs under another parent or outside the artifact. (`minto-p17-vertical-qa`)

## Horizontal Logic: Deduction or Induction

Every peer set uses one reasoning mode:

- **Deductive:** Each point depends on the prior point; the parent states the conclusion.
- **Inductive:** Each point independently belongs to one like category; the parent states the inference supported by the set.

The agent does not mix deductive steps and inductive members within one peer set. (`minto-p63-deduction-induction`)

## SCQA Introduction

Use an introduction only when the reader needs common ground before receiving the governing thought:

- **Situation:** Shared context the reader accepts.
- **Complication:** The change, tension, or problem that makes the Situation unstable.
- **Question:** The question naturally raised by the Complication; it may remain implicit.
- **Answer:** The governing thought, stated before supporting points.

When context is already shared, begin with the Complication or Answer. SCQA is a preamble, not a mandatory sentence or slide count. (`minto-p22-scqa`)

## MECE Grouping

The agent checks mutual exclusivity and collective exhaustiveness separately:

- **Mutually exclusive:** No two peers describe the same underlying phenomenon within the parent scope.
- **Collectively exhaustive:** The set covers the relevant universe defined by the parent scope.

A set is exhaustive only when its parent defines the relevant universe. If the cleared claim set does not define that universe, the agent does not call the set exhaustive. (`minto-p96-mece`)

Before accepting a peer set, the agent:

1. writes the parent question;
2. names the shared role with a specific plural noun;
3. checks overlap;
4. checks completeness only against a defined universe;
5. confirms the parent is an inference, not a container;
6. uses the number of peers the meaning requires and regroups only when a valid category exists.

Minto's group-size observation makes a growing flat list a cue to test categorization, not a universal pass/fail count. (`minto-p7-magical-number-seven`)

## Source Anchors

- `minto-p5-pyramid-sorting` — pyramid rules and logical orders
- `minto-p7-magical-number-seven` — group-size observation
- `minto-p17-vertical-qa` — vertical question-and-answer logic
- `minto-p22-scqa` — SCQA introduction
- `minto-p63-deduction-induction` — deductive and inductive reasoning
- `minto-p96-mece` — mutual exclusivity and collective exhaustiveness

## References

- `references/rules-of-pyramid.md` — detailed rules and worked examples
- `references/scqa-pattern.md` — medium-specific SCQA guidance and examples
- `references/vertical-horizontal-logic.md` — detailed logic examples
- `references/mece-grouping.md` — grouping diagnostics and examples
- `references/llm-adaptation.md` — modern LLM failure modes and prompt patterns
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-source-integrity/SKILL.md` — separate fact-checking and data-handling contract
- `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`

Reference examples are never task evidence. Load them only when detailed explanation or diagnosis requires them, and do not copy their content into a user artifact.
