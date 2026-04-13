---
name: pyramid-audit
description: This skill should be used when the user asks to critique, review, diagnose, or improve existing professional writing against Barbara Minto's Pyramid Principle — "audit this doc", "review this email", "is the structure sound", "does this follow MECE", "find structural problems in this memo", "why does this feel buried", "check my exec summary for pyramid violations", "does the deck match the pyramid principle". Produces a rule-by-rule diagnostic report with source-anchor citations and ranked fixes. Does NOT generate or draft new content — for drafting tasks hand off to pyramid-short-form, pyramid-long-form, or pyramid-presentation. Does NOT re-explain the Pyramid Principle itself — that is pyramid-principle-core's job.
version: 0.1.0
---

# Pyramid Audit

## Purpose

This skill takes user-supplied writing — an email, memo, report, presentation outline, or any professional document — and diagnoses it against Barbara Minto's Pyramid Principle rules. It outputs a structured report of violations, severity ratings, source-anchor citations, and ranked fixes. It does not rewrite or draft content. Every finding must be traceable to a rule in the canonical source library.

Load it when the question is "what's wrong with this?" not "write this for me."

## When to Invoke / When NOT to Invoke

**Invoke this skill when:**
- The user supplies existing writing and asks for structural critique
- The user asks whether their document follows the Pyramid Principle or MECE
- The user wants to know why a memo, email, or deck "feels off" or "buries the point"
- The user asks for feedback on structure, logic flow, or intro clarity
- The user asks specifically about SCQA, governing thought, or key-line quality in existing content

**Hand off to sibling skills instead when:**
- The user wants to draft new content from scratch → `pyramid-short-form` (emails, memos) or `pyramid-long-form` (reports, proposals) or `pyramid-presentation` (slide decks)
- The user wants to understand the Pyramid Principle rules before applying them → `pyramid-principle-core`
- The user provides an outline but wants it built out into a full document → `pyramid-long-form` or `pyramid-short-form`

Do not produce an audit without user-supplied content. Do not re-explain the Pyramid Principle framework unless a specific rule is being invoked as grounds for a violation finding.

## Required Input

Before auditing, confirm:

1. **The content to audit** — pasted text, a file path, or a URL the user provides. If none is supplied, ask for it before proceeding.
2. **The reader's question** (optional but valuable) — what question is this document answering for its reader? If the user does not supply this, infer it from the content and state the inference explicitly before auditing: "Inferred reader question: [X]. Proceeding on this basis."
3. **The medium** (optional) — email, memo, report, or deck. If unstated, infer from content signals and state the inference.

Never omit the governing-thought check — it is the most load-bearing check in every audit.

## Audit Procedure

Work through these five steps in order. Do not skip steps or reorder them.

### Step 1 — Identify the Governing Thought

Locate the single most important claim the content makes — the apex of its pyramid. Check:
- Is it stated? If not, mark as **not stated** and flag as a Strong checkpoint.
- Is it stated early (first paragraph, first slide, subject line + opening sentence)? If buried past the midpoint, flag as Buried governing thought.
- Does it directly answer the reader's question (inferred or stated)? If it answers a different question, flag the mismatch.

Extract the governing thought verbatim (or write "not stated") as the first line of the audit report.

### Step 2 — Check the Introduction Against SCQA

Skip this step only if the content is clearly a continuation document with no opening preamble (e.g., a follow-up section, a reply to a prior message that supplies the Situation and Complication). Otherwise, rate each SCQA element as **Pass**, **Weak**, or **Fail**:

- **Situation** — Does the opening establish shared, undisputed context? Pass = present and grounded. Weak = present but contested or padded. Fail = absent or mixed with the Complication.
- **Complication** — Does the intro introduce a change, tension, or problem that makes the Situation unstable? Pass = present and specific. Weak = vague or implied only. Fail = absent (the most common SCQA failure).
- **Question** — Is the question the reader would naturally ask evident from the S and C together? Pass = clearly implied or stated. Weak = ambiguous. Fail = no natural question arises.
- **Answer** — Is the governing thought stated early and explicitly? Pass = stated, answer-first. Weak = stated but delayed. Fail = absent or implied only.

