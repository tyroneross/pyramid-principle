---
name: pyramid-source-integrity
description: Use when a task requires fact checking, source validation, calculation checks, metric handling, or a source-bound claim set before Pyramid Principle structuring.
version: 0.1.0
---

# Pyramid Source Integrity

## Purpose

Decide which claims and data are safe to use before another skill builds the structure or storyline. Run it again after drafting to check the finished artifact.

This skill does not choose the governing thought, group claims, order sections, or create a storyline. Those responsibilities belong to `pyramid-principle-core` and its drafting skills.

## Separate-Pass Composition Protocol

Keep source integrity and structure as separate operations:

1. **Pre-check:** Run this skill on the raw sources and create an internal claim packet.
2. **Structure:** Give the claim packet to the appropriate Pyramid drafting skill. That skill builds from the packet, not from assumptions or common document patterns.
3. **Post-check:** Run this skill on the finished draft and the original claim packet. Correct or delete any claim that fails the packet, then return only the corrected artifact.

For smaller drafting models and strict `use only these facts` work, run these as three separate model calls. Use the strongest available verification model for the pre-check and post-check, and use deterministic calculation or research tools when applicable. Do not let the same smaller model draft and approve its own factual claims.

The internal claim packet contains:

- the requested artifact and reader question;
- the supplied decision or recommendation, identified as an instruction rather than evidence of an outcome;
- allowed facts, each with a stable claim ID, canonical wording, source, scope, numbers, qualifiers, and must-preserve terms;
- allowed derived values, each with a formula and rounding;
- requested non-factual statements that may appear; and
- contradicted, unverified, or missing claims that must not appear as facts.

When the user says `use only these facts`, mark the packet `closed claim set`. In a closed claim set, every factual or evaluative clause not explicitly listed is prohibited. Smaller models copy each allowed fact's canonical wording. Other models may revise syntax only when every must-preserve entity, population, period, unit, denominator, qualifier, and degree of certainty remains explicit.

For a separate-call workflow, the structural pass creates a trace draft by appending the relevant claim ID to each factual or evaluative clause. The post-check compares the whole clause with the canonical claim and must-preserve terms; an ID does not authorize missing scope, extra adjectives, implications, or predictions. It restores missing required terms, deletes unmatched language, and removes all IDs before returning the artifact.

Do not show the packet or claim IDs in the final artifact. The post-check may repair or remove claims, numbers, and qualifiers; it must not redesign the structure or add a new storyline.

## Non-Negotiable Output Gate

Run this gate immediately before returning any source-bound artifact:

1. Split the draft into individual factual and evaluative claims, including claims carried by adjectives and verbs.
2. Map each claim to one supported ledger entry or one valid derived calculation.
3. Delete any claim that has no match. Adding `may`, `could`, `likely`, or `we believe` does not make an unsupported prediction usable.
4. Preserve the source's entities, population, period, geography, units, qualifiers, and causal strength. Do not broaden a sample, rename an entity, promote a contributing factor to a primary cause, or turn a resource count into a feasibility judgment.
5. Treat every adjective that asserts importance, scale, effort, risk, quality, or certainty as a claim that requires source support.
6. Treat every verb that asserts an intervention's effect, alignment, prevention, or result as a claim that requires source support.

When the user says `use only these facts`, the artifact may contain only the supplied decision, Supported facts, and Derived calculations. It must not add a benefit, risk, cause, prediction, urgency, implementation activity, next step, or closing invitation. A supplied recommendation authorizes the action statement; it does not authorize a claim about what the action will achieve.

For a composition post-check, return only the corrected artifact. Return the fact-check report later in this skill only when the user explicitly asks to see a fact check.

## Route the Request

Use this skill when the user asks to:

- use only supplied facts or sources;
- fact-check claims;
- validate numbers, calculations, comparisons, or data scope;
- distinguish fact from inference or recommendation;
- verify current external facts before writing; or
- prevent unsupported content in a draft.

Use it as a separate layer before and after `pyramid-short-form`, `pyramid-long-form`, or `pyramid-presentation`. Use `pyramid-audit` separately for structural diagnosis.

## Select the Verification Mode

The agent states or internally applies one mode before checking claims:

- **Source-bound check:** Compare claims only with material the user supplied. Do not imply that the source itself was independently verified.
- **Data check:** Recalculate derived values and validate units, denominators, populations, periods, and comparison bases.
- **External fact check:** Verify claims with current authoritative sources using an available research or browsing tool. If no such tool is available, state `External verification not performed.`

When the user says `use only these facts`, use source-bound and data checks and apply the restricted output rule in the Non-Negotiable Output Gate. Do not perform or imply external verification unless requested or required by the task's risk.

## Build the Claim Ledger

Create an internal ledger with one row per material claim. Preserve the source wording until the check is complete.

