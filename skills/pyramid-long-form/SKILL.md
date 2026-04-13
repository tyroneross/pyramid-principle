---
name: pyramid-long-form
description: This skill should be used when the user asks to outline, draft, or restructure a long professional document — "structure this report", "outline a brief", "build the argument for a 20-page doc", "draft a research writeup", "organize this proposal", "write a strategy doc", "structure a whitepaper", "put this analysis in pyramid form", "key line for a report". Produces a full pyramid outline with nested key lines, section headings that assert their points, and explicit support trees from introduction through conclusion. Do NOT use this skill for short communication under ~500 words (hand off to pyramid-short-form), for slide decks (pyramid-presentation), or for critiquing existing content (pyramid-audit).
version: 0.1.0
---

# Pyramid Long-Form

## Purpose

Generate full-document structural scaffolding for long-form professional writing using Barbara Minto's Pyramid Principle. The primary output of this skill is the pyramid outline — a hierarchy of asserted key-line points, section headings, and nested sub-key-lines — before any extended prose is written. Prose drafting follows the scaffold; never the reverse.

Target artifact length: 500–20,000+ words. Document types: reports, briefs, proposals, research writeups, decision memos, strategy documents, whitepapers, and any other multi-section professional writing with section headings. The emphasis throughout is structure-first: a structurally sound skeleton produces coherent prose; prose written without a skeleton rarely restructures into one.

Source grounding for the foundational claim: `minto-p5-pyramid-sorting`.

## When to Invoke / When NOT to Invoke

**Invoke when the artifact is:**
- A formal report (analytical, findings-based, or periodic)
- A strategic proposal or business case
- A research synthesis or literature-grounded writeup
- A decision memo requiring multiple headed sections
- A strategy document or whitepaper
- Any document where the reader needs multiple headed sections and the argument runs longer than 500 words

**Do not invoke — hand off instead:**
- Output is ≤500 words or fits on one page → `pyramid-short-form`
- Output is a slide deck or presentation → `pyramid-presentation`
- User supplied existing writing and wants structural critique → `pyramid-audit`
- User wants the foundational rules explained before drafting → `pyramid-principle-core`

**The heuristic:** If the artifact requires more than one headed section, or if the argument requires multiple independent logical threads developed in sequence, it belongs in long-form.

## The Two-Pass Workflow

Long-form writing proceeds in two distinct passes. Do not merge them. (`minto-p5-pyramid-sorting`, `minto-p17-vertical-qa`)

**Pass 1 — Architecture:** Identify the reader's question, write the governing thought, build the key line, nest supports to the required depth. No prose beyond single asserted sentences. Output is a complete outline: a hierarchy of claims from governing thought to leaves, every node an asserted point.

**Pass 2 — Prose population:** Write section openers stating the point first. Add evidence and context below it. Anchor every paragraph to a Pass 1 outline node. Transitions name the prior peer's point and introduce the next by its role in the key line. If new information found during writing invalidates the governing thought, return to Pass 1 and revise the outline — do not revise prose around an outdated structure.

## Intake — Clarify Before Pass 1

Confirm these inputs before building the pyramid.

- **Reader's question** — one sentence. "What should we do about the platform migration?" is a question. "The migration situation" is not.
- **Document type** — report, brief, proposal, research synthesis, strategy doc, whitepaper, or decision memo. Determines which skeleton variant applies (see `references/report-skeleton.md`).
- **Length budget** — word count or page target. Determines pyramid depth and key-line width.
- **Audience seniority** — determines how much shared context the SCQA can assume.
- **Decision, information, or persuasion** — what the document must do for its reader. Determines the key-line logic mode.
- **Evidence on hand** — what data and analysis exist. Determines what the pyramid can claim at the leaf level.
- **Approval chain** — who reviews before the final reader. Affects governing thought specificity and evidence thresholds.

Tag any inference before proceeding: "TAG:ASSUMED — reader's question is X."

## Pass 1 — Building the Pyramid

Execute these steps in order.

**Step 1: Write the reader's question in one sentence.** Drafting anchor — may not appear in the final document but constrains every structural decision.

**Step 2: Write the governing thought in one declarative sentence.** The direct answer to the reader's question. Specific enough to be disputed. The apex: everything in the document either introduces it (SCQA) or supports it (pyramid). (`minto-p22-scqa`)

**Step 3: Draft the SCQA introduction.** Four moves: Situation (shared context the reader already accepts), Complication (what changed or what problem exists), Question (explicit or implicit), Answer (the governing thought, stated as the final sentence of the introduction). For long-form, each move earns its own sentence or short paragraph; the introduction runs no longer than one page.

Full SCQA treatment — pitfalls, medium-specific guidance, worked examples — is in `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md`. (`minto-p22-scqa`)

**Step 4: Draft the 3–5 key-line points.** Each point answers the question the governing thought raises ("Why?" / "How?" / "Why do you say that?"). Apply the plural-noun test before writing: name the set with a specific plural noun. Run MECE checks: no two points describe the same phenomenon; the set accounts for all significant support the governing thought requires.

MECE validation checklist: `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md`. (`minto-p96-mece`)

**Step 5: Choose one logical order for the key line and hold it.** Deductive, chronological, structural, or comparative — determined by what the set represents, not preference. State which order applies and why. For deductive key lines, the governing thought is the "therefore" conclusion. For inductive key lines, the governing thought is the inference from the pattern.

Deductive vs. inductive guidance: `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md`. (`minto-p63-deduction-induction`)