Source authority for SCQA checks: `minto-p22-scqa` (see `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`).

### Step 3 — Check Vertical Logic

Read the content as a question/answer dialogue from the governing thought downward. For each major point:
- What question does this point raise?
- Does the material immediately below it answer that specific question?

Flag violations when:
- Material below a point answers a different question than the point raised
- A point is introduced before the level above has raised its question (information arrives too early)
- A point is asserted but never answered by anything below it (a hanging assertion)

Quote the specific text where the vertical break occurs. Cite `minto-p17-vertical-qa`.

Source authority: `minto-p17-vertical-qa` (see `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`).

### Step 4 — Check Horizontal Logic

For each peer set (any group of items at the same level of the structure):

**MECE check:**
- Are peers mutually exclusive? Flag if two items describe the same underlying phenomenon or if a fact, entity, or event could be correctly placed in more than one peer.
- Are peers collectively exhaustive? Flag if a significant item is missing that the reader would immediately notice given the parent claim.

**Logic-mode check:**
- Is the peer set deductive (each point derives from the prior, ending in a "therefore")? Or inductive (each point is an independent member of a like category)?
- Is only one mode in use? Flag if deductive steps and inductive members appear in the same grouping.

**Parent-label check:**
- Does the parent accurately summarize all children (inference), or does it merely name the topic (container label)?

Source authorities: `minto-p96-mece`, `minto-p63-deduction-induction`, `minto-p5-pyramid-sorting` (see `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`).

### Step 5 — Check Ordering

For each peer set identified in Step 4, determine which of the four valid orders applies:
- **Deductive** — a chain ending in a "therefore" conclusion
- **Chronological** — time sequence, first to last
- **Structural** — parts of a whole, arranged spatially or categorically
- **Comparative** — ranked by a criterion

Flag violations when:
- No discernible order rule is applied (arbitrary sequence)
- Two different ordering principles are mixed within one peer set
- The ordering principle applied does not match the nature of the set (e.g., comparative order applied to a process that should be chronological)

Source authority: `minto-p5-pyramid-sorting` (see `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`).

## Output Format

Produce the audit report in this exact structure. Do not add sections. Do not omit sections. The report opens with the overall verdict — the audit itself must follow the answer-first rule it enforces.

---

**OVERALL VERDICT**
[One sentence: **Share as-is** / **Minor edits** / **Restructure** — and the single highest-leverage reason.]

