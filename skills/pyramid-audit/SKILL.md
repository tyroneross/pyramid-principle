---
name: pyramid-audit
description: Use when user provides existing writing and asks for structural critique against the Pyramid Principle. Produces rule-grounded findings and ranked fixes without rewriting.
---

# Pyramid Audit

## Purpose

Diagnose user-supplied writing against Barbara Minto's Pyramid Principle. Load `pyramid-principle-core` for the structural rules. Load `pyramid-source-integrity` separately only when the user also requests fact or data validation.

This skill audits. It does not rewrite the content, draft a replacement, or explain the entire framework.

## Route the Request

Use this skill when the user supplies an email, memo, report, outline, deck storyline, or other professional writing and asks what is structurally wrong, whether it follows the Pyramid Principle, or how to improve its logic.

Hand off when:

- the user wants new short-form writing → `pyramid-short-form`
- the user wants a report or multi-section document drafted → `pyramid-long-form`
- the user wants a deck drafted → `pyramid-presentation`
- the user wants the framework explained → `pyramid-principle-core`
- the user wants claims, sources, calculations, or data checked rather than structure → `pyramid-source-integrity`

Do not audit without user-supplied content.

## Identify the Inputs

Before auditing, the agent identifies:

1. **Content:** The exact text, file, or user-provided source to audit.
2. **Reader question:** Use the user's question when supplied. Otherwise infer one from the content and label it as inferred.
3. **Medium:** Email, memo, report, deck, or fragment. Infer it only when the content makes the medium clear.

The reader question and medium are audit metadata. They are not part of the document and cannot supply a missing Situation, Complication, claim, or evidence.

## Run the Audit

The agent performs five checks in order.

### 1. Governing Thought

- Locate the single main claim and quote it verbatim, or write `Not stated`.
- Check whether it directly answers the reader question.
- Distinguish the answer from its evidence. When one sentence recommends an action and another sentence gives the reason, the recommendation is the governing thought even if the evidence appears first.
- Check whether it appears before supporting evidence or detail. If the reader must process support before learning the main claim, flag a buried governing thought.
- Always run this check. (`minto-p5-pyramid-sorting`)

### 2. SCQA Introduction

- Apply SCQA only when the supplied content contains an opening preamble.
- A governing thought followed by support is pyramid body, not an implied preamble.
- A fragment, list, section, or continuation with no opening preamble receives: `Not applicable — the supplied content contains no opening preamble.`
- When a preamble exists, rate Situation, Complication, Question, and Answer as `Pass`, `Weak`, or `Fail` using only the supplied text.
- Do not infer a Situation or Complication from the reader question or assumed shared knowledge. (`minto-p22-scqa`)

### 3. Vertical Logic

For each major point, state the question it raises: `Why?`, `How?`, or `Why do you say that?` Check whether the material immediately below answers that question.

Flag a violation only when the supplied text shows a different answer, premature information, or an unsupported hanging assertion. Quote the break and cite `minto-p17-vertical-qa`.

### 4. Horizontal Logic

Apply this check only to a peer set of two or more sibling points. A single sentence, statistic, or quantified fact is not a peer set.

For each actual peer set:

1. Write the candidate parent question.
2. Name the role every peer performs under that parent, such as reasons, controls, findings, evidence, risks, or steps.
3. Keep different topics together when they answer the same parent question and perform the same role. Do not classify peers by their nouns alone.
4. Check mutual exclusivity from the supplied text.
5. Check collective exhaustiveness only when the supplied content or cited domain evidence establishes the relevant universe. A parent claim such as `three controls` asserts completeness; it does not prove completeness. For an excerpt with no defined universe, the required result is `Exhaustiveness is not verifiable from the supplied content.` Do not declare the set complete or invent a missing item.
6. Check whether the set uses one reasoning mode: deductive or inductive.
7. Check whether the parent is an inference that summarizes the children rather than a topic label.

Cite `minto-p96-mece`, `minto-p63-deduction-induction`, or `minto-p5-pyramid-sorting` for each violation.

### 5. Ordering

Assign an order only when the text shows it:

- deductive — each point leads to the next and ends in a conclusion
- chronological — explicit time or process sequence
- structural — explicit parts of a whole or categorical structure
- comparative — explicit ranking criterion or comparison signal