**Step 6: Draft each key-line point's sub-key-line (3–5 points).** State the key-line point, ask what question it raises, write the sub-points that answer that exact question. Each sub-point is a complete asserted sentence. Apply plural-noun test and MECE checks at each sub-key-line independently.

Q/A dialogue mechanism: `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md`. (`minto-p17-vertical-qa`)

**Step 7: Repeat for additional levels as needed.** Most reports need two levels below the governing thought. Whitepapers may need three. Four levels is the practical maximum. Stop when each leaf satisfies: a skeptical reader who accepts it would have no further logical question the document is obligated to answer. A leaf with no such question left open is complete; a leaf that can be removed without leaving a gap is bloat.

## Pass 2 — Populating with Prose

**Open each section with the point it proves.** First sentence states the claim; evidence and context follow. Never open with background.

**Headings assert, not describe.** "Three factors slow adoption" asserts a finding. "Adoption factors" describes a topic. Every heading is assertive, specific, and falsifiable. (`minto-p5-pyramid-sorting`; heading grammar patterns in `references/report-skeleton.md`; ordering rationale in `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md`)

**Transitions name the prior point and introduce the next.** A single sentence between peer sections recalls the prior point and positions the next by its role in the key line.

**Evidence sits under the point it supports.** Never in a separate "data" or "background" section. Evidence placed before the claim it supports inverts the pyramid.

**Conclude with a restatement of the governing thought.** Not a section-by-section recap. One sentence or short paragraph restating the apex claim in light of the evidence presented.

## Section-Intro Formula

Every section with sub-sections opens with an intro paragraph (30–60 words):

1. Restate the parent question in one line.
2. State the answer this section gives — asserted in one declarative sentence.
3. Preview the peer points if sub-sections follow — name them in one compressed sentence.

## Heading Conventions

**Assert the point.** Headings are claims, not labels.

**Parallel grammar across peers.** All noun phrases, or all complete sentences — do not mix forms within a peer set.

**Concise.** Assertion headings run 4–10 words. Heading grammar patterns with parallel/non-parallel examples are in `references/report-skeleton.md`. Ordering rationale: `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md`.

## Length Budget Guidance

| Target length | Key-line points | Pyramid depth | Headings |
|---|---|---|---|
| ~500 words | 2–3 | 1 level | 2–3 |
| ~2,000 words | 3–4 | 2 levels | 6–12 |
| ~10,000+ words | 3–5 (prefer 3–4) | 3–4 levels | 20–40+ |

For documents over 2,000 words, add an executive summary restating the governing thought and compressed key line before the introduction.

## Self-Check Before Returning

Run all six gates before returning Pass 1 output or Pass 2 prose to the user. Any failure requires revision before continuing.

1. **Governing thought in the first paragraph?** If the Answer appears after the first paragraph of the document body, the structure is inverted.
2. **SCQA introduction completes before the key line begins?** The introduction establishes Situation, Complication, and governs thought before any supporting argument appears.
3. **Every key-line point answers the question the governing thought raises?** Apply the vertical Q/A dialogue: state the governing thought, ask what question it raises, confirm each key-line point answers that exact question — not a related or adjacent one.
4. **Peer sets MECE, same-kind, and consistent logic mode?** Apply the plural-noun test. Confirm no two peers overlap. Confirm the parent claim accurately summarizes all peers using a single reasoning mode (deductive or inductive, not both). (`minto-p96-mece`, `minto-p63-deduction-induction`)
5. **One ordering rule applied consistently across the key line?** Name the ordering rule used (deductive / chronological / structural / comparative). Confirm every peer in the key line belongs in that order — no stray points from a different order type.
6. **Would cutting any leaf leave a question unanswered?** Read each leaf and ask: "If this were removed, would the reader have a logical question that the document is now obligated to answer?" If no, the leaf is bloat and should be cut.

Any gate that fails → revise the outline before writing more prose. For a full structural audit of existing writing, direct to `pyramid-audit`.

## Common Long-Form Mistakes

**Opening with background instead of SCQA.** The introduction spans two pages of context and history before stating what changed or what the document argues. The reader finishes the introduction not knowing the governing thought. Fix: build the SCQA explicitly, with Complication and Answer as the final moves. (`minto-p22-scqa`)

**Process description substituting for findings.** "We conducted 24 interviews, analyzed three years of sales data, and ran a competitive benchmarking study." This describes the work, not what the work found. Findings answer the reader's question; process description does not. The key line should be asserted findings, not research methods.

**Evidence dumped in appendix-style sections.** A "Data" or "Background" or "Evidence" section that precedes the argument, or sits alongside it as a peer, inverts the pyramid. Evidence belongs directly under the specific point it supports, at the level where the reader needs it to accept that point.

**Topic-led section headings.** "Market conditions," "Team capacity," "Financial overview" — these are containers. Each heading should assert the point that section proves: "Market contraction reduces total addressable revenue by 18%." `minto-p5-pyramid-sorting`

**Conclusion as document summary.** Recapping all section points in the conclusion restates what the reader already read. The conclusion's job is to restate the governing thought — the apex claim — in light of the evidence the pyramid provided. One well-chosen sentence does this better than a bulleted recap.

## Additional Resources

- **`references/report-skeleton.md`** — Universal document skeleton, five document-type variants, section-intro paragraph templates, and heading grammar patterns with parallel/non-parallel examples
- **`references/key-line-examples.md`** — Three fully worked key-line examples at decreasing abstraction: Q3 product strategy (inductive), infrastructure migration proposal (chronological), customer research synthesis (structural/comparative)

Canonical rule detail:

```
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md
${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md
```
