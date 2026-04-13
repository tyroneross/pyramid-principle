---
name: pyramid-principle-core
description: This skill should be used when the user asks about "pyramid principle", Barbara Minto's Pyramid Principle, or mentions "pyramid structure", "Minto", "SCQA", "situation complication question answer", "governing thought", "MECE", "key line", "deduction vs induction", "vertical and horizontal logic", "answer-first", "top-down structure", or wants the foundational rules of structured communication before drafting. Provides the canonical rule library — idea grouping, summarizing upward, ordering logic (deductive/chronological/structural/comparative), SCQA introductions, question/answer vertical logic, deductive vs inductive horizontal logic. Do NOT use this skill to draft a full artifact — hand off to pyramid-short-form, pyramid-long-form, or pyramid-presentation. Do NOT use for diagnostic review of existing writing — that is pyramid-audit's job.
version: 0.1.0
---

# Pyramid Principle Core

## Purpose

This skill supplies the canonical rule library for Barbara Minto's Pyramid Principle. It establishes shared definitions and structural rules that every other skill in this plugin depends on. It does not produce finished documents or audit existing writing — those functions belong to sibling skills that load these references and apply them to specific formats and tasks.

Load this skill at the start of any structured communication work to orient the session toward the correct framework. Treat its rules as authoritative. If a sibling skill produces output that conflicts with a rule stated here, this skill takes precedence.

Source material: Barbara Minto, *The Pyramid Principle* (2009 revised edition). Verbatim quotes with stable anchor IDs are in `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`.

## When to Invoke

Invoke this skill when:

- The user asks what the Pyramid Principle is, how it works, or why it matters
- The user asks about SCQA, MECE, vertical logic, horizontal logic, deductive vs. inductive reasoning, logical order, or the governing thought
- Any sibling skill encounters a rule question before proceeding
- A new sibling skill is being authored and needs its rule grounding established

Hand off after supplying rules:

- User wants to write a short email or memo → `pyramid-short-form`
- User wants to write a long document, report, or proposal → `pyramid-long-form`
- User wants to build a presentation → `pyramid-presentation`
- User wants existing writing diagnosed → `pyramid-audit`

Do not draft document sections from this skill. State the relevant rules, then explicitly name the next skill to load.

## The Three Rules of Valid Pyramid Groupings

Every valid pyramid satisfies three rules simultaneously. Violating any one of them breaks the structure, regardless of how well the others are observed.

**Rule 1: Ideas at any level summarize the ideas grouped below them.**

The idea at each level is not a label or topic heading — it is a substantive claim that the items below it collectively prove or explain. The apex of the pyramid (the governing thought) is the single most important point, and every subordinate level is a logical answer to the question the level above raises. Nothing appears in the pyramid unless it is either the top-level claim or a direct support for a claim above it.

**Rule 2: Ideas within a grouping are the same kind of thing.**

Peers on the same level share a common question-type they answer. A grouping of reasons, a grouping of steps, a grouping of risks, a grouping of criteria — each is a valid set because every member answers the same question. A grouping that mixes a reason, a step, and a piece of evidence is not a valid set; it has no single parent claim that accurately summarizes all three.

**Rule 3: Ideas within a grouping follow a logical order.**

The sequence of peers is chosen, not arbitrary. One of four valid orders applies to every grouping (see The Four Logical Orders below). The order reveals the logic that unifies the set, which in turn makes the parent claim accurate and testable.

Source grounding: `minto-p5-pyramid-sorting`. Full canonical statement, the magical-number constraint (prefer 3, fine up to ~5, break into categories beyond), a worked flat-to-pyramid example, and failure signals in `references/rules-of-pyramid.md`.

## The Four Logical Orders

Apply exactly one order per peer set, chosen by what that set represents:

- **Deductive order** — a chain of reasoning where each point follows from the prior, ending in a "therefore" conclusion. The parent summarizes the final conclusion that the chain reaches. Use when the set forms an argument or a syllogism.
- **Chronological order** — steps in time sequence from first to last. Use when the set represents a process, action plan, or sequence of events. The parent names the outcome the steps produce.
- **Structural order** — parts of a whole, arranged spatially or categorically (north to south, top to bottom, function to function). Use when describing a system, organization, geography, or structure. The parent names the whole.
- **Comparative order** — items ranked by a criterion (largest to smallest, highest to lowest priority, strongest to weakest case). Use when the set represents options, alternatives, or ranked findings. The parent states the basis of comparison or the leading conclusion from it.

## The Two Relationships Within a Pyramid

Every pyramid contains exactly two relationship types: vertical and horizontal. Both must be valid for the structure to hold.

### Vertical: Question/Answer Dialogue

Every idea in the pyramid raises a question in the reader's mind. The level immediately below answers that question. This is not a metaphor — it is the operational rule for deciding what goes where.

When a point is asserted, the reader automatically asks one of three questions: *Why?* (seeking a justification), *How?* (seeking a method or mechanism), or *Why do you say that?* (seeking evidence). The writer is obligated to answer that specific question on the next line down. If the material on the line below answers a different question, it belongs elsewhere — or not at all. Information that does not answer the reader's current question must wait until that question is raised, which may be several levels down, or never.

Source grounding: `minto-p17-vertical-qa`. The "Why? / How? / Why do you say that?" pattern with worked examples is in `references/vertical-horizontal-logic.md`.

