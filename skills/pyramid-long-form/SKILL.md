---
name: pyramid-long-form
description: Use when user asks to structure or draft a report, brief, proposal, research writeup, strategy document, whitepaper, or other multi-section professional writing using the Pyramid Principle.
version: 0.1.0
---

# Pyramid Long-Form

## Purpose

Structure or draft a multi-section professional document. Load `pyramid-principle-core` first. Its operating contract and structural rules take precedence.

This skill handles documents that require developed sections or usually exceed about 500 words. It does not audit existing writing or produce slide storylines.

## Route the Request

Use this skill for reports, briefs, proposals, research writeups, decision documents, strategy documents, and whitepapers.

Hand off when:

- the artifact is an email, Slack update, executive summary, or one-pager → `pyramid-short-form`
- the artifact is a deck or presentation storyline → `pyramid-presentation`
- the user wants existing writing diagnosed → `pyramid-audit`
- the user wants the framework explained → `pyramid-principle-core`

## Identify the Inputs

Before structuring the document, the agent identifies:

1. **Reader question:** What must the document answer?
2. **Governing thought:** Which decision, recommendation, or finding did the user supply?
3. **Evidence:** Which supplied facts and cited sources may support the governing thought?
4. **Requested depth:** Outline, detailed outline, section draft, or full document?
5. **Constraints:** Audience, length, tone, required sections, sensitivity, and citation format.

The agent asks a question only when a missing answer would materially change the document and the supplied evidence does not support a safe choice.

## Return the Requested Depth

- **Outline:** Return the title, actual decision or governing claim, section claims, and nested source-backed supports. The eventual document word budget does not set the outline's length. Do not draft body prose or output framework commentary.
- **Detailed outline:** Add subsection claims, evidence placement, and source notes.
- **Section draft:** Draft only the requested section and preserve its position in the document logic.
- **Full document:** Draft the complete document after the outline passes the internal checks.

Do not output SCQA, key-line, reasoning-mode, assumption, or self-check labels unless the user requests an annotated structure.

When the user requests a source-bound outline or says to use only supplied facts:

- include only the supplied decision, source-backed section claims, supplied facts, and explicit evidence limits;
- omit generic introduction, implementation, expected-outcome, and conclusion sections unless the user requests them and the source supplies their content;
- do not add a section merely because it is common in that document type;
- state an unevidenced expected result as `not established by the supplied evidence`, not as a prediction.

The source-bound outline starts with the actual title and decision sentence, then uses only asserted section headings with their supplied facts. It may end with one `Evidence limits` section. It must not print the drafting labels `Title`, `Governing Thought`, `Fact`, `Inference`, `Decision`, `Rationale`, or `End of Outline`.

Unless the user supplies their content, the agent must not create sections named or serving as `Introduction`, `Implementation`, `Expected Outcomes`, `Benefits`, `Next Steps`, or `Conclusion`.

If the supplied decision includes an intervention whose effect has not been measured, state the intervention in the decision sentence only. Do not create a section that predicts its benefits. Put the missing outcome evidence under `Evidence limits`.

Use this final syntax for a source-bound outline:

- first line: a Markdown `#` title with no `Title` label;
- second paragraph: the supplied decision sentence with no `Governing Thought`, `Governing Claim`, or `Decision` label;
- remaining `##` sections: source-backed claims and their supplied facts;
- optional final `## Evidence limits` section;
- stop after the final section without an `End of Outline` label.

## Build the Architecture

The agent completes the architecture before drafting prose:

1. **Write the governing thought.** Use the decision, recommendation, or finding the user supplied. Do not replace it with a stronger outcome claim.
2. **Add only necessary introduction context.** Include the minimum Situation or Complication the reader needs, then state the governing thought before the document body. When the context is shared, begin with the governing thought. (`minto-p22-scqa`)
3. **Select section claims.** Use the distinct claims required to support the governing thought. Do not add or remove sections to reach a preferred count.
4. **Test each peer set.** Every section or subsection at one level answers the same parent question and performs the same logical role. Different topics may remain peers when one accurate role label describes all of them. (`minto-p96-mece`)
5. **Choose one order per peer set.** Use deductive, chronological, structural, or comparative order only when the material shows that order. (`minto-p5-pyramid-sorting`, `minto-p63-deduction-induction`)
6. **Place evidence under the claim it supports.** Do not create a separate background or data section when the material belongs under a specific claim.
7. **Nest only when needed.** Add a lower level when a section claim requires multiple distinct supports. Do not create depth to make the outline look complete.

## Draft the Prose

When the user requests prose, the agent:

1. opens each section with the claim that section establishes;
2. places source-backed evidence and explanation beneath that claim;
3. keeps each paragraph tied to one outline node;
4. uses transitions only when they clarify the logical relationship between peer sections;
5. revises the architecture when new evidence changes the governing thought instead of writing around an outdated outline;
6. concludes by restating the governing thought only when the document needs a conclusion, without recapping every section.

## Control Unsupported Content

Every factual statement, heading, and support point must map to supplied evidence or a cited source.

The agent must not:

- turn a recommendation into a promised outcome
- convert correlation into cause
- infer savings, delays, risk, compliance, reliability, success, or improvement without supporting evidence
- attribute an aggregate metric to one subgroup or activity unless the source makes that allocation
- add implementation details, staffing needs, timelines, or expected results to complete a template
- copy names, facts, terminology, scenarios, or conclusions from examples

When the user requests an interpretation or recommendation, distinguish it from supplied fact and identify the evidence that supports it. Qualify the claim when the evidence suggests but does not establish the conclusion.

## Format the Outline

For an unannotated outline:

- state the actual governing claim near the top without labeling it `Governing Thought`;
- use asserted section headings, not topic labels;
- place only the facts or qualified interpretations that support each heading beneath it;
- state a source limitation when an aggregate fact cannot support a narrower attribution;
- include an ask, next step, or expected result only when supplied or requested.

For a source-bound outline, stop after the final source-backed section. Do not add prose to approach the eventual document word budget.

## Verify Before Returning

The agent checks the architecture and requested artifact internally and fixes any failure:

1. The supplied governing thought answers the reader question before body support.
2. Every heading is a claim supported by material beneath it.
3. Every factual statement maps to supplied evidence or a cited source.
4. No claim is stronger or more specific than its evidence.
5. Every peer set answers one parent question, performs one role, and uses one logical order.
6. The outline retains every material support without forcing a preferred count or depth.
7. No aggregate metric is attributed to a component without evidence.
8. No example terminology, unsupported content, framework labels, or self-check appears.
9. The response matches the requested depth and contains only the requested artifact.

## References

- `references/report-skeleton.md` — detailed document patterns; use structure only
- `references/key-line-examples.md` — grouping examples; never use their facts as task evidence
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/vertical-horizontal-logic.md`
- `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md`
- `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`
