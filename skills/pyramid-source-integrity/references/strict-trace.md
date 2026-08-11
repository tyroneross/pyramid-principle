# Strict Source Trace

Use this reference only when the task meets a strict-mode trigger in `pyramid-source-integrity`.

## Separate-Pass Protocol

1. Run a source-integrity pre-check on the raw sources.
2. Give the resulting claim packet to the appropriate Pyramid writing skill.
3. Run a separate source-integrity post-check against the draft and original packet.

Use the strongest available verification model for the pre-check and post-check around a smaller drafting model. Use deterministic tools for material calculations. Do not let the smaller model approve its own factual output.

## Claim Packet

Include:

- the requested artifact and reader question;
- a source register with one complete, inspectable record per source ID;
- the supplied decision or recommendation, identified as an instruction rather than evidence of an outcome;
- each allowed fact with a stable claim ID, canonical wording, source ID, exact locator, confidence and reason, scope, numbers, qualifiers, and must-preserve terms;
- each allowed derived value with input claim IDs, formula or query, tool, result, rounding, validation, source trace, confidence, and reason;
- requested non-factual statements; and
- contradicted, unverified, or missing claims that must not appear as facts.

Every source ID must resolve to the source register. Never substitute `same as above`, `user input`, `company data`, `derived`, a bare domain, or a dash.

## Closed Claim Set

When the user says `use only these facts`, mark the packet `closed claim set`.

The artifact may contain only:

- the supplied decision or recommendation;
- supported facts;
- valid derived calculations; and
- limitations required to prevent a misleading statement.

Do not add a benefit, risk, cause, prediction, urgency, implementation activity, next step, or closing invitation. Qualifiers such as `may`, `could`, `likely`, or `we believe` do not make an unsupported prediction usable.

## Trace Draft

For a separate-call workflow, append the relevant claim ID to every factual or evaluative clause. An ID authorizes only the canonical claim with all must-preserve terms; it does not authorize broader scope, extra adjectives, implications, or predictions.

The post-check must:

1. split the draft into individual factual and evaluative claims, including claims carried by adjectives and verbs;
2. map each claim to one supported packet entry or valid derived calculation;
3. preserve entities, population, period, geography, units, qualifiers, and causal strength;
4. restore any missing must-preserve term;
5. delete unmatched language; and
6. remove all claim IDs before returning the artifact.

Preserve the structural pass's headings, order, paragraph boundaries, and bullet format. Correct or delete unsupported wording only; do not regroup, reorder, or reformat the argument.

Return only the corrected artifact unless the user requests the trace or fact-check report.

## Integrity Status

Use one status per claim:

- **Supported:** The source directly supports the claim.
- **Derived:** A reproducible calculation follows from supported inputs.
- **Contradicted:** A source or valid calculation conflicts with the claim.
- **Unverified:** No checked source establishes the claim.
- **Not factual:** The statement is an inference, recommendation, or opinion supplied or requested by the user.

Status records how the evidence relates to the claim. Confidence determines how the writer treats the claim. Do not repeat that action in another field.

## Source Register Records

- **Prompt record:** Current prompt plus numbered fact or exact quotation.
- **File record:** Full path or supplied filename, version/hash/date when available, and locator scheme.
- **Published-source record:** Title, publisher or author, URL, relevant date, and verification date.
- **Dataset record:** Dataset or table identity, version/date, and query or row locator.
- **Calculation record:** Calculation ID, input claim IDs, formula or query, named deterministic tool, result, rounding, and validation.

For a derived value, set status to `Derived`, cap confidence at the weakest required input, and lower it further when the formula, schema, denominator, join, extraction, or validation is uncertain.

## Strict Output Gate

Before returning a packet or trace, correct every failure:

1. Every source ID resolves to one complete source-register record.
2. Every claim has a source ID and exact locator; no source or locator is a dash, blank, or generic label.
3. Every user-supplied source that was not independently checked is `Medium` or lower.
4. Every derived value names a calculation source, input claim IDs, formula or query, deterministic tool, result, rounding, validation, confidence at or below its weakest input, and `Derived` status.
5. No claim repeats the confidence action in a `permitted use` field.

A derived claim's source ID must be its calculation record, such as `CALC-1`; never use a dash, `derived`, or an input source ID. The calculation record then points to the input claim IDs and their evidence.

Use this minimum shape:

```text
SOURCE REGISTER
SRC-1 | complete source identity | locator scheme and date/version
CALC-1 | inputs C1, C2 | formula/query | tool | result | rounding | validation

CLAIMS
C1 | Supported | SRC-1 | exact locator | confidence | reason
D1 | Derived | CALC-1 | inputs and formula | confidence | reason
```