### Horizontal: Deductive or Inductive Logic

Peers on the same level are related to each other by one of two reasoning modes, and the choice of mode determines how the parent claim is formed:

**Deductive** — each point derives from the point before it. The sequence is a chain; remove any link and it breaks. The parent summarizes the final conclusion, resting most heavily on the last point. Example: major premise → minor premise → therefore conclusion.

**Inductive** — each point is an independent member of a like category. No point derives from another. The parent makes an inference about the set as a whole — a claim true given all members but not deducible from any single one.

A peer group uses one mode or the other — never both. Mixing modes breaks the parent claim: a summary that works for a deductive chain will not work for an inductive set.

Source grounding: `minto-p63-deduction-induction`. Worked examples of deductive groupings, inductive groupings, and a mixed-logic violation that illustrates why mixing fails, all in `references/vertical-horizontal-logic.md`.

## SCQA Introductions

Every document, email, or presentation opens with a preamble that establishes common ground before introducing new thinking. Without this, the reader does not know why the governing thought is relevant. The SCQA pattern builds that common ground in four moves:

- **Situation** — context the reader already accepts as true. Facts or recent developments that establish shared starting ground. Brief — the reader should recognize it immediately.
- **Complication** — the change, tension, or problem that makes the Situation unstable. Without a Complication, the reader has no reason to care about the Answer.
- **Question** — the question the Complication raises in the reader's mind. Often implicit. Typical forms: "What should we do?" / "Why is this happening?" / "How can we fix it?"
- **Answer** — the governing thought: the document's central claim. The apex of the pyramid. State it explicitly and early.

The introduction is not the pyramid. It is the preamble that earns the reader's attention. The SCQA contains no argument — it sets up the argument the pyramid makes.

Source grounding: `minto-p22-scqa`. Medium-specific guidance (compressed 2–3 sentence form for short-form vs. full-paragraph treatment for long-form vs. opening slides for presentations), two worked examples (one good, one bad with a rewrite), and common pitfalls are in `references/scqa-pattern.md`.

## MECE Grouping

Every peer set must be Mutually Exclusive and Collectively Exhaustive (MECE). These are not aspirational standards — they are pass/fail tests for every grouping in the pyramid.

**Mutually exclusive** means no item in a peer set belongs in more than one peer. If two items overlap — share the same underlying cause or describe the same phenomenon from different angles — the grouping is broken. Overlap signals the categorization is too coarse or that items need an intermediate level.

**Collectively exhaustive** means the peer set accounts for all relevant instances of the thing grouped. A significant omission invalidates the parent's summary. Exhaustiveness is relative to the question the parent answers — not an absolute requirement to list every possible instance.

**The plural-noun test** — name the peer set with a plural noun before checking it. "Three risks to the Q3 launch schedule" is a valid plural-noun label: it implies a specific question (what risks?), a specific scope (Q3 launch), and a reasonably bounded list. "Three things to consider" is not valid: "things" imposes no constraint, so the set cannot be genuinely exclusive or exhaustive. If the label does not commit to a kind, the grouping cannot be MECE.

**Name the category above the items** — the parent-level idea is the inference from the set, not a container label. "Issues" is a container. "Three execution dependencies that put the Q3 launch at risk" is an inference. The inference is what carries meaning; the container only carries volume.

Source grounding: `minto-p96-mece` (Minto's direct definition of mutually exclusive and collectively exhaustive) and `minto-p7-magical-number-seven` (cognitive basis for categorization and bounded group size). Worked examples for valid vs. broken labels, plural-noun failures, and a validation checklist in `references/mece-grouping.md`.

## Composition for Downstream Skills

Sibling skills load the canonical detail files from this skill's references directory using the plugin root variable. The standard load paths are:

```
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/llm-adaptation.md
```

Verbatim source quotes with stable anchor IDs live at:

```
${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md
```

Every rule stated in a sibling skill must cite the anchor ID from `source-anchors.md` that grounds it. This ensures source traceability across the plugin as it evolves.

## LLM Adaptation Note

The rules in this skill derive directly from Minto's 2009 text. The file `references/llm-adaptation.md` extends those rules into the specific context of LLM-generated output, where distinctive failure modes appear: background-before-answer structure, weak category labels, mixed-kind bullet lists, evidence without inference, and deductive-inductive confusion. That file provides prompt patterns for enforcing pyramid structure in generation tasks and a reusable fillable template skeleton. It is explicitly marked as a modern extension not present in the source.

## Additional Resources

- **`references/rules-of-pyramid.md`** — Canonical statement of all three rules, all four logical orders, magical-number constraint, flat-to-pyramid worked example, and failure signals
- **`references/scqa-pattern.md`** — SCQA definition with verbatim source quote, medium-specific guidance, two worked examples, and common pitfalls
- **`references/vertical-horizontal-logic.md`** — Vertical Q/A dialogue mechanism and horizontal deductive-vs-inductive distinction with verbatim quotes, worked examples, and a mixed-logic violation
- **`references/mece-grouping.md`** — MECE definition, plural-noun test, category-label guidance, worked examples, and a validation checklist
- **`references/llm-adaptation.md`** — Modern extension: LLM failure modes, prompt patterns that enforce pyramid structure, and a reusable template skeleton
