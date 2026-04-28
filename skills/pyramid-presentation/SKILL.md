---
name: pyramid-presentation
description: Use when user asks to structure, storyline, or outline a presentation, deck, slides, ghost deck, or talk using the pyramid principle. Produces slide-by-slide assertion headlines and key lines.
version: 0.1.0
---

# Pyramid Presentation

## Purpose

Produce storyline architecture for slide decks and spoken presentations using Barbara Minto's Pyramid Principle. The primary output is a ghost deck: a slide-by-slide headline track in which every headline is a complete assertion, the logical argument is visible without any slide body content, and the governing thought appears before the evidence. Slide body content, charts, and design come after the ghost deck is sound.

Emphasis throughout: the headline track carries the argument. In prose, transitions and paragraph openers do structural work. In a deck, those disappear — the headline is the only structural signal on each slide. A topic-label headline ("Market Overview") is a structural failure. An assertion headline ("Mid-market expansion drove 84% of Q3 revenue growth") is structural success.

Source grounding: `minto-p5-pyramid-sorting`.

## When to Invoke / When NOT to Invoke

**Invoke when the artifact is:**
- A slide deck of any kind (board deck, strategy deck, investor pitch, research readout, internal proposal, product roadmap, data story)
- A spoken talk or keynote where a slide-by-slide outline is needed
- A "ghost deck" — headlines-only structure before full content is produced
- A presentation storyline or slide flow working from raw material

**Do not invoke — hand off instead:**
- Artifact is a prose report, brief, or proposal with section headings → `pyramid-long-form`. Key distinction: long-form develops argument through paragraphs; presentation compresses paragraphs into single assertion headlines.
- Artifact is an email, memo, or one-pager under ~500 words → `pyramid-short-form`
- User has a deck and wants structural critique of existing slides → `pyramid-audit`
- User wants the foundational rules explained before building → `pyramid-principle-core`

The critical boundary with `pyramid-long-form`: long-form carries argument through paragraphs; a deck carries argument through the headline track alone. Every slide headline must assert its point completely — body, chart, and bullets are evidence, not the argument.

## Why Presentations Need Pyramid Discipline More, Not Less

Prose can hide structural weakness behind transitions. A deck cannot. When slides remove connective tissue, the logical structure must be visible in the headline track itself. If a reader can read only slide titles and not reconstruct the argument, the deck is broken at the structural level.

The mechanism is the vertical question/answer dialogue: every headline asserts a claim that raises a question in the reader's mind, and the next section answers that question. (`minto-p17-vertical-qa`) A topic-label headline raises no question — it invites the audience to decide what the slide means. That is the writer's job.

## The Ghost-Deck-First Workflow

Build every deck in three passes. Do not move to Pass 2 until Pass 1 produces a headline track that tells the complete argument without any body content.

### Pass 1 — Storyline (Headlines Only)

Write every slide headline as a single assertion sentence. The headline track alone — read top to bottom — must tell the complete argument. No slide body, no chart stubs, no bullets. If the argument is unclear from headlines alone, the structure is wrong.

For each headline, confirm: Is this a claim the audience can agree or disagree with? If yes, it is an assertion. If it is only a topic ("Competitive Landscape", "Q3 Results", "Options Analysis"), it is a label — rewrite it.

### Pass 2 — Evidence Placement

Under each headline, identify the one chart, table, quote, or diagram that directly supports it. One point per slide. If a slide requires two charts to make its point, the point is probably two slides. If a slide has a chart with no assertable headline, the slide has no argument — generate the assertion or cut the slide.

Charts and tables are evidence, not arguments. The headline names the inference; the chart validates it. A chart with no claim headline forces the audience to do the writer's job.

### Pass 3 — Transitions and Section Intros

Add section divider slides that restate the upcoming section's point in one assertion sentence. Add closing slides that restate the governing thought. No agenda slides after the opening — the section divider is the agenda. Check that dividers connect prior and upcoming sections ("We've established that X. The question is now why Y.") to maintain narrative continuity.

## The Storyline Architecture

Every deck follows a four-zone structure. Adjust slide counts for length; do not omit zones.

### Opening (1–3 Slides): Compressed SCQA → Governing Thought

Map the SCQA pattern across opening slides, not prose. A standard opening pattern:

- **Slide 1 — Situation:** The state of affairs the audience already knows and accepts. Brief. No new claims.
- **Slide 2 — Complication:** What changed, what's wrong, or what the Situation makes insufficient. This slide creates urgency.
- **Slide 3 — Governing Thought:** The Answer stated explicitly as the slide headline before any supporting evidence. This is the most important slide in the deck.

The Question is often implicit. Do not bury the governing thought past Slide 3. Short decks (under 10 slides) may compress the opening to 1–2 slides.

Full SCQA treatment, including the presentation-specific pattern, is in `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md`. (`minto-p22-scqa`)

### Key Line (1 Slide): The Argument's Table of Contents

One slide listing the 3–5 supporting claims that together prove the governing thought. This slide is not a table of contents for the file — it is the table of contents for the argument. Each bullet is an asserted point (abbreviated), not a section title.

