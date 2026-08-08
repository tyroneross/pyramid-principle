---
name: pyramid-presentation
description: Use when user asks to structure, storyline, or outline a presentation, deck, slides, ghost deck, or talk using the pyramid principle. Produces slide-by-slide assertion headlines.
version: 0.1.0
---

# Pyramid Presentation

## Purpose

Produce a presentation storyline whose assertion headlines carry the argument. Load `pyramid-principle-core` first. Its operating contract and structural rules take precedence.

This skill produces deck structure. It does not design slides or audit an existing deck.

## Route the Request

Use this skill for slide decks, talks, ghost decks, presentation storylines, and slide-flow requests.

Hand off when:

- the artifact is a prose report or multi-section document → `pyramid-long-form`
- the artifact is an email, memo, or one-pager → `pyramid-short-form`
- the user wants an existing deck diagnosed → `pyramid-audit`
- the user wants the framework explained → `pyramid-principle-core`

## Identify the Inputs

Before drafting, the agent identifies:

1. **Audience question:** What must the audience understand or decide?
2. **Governing thought:** Which decision, recommendation, or finding did the user supply?
3. **Evidence:** Which supplied facts support that governing thought?
4. **Shared context:** What does the audience already know?
5. **Requested depth:** Headlines only, evidence placement, transitions, or a fuller outline?

The agent asks a question only when a missing answer would materially change the storyline and the supplied material does not support a safe choice.

## Return the Requested Depth

- **Ghost deck or headlines-only request:** Return only numbered lines in the form `Slide [number] — [assertion headline]`.
- **Evidence-placement request:** Add one source-backed chart, table, quote, diagram, or fact under the headline it supports.
- **Fuller outline request:** Add source-backed evidence placement and requested transitions. Do not add design, speaker notes, or framework commentary unless requested.

The agent runs structural checks internally. It does not output SCQA labels, zone names, section-analysis headings, or self-check results.

## Build the Headline Track

The agent performs these steps in order:

1. **State the governing thought before evidence.** Use the decision, recommendation, or finding the user supplied. When the audience already has the context, make it the first substantive headline. When the audience needs context, include only the minimum Situation or Complication required to understand it first. No universal slide number applies. (`minto-p22-scqa`)
2. **Preserve the supplied claim.** Do not replace a supplied decision with a stronger promise about what it will achieve. Do not turn correlation into cause or evidence into an unproven outcome.
3. **Write support headlines from evidence.** Every support headline states a fact the source supplies or a qualified inference the evidence establishes. Remove any headline that lacks support.
4. **Group same-role peers.** Every peer headline answers the same parent question and performs the same logical role. Group reasons with reasons, findings with findings, evidence with evidence, and steps with steps. Different topics may remain peers when one accurate role label describes all of them. (`minto-p96-mece`)
5. **Choose one logical order per peer set.** Use deductive, chronological, structural, or comparative order according to what the set represents. Do not mix order rules within one set. (`minto-p5-pyramid-sorting`, `minto-p63-deduction-induction`)
6. **Make one point per slide.** Each headline states one claim the audience can agree or disagree with. Split only when a headline makes more than one point; do not split solely to meet a word limit.
7. **Use the necessary number of slides.** Do not add slides to reach a preferred count or remove supported points to meet a limit. Regroup when a flat sequence becomes difficult to follow.

## Control Unsupported Content

The agent maps every headline to supplied evidence or a cited source.

Unless the supplied material establishes it, the agent must not add:

- a cause, benefit, risk, trend, implication, or predicted result
- a metric, timeline, resource need, or implementation detail
- a claim that evidence is sufficient, representative, reliable, or decisive

The agent treats examples in `references/` as structural patterns. It does not copy their names, facts, slide counts, scenarios, or conclusions into the deck.

## Structure a Full Storyline

When the user requests more than a ghost deck, use these logical functions as needed:

- **Opening:** minimum required context, then the governing thought before evidence
- **Key line:** the distinct same-role claims that support the governing thought
- **Body:** one section per key-line claim, with evidence placed under the assertion it supports
- **Closing:** the governing thought restated with only the confidence the evidence earns; include an ask only when supplied or requested

These functions do not require fixed slide positions or counts.

## Verify Before Returning

The agent checks the storyline internally and fixes any failure:

1. The supplied governing thought appears before supporting evidence; any preceding context is necessary.
2. Every headline maps to supplied evidence or a cited source.
3. No headline is stronger than its evidence.
4. Every peer set answers one parent question and performs one role.
5. The headline track remains understandable without slide bodies.
6. Each slide makes one point, and the sequence uses a valid logical order.
7. No example terminology, unsupported content, framework labels, or self-check appears.
8. The response matches the requested depth and contains no extra drafting commentary.

## References

- `references/storyline-patterns.md` — deck patterns; slide numbers and facts are illustrative only
- `references/slide-headline-rules.md` — assertion-headline diagnostics and examples
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md`
- `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`