**GOVERNING THOUGHT**
[Verbatim extraction, or "Not stated"]
[One sentence: does it directly answer the reader's question?]

**SCQA CHECK** *(skip if not an opening document)*
- Situation: [Pass / Weak / Fail] — [explanation]
- Complication: [Pass / Weak / Fail] — [explanation]
- Question: [Pass / Weak / Fail] — [explanation]
- Answer: [Pass / Weak / Fail] — [explanation]

**VERTICAL LOGIC VIOLATIONS**
[List each violation with: the quoted text, the break point, and the anchor cite]
[If none: "None identified."]

**HORIZONTAL LOGIC VIOLATIONS**
[List each violation with: the peer set described, the type of violation, and the anchor cite]
[If none: "None identified."]

**ORDERING ISSUES**
[List each peer set where ordering is arbitrary or wrong, with anchor cite]
[If none: "None identified."]

**TOP 3 RANKED FIXES**
1. [Highest-leverage fix — the single change that unlocks the most structural improvement]
2. [Second fix]
3. [Third fix]

---

**Deriving the Overall Verdict.** The verdict follows mechanically from the diagnostic findings, not editorial judgment:

- **Restructure** — Governing Thought is "Not stated," OR SCQA has two or more Fails, OR any Strong-checkpoint violation appears in vertical/horizontal/ordering sections.
- **Minor edits** — Governing Thought is stated but delayed, OR SCQA has one Fail, OR only Guidance or Polish violations appear.
- **Share as-is** — Governing Thought is answer-first, SCQA is all Pass/Weak with at most one Weak, no Guidance-or-stronger violations.

**Mini-example — shape of a real audit output:**

Content audited: A two-paragraph memo recommending a vendor change. Paragraph 1 describes the current vendor's history and how the relationship developed. Paragraph 2 states "there are several alternatives we should evaluate."

OVERALL VERDICT: **Restructure.** The memo has no governing thought, so the reader finishes it with no position to evaluate or act on.

GOVERNING THOUGHT: Not stated. The memo describes a situation and gestures toward action but never asserts a claim. Strong checkpoint. The reader finishes the opening with no position to evaluate.

SCQA CHECK: Situation: Pass. Complication: Fail — no change or problem is introduced; the status quo is described but no tension is established. Question: Fail — no natural question arises from a static Situation. Answer: Fail — absent.

VERTICAL LOGIC VIOLATIONS: "There are several alternatives we should evaluate" raises "which alternatives, by what criteria?" — nothing below answers it. Hanging assertion. (`minto-p17-vertical-qa`)

HORIZONTAL LOGIC VIOLATIONS: None identified.

ORDERING ISSUES: None identified.

TOP 3 RANKED FIXES: 1. State the governing thought answer-first — the recommended decision, in the opening. 2. Add a Complication — what changed that makes vendor evaluation urgent now? 3. Replace "several alternatives" with a named, structured set of options.

## Severity Ladder

Two primary tiers plus an optional polish tier. The framing is guidance-oriented, not adversarial. "Strong checkpoint" means something the author should address before sharing. "Guidance" means something worth considering but not required.

**Strong checkpoint** — governing thought is false, missing, or answers the wrong question, or SCQA is broken enough that the reader cannot identify what the document argues. Renders the document structurally invalid regardless of how well other elements are written. Address before sharing.

**Guidance** — a logic violation the reader will hit during normal reading: a vertical break, a non-MECE peer set, a mixed logic mode, a container label where an inference belongs. Degrades reader trust and comprehension without making the central argument unintelligible. Worth considering.

**Polish** (optional tier) — a minor issue: a slightly weak Situation, a thin inference label, a minor ordering inconsistency. Document is intelligible, but precision or elegance would improve. Raise polish notes only after Strong checkpoints and Guidance items are listed. Can be omitted if the audit is already actionable.

Do not use "Blocker" as a severity label. Factual descriptions of real blocking conditions (a failing build, a deploy gate) remain appropriate; the preference here is about stylistic severity framing, not about descriptions of actual blockage.

## Source Citation Rule

Every violation cited in the audit report must include the source anchor ID from `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md` that grounds the rule being applied. The valid anchor IDs are:

- `minto-p5-pyramid-sorting` — the three pyramid rules and four logical orders
- `minto-p7-magical-number-seven` — group-size constraints
- `minto-p17-vertical-qa` — vertical question/answer dialogue
- `minto-p22-scqa` — SCQA introduction pattern
- `minto-p63-deduction-induction` — deductive vs. inductive horizontal logic
- `minto-p96-mece` — mutually exclusive, collectively exhaustive

A finding without a source anchor is an editorial suggestion, not a rule violation. Label it as such, and do not assign it a severity level from the severity ladder.

## What NOT to Do

- Do not rewrite the audited content. If the user explicitly requests a rewrite, hand off to the relevant generative skill (`pyramid-short-form`, `pyramid-long-form`, or `pyramid-presentation`).
- Do not invent rules. If something feels weak but no anchor applies, label it an editorial observation — not a rule violation.
- Do not produce an audit without completing Step 1 (governing thought check). Every other finding depends on knowing what the document claims at its apex.
- Do not assign severity ratings to findings that lack anchor citations.
- Do not re-explain the Pyramid Principle framework. Cite the rule in one sentence, cite the anchor, move on. Direct rule questions to `pyramid-principle-core`.

## Additional Resources

- **`references/diagnostic-checklist.md`** — Rule-indexed checklist organized by the five audit steps, with red-flag indicators, severity guidance, and a printable yes/no checklist
- **`references/common-violations.md`** — Catalog of the ten most frequent violations with examples, anchors, fixes, and root-cause explanations

Canonical rule detail for the rules cited in this skill:

```
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md
```

Source anchor definitions:

```
${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md
```