For each claim, record:

1. the exact claim;
2. whether it is a supplied fact, derived calculation, inference, recommendation, or opinion;
3. the supporting source or `none supplied`;
4. its population, period, geography, product, or other scope;
5. every number's value, unit, denominator, and comparison base;
6. the exact terms that must remain explicit to preserve scope and meaning; and
7. one status and its required action:
   - **Supported:** The source directly supports the claim. The drafting skill may use it with the same meaning and scope.
   - **Derived:** The stated calculation follows from supported inputs. The drafting skill may use it when the calculation or method remains clear.
   - **Contradicted:** A supplied or verified source or a valid calculation conflicts with the claim. The drafting skill must not present it as fact.
   - **Unverified:** No checked source establishes the claim. The drafting skill must omit it, request verification, or label it as unverified when the user needs the limitation.
   - **Not factual:** The statement is an inference, recommendation, or opinion. The drafting skill may use it only when the user supplied or explicitly requested that statement and must not present it as a sourced fact.

Use the ledger to create the internal claim packet. Do not print either one unless the user asks for a fact-check report or unresolved claims prevent reliable drafting.

## Check Data Without Changing Its Meaning

The agent performs each applicable action:

1. Preserve every supplied number, sign, unit, denominator, population, period, and qualifier.
2. Recalculate derived values from the stated inputs. Record the formula and rounding when the result will appear in the artifact.
3. When comparing two rates expressed as percentages, calculate both measures before validating the wording:
   - percentage-point change = `new rate - old rate`; report the result as `percentage points`, never `%`;
   - relative percent change = `(new rate - old rate) / old rate × 100`; report the result as `%` or `percent` and identify it as relative change;
   - a claim using `%` must match the relative calculation, while a claim using `percentage points` must match the subtraction. If it matches neither, mark it `Contradicted` and provide the corrected wording.
4. Keep counts, percentages, averages, medians, rates, and totals in their original statistical roles.
5. Attribute an aggregate only to its stated population. Do not assign it to a subgroup, cause, activity, or time period that the source does not identify.
6. Compare values only when their definitions, populations, units, and periods are compatible. Otherwise report the mismatch.
7. Keep missing values missing. Do not estimate, interpolate, or fill them unless the user requests a method and the result is labeled as an estimate.
8. Preserve correlation as correlation. Do not convert it into cause, impact, benefit, risk, or predicted outcome.
9. Keep conflicting values separate until their definitions, dates, or source authority resolve the conflict.

Use a deterministic calculator, spreadsheet, or code execution tool for material calculations when one is available. If a calculation cannot be reproduced reliably, mark the derived claim `Unverified` instead of approving it from model judgment alone.

## Check External Facts

When external verification is required and tools are available, the agent:

1. uses a primary or authoritative source that directly supports the claim;
2. records the source, publication or effective date, and verification date;
3. checks that the source's scope matches the claim;
4. uses a second independent source when the claim is consequential and one is available; and
5. marks any unresolved conflict or stale source instead of choosing silently.

A search result, uncited recollection, or source that merely discusses the topic does not verify the claim.

## Hand Off Claims to the Structure Layer

Before structuring, pass the drafting skill only:

- supported facts with their original scope;
- derived calculations with their formulas and rounding;
- requested inferences or recommendations identified as such and linked to their supporting evidence; and
- unresolved conflicts or evidence limits that the reader needs to know.

The structure layer may select, group, order, and express these claims. It must not change their status, scope, numbers, or certainty.

After drafting, run the separate post-check against every factual or evaluative clause, headline, table entry, and number. For a trace draft, validate each entire tagged clause against its canonical claim and must-preserve terms, restore any missing scope, then strip the IDs. Delete or correct unsupported additions before returning the artifact. If structure requires a claim the packet does not support, remove that branch or state the evidence limit; do not manufacture the claim.

## Return a Fact-Check Report Only When Requested

Use these headings:

1. **RESULT** — State whether the checked material is supported, needs correction, or cannot be verified.
2. **CLAIMS** — For each material claim, give its status, source, and required action.
3. **DATA CHECKS** — Show only calculations, scope mismatches, incompatible comparisons, or data-definition issues that affect use.
4. **UNVERIFIED OR MISSING** — List claims or inputs that remain unresolved and what evidence would resolve them.
5. **SOURCES** — List the supplied or external sources actually checked. If none were checked externally, state that directly.

Do not mix structural Pyramid Principle findings into this report. If the user requests both checks, return separate `SOURCE INTEGRITY` and `STRUCTURE` sections.

## Capability Boundary

This skill can check consistency with supplied material, validate explicit calculations, preserve data scope, and direct an available research tool. It cannot independently certify that a supplied source is true, access current information without a tool, recover missing definitions, or prove causation from correlation.