The key-line points must be MECE: no two points describe the same underlying claim, and the set together fully supports the governing thought. Apply the plural-noun test before writing: name the set with a specific plural noun. `minto-p96-mece`

### Body (One Section per Key-Line Point)

Each key-line point becomes one section. Each section opens with a divider slide asserting the point in full. The divider is followed by 2–5 support slides, each with its own assertion headline and one piece of evidence.

Choose one logical order (deductive, chronological, structural, or comparative) and hold it across all slides in the section. (`minto-p63-deduction-induction`)

### Closing (1–2 Slides): Governing Thought Restated, Then the Ask

Restate the governing thought in the second-to-last slide — not as a summary of sections, but as the original central claim with the confidence that the evidence now earns. The final slide states the specific decision, action, or commitment the deck requires from the audience. No "Questions?" slide as the last substantive slide — the governing thought is the last argument the audience sees.

## Assertion-Style Headlines

The single most important rule in deck construction. Headlines must state the point, not name the topic.

**Topic label (failure):** "Q3 Revenue"
**Assertion (correct):** "Q3 revenue grew 12%, driven entirely by mid-market expansion"

**Topic label (failure):** "Customer Research Findings"
**Assertion (correct):** "Customers abandon onboarding at step 3 due to mandatory SSO configuration"

**Topic label (failure):** "Infrastructure Proposal"
**Assertion (correct):** "Migrating to multi-region infrastructure eliminates the single point of failure causing 94% of downtime incidents"

A topic-label headline makes no claim — no cognitive anchor, no basis to agree or disagree, no logical connection to the slide before it.

Full rules and before/after examples: `references/slide-headline-rules.md`

## One Point per Slide

Each slide makes exactly one assertion:

- **Two points → split.** Each earns its own evidence and logical position in the track.
- **No assertable point → cut or convert.** Relabel as a divider or cut as structural bloat.
- **Pure transition sentence → not a slide.** Absorb it into the preceding divider.

(`minto-p7-magical-number-seven`)

## Data-Story Specific Guidance

When the deck is primarily data-driven, three additional rules apply:

**Order charts by the question they answer, not by data collection order.** The logical order of the argument determines chart sequence — not the order in which data was gathered.

**Group charts into sections whose divider slides name the inference.** "Data" and "Analysis" are topic labels. "Three signals show platform engagement peaked in Q2 and is now declining" is an assertion.

**Use comparative or structural order for data sections; chronological only when the story is change over time.** Do not default to chronological — confirm it matches the logical argument.

## Section Transitions

Each divider slide closes the prior section and opens the next: reference the prior section's point in one phrase ("We've established X..."), then introduce the next section's point as an assertion ("...which means Y"). No standalone "Agenda" slides after the opening — section dividers are the agenda.

## Self-Check Before Returning

Run all seven gates before returning any ghost deck or full storyline. Any failure → fix structure before continuing. For a full structural audit of an existing deck, direct to `pyramid-audit`.

1. **Headline-only test:** Read only the slide headlines, top to bottom. Does the argument come through completely without any body content? If not, headlines are topic labels, not assertions.
2. **Opening establishes SCQA and states governing thought:** Does the opening compress Situation and Complication, and state the Answer explicitly before evidence begins?
3. **Every headline is an assertion, not a topic label:** Is every slide title a claim the audience can agree or disagree with? Zero topic labels.
4. **Every headline is under 16 words (12 ideal):** Count words in each headline. If any exceeds 16, split the claim across two slides or trim. Length discipline is load-bearing — long headlines signal unseparated points. See `references/slide-headline-rules.md` for the length rule.
5. **Key-line points are MECE and same-kind:** Do the supporting claims pass the plural-noun test? Do any two points overlap? Does the set collectively prove the governing thought?
6. **Each section opens with a divider asserting the point:** Does every body section begin with a divider slide that states the section's claim as a complete assertion?
7. **Closing restates governing thought, not section summaries:** Does the closing restate the apex claim — not "in summary, we covered X, Y, and Z"?

## Common Presentation Mistakes

**Topic-label headlines.** "Market Overview," "Team," "Next Steps" — these are file tabs, not arguments. Replace every one before presenting.

**Agenda slide that doesn't match the key line.** An agenda slide listing section names ("Background," "Analysis," "Recommendations") that don't match the asserted key-line points means the deck has two competing structures. Cut the agenda slide; let the key-line slide do the work.

**Evidence sections without claim headlines.** A section titled "Supporting Data" or "Evidence" with charts but no assertion headlines. Each chart must be under a headline that makes the claim the chart supports.

**Mixing chronological status, findings, and recommendations in one section.** Three logical modes in one section produce incoherence. Keep them in separate sections with explicit dividers.

**Concluding with "Questions?" instead of the governing thought.** The last thing the audience sees should be the central claim — the answer to the question that opened the deck. "Questions?" as the final slide erases the argument just as it should be landing.

## Additional Resources

- **`references/storyline-patterns.md`** — Six deck-type templates with slide-by-slide skeletons, logic-mode guidance, and worked examples
- **`references/slide-headline-rules.md`** — Deep dive on assertion-style headlines: grammar, length, verb strength, specificity, and 10 before/after rewrites

Canonical rule detail:

```
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md
${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md
```