List position alone does not establish comparative order. When no order is discernible, report that fact and judge whether it materially harms comprehension. Do not invent an ordering rationale. Cite `minto-p5-pyramid-sorting` for a violation.

## Control Audit Claims

Every finding must quote or describe evidence in the supplied content and cite a valid source anchor. A comment with no source anchor is an editorial observation, not a Pyramid Principle violation, and receives no severity label.

Audit the supplied content's structure, not the truth of its factual claims. A scoped factual statement such as `all requests received this quarter` is not a MECE violation or a request to prove the data independently.

When the user requests both checks, run `pyramid-source-integrity` and this structural audit independently. Return separate `SOURCE INTEGRITY` and `STRUCTURE` sections. A contradicted or unverified fact is a source-integrity finding, not a Pyramid Principle violation unless the text also contains a demonstrated structural break.

The agent must not:

- copy names, facts, scenarios, or fixes from examples
- invent missing context, evidence, domain facts, or reader knowledge
- declare a peer set exhaustive without evidence defining the relevant universe
- assign a logical order that the text does not show
- add fixes for problems the audit did not find
- rewrite the content unless the user separately requests a rewrite

## Choose the Verdict

Complete all five checks and determine the material findings before writing the verdict.

Choose the verdict from the effect on the reader, not from a finding count:

- **Restructure:** The governing thought is missing or answers the wrong question, or structural breaks prevent the reader from following the central argument.
- **Minor edits:** The central argument and supporting logic remain intact, but localized problems reduce clarity.
- **Share as-is:** The governing thought is clear before support, vertical logic holds, peer groups perform one role, and no material finding would change the reader's understanding.

Verdict and fixes must agree. If the report identifies no material violation and no structural fix, the required verdict is `Share as-is`. `Minor edits` is invalid when `RANKED FIXES` says no structural fix is required; use it only when the report names a localized material finding and its corresponding fix.

Use `Strong checkpoint` only when the missing or false central structure prevents reliable use. Use `Guidance` for a material but localized logic problem. Use `Polish` only for a minor non-blocking improvement.

## Return the Report

Return these headings in order:

1. **OVERALL VERDICT** — Begin with `Share as-is`, `Minor edits`, or `Restructure`, then state the highest-leverage reason.
2. **GOVERNING THOUGHT** — Quote it or write `Not stated`, then state whether it answers the reader question.
3. **SCQA CHECK** — Rate the four elements only when a preamble exists; otherwise write the single `Not applicable` line.
4. **FINDINGS** — List only demonstrated vertical, horizontal, or ordering violations. For each, name the rule type, quote or describe the supplied text, explain the break, and cite the source anchor. When no violation exists, write exactly `None identified.` and stop the section. Do not add positive validation, an inferred order, or a completeness claim.
5. **RANKED FIXES** — List only fixes tied to findings, highest leverage first. If none exist, write `None — no structural fix is required.`

Do not return placeholder brackets, drafting instructions, a rewritten artifact, or a self-check.

## Verify Before Returning

The agent checks the report internally and fixes any failure:

1. Every violation maps to supplied text and a valid source anchor.
2. SCQA is `Not applicable` when no opening preamble exists.
3. Every mixed-kind finding fails the candidate-parent and shared-role tests.
4. No exhaustiveness or ordering claim exceeds the supplied evidence.
5. Every fix maps to a reported finding.
6. No example terminology or unsupported audit claim appears.
7. The response contains only the audit report.

## Source Anchors

- `minto-p5-pyramid-sorting` — pyramid rules and logical orders
- `minto-p7-magical-number-seven` — group-size observation
- `minto-p17-vertical-qa` — vertical question-and-answer logic
- `minto-p22-scqa` — SCQA introduction
- `minto-p63-deduction-induction` — horizontal reasoning modes
- `minto-p96-mece` — mutual exclusivity and collective exhaustiveness

## References

- `references/diagnostic-checklist.md` — detailed rule-indexed checks
- `references/common-violations.md` — violation catalog; examples are patterns only
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-source-integrity/SKILL.md` — separate fact and data validation
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md`
- `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`
