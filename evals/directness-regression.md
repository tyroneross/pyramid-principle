# Structure and Source-Integrity Regression Cases

Use these cases after changing the source-integrity, core, or sibling skills. When a case contains facts, sources, or data, run three distinct stages: a `pyramid-source-integrity` pre-check that creates the internal claim packet, the named structural skill, and a `pyramid-source-integrity` post-check against the draft and original packet. When testing a smaller drafting model, run source checks with the strongest available verification model and use deterministic tools for material calculations.

## Source-integrity criteria

1. Before structuring, the agent checks every material claim against the case sources. When the prompt says `use only these facts`, the artifact uses only the supplied decision, supported facts, and valid derived calculations; it adds no new interpretation or prediction.
2. The agent preserves every number's value, unit, denominator, population, period, and qualifier. If it derives a value, the source-integrity check can reproduce the formula and rounding.
3. The agent does not attribute an aggregate to a subgroup, compare incompatible data, fill a missing value, convert correlation into cause, or present an unverified claim as fact.
4. After drafting, the agent checks every factual or evaluative clause, headline, table entry, and number against the cleared claim set and corrects or deletes any mismatch. Qualifying an unsupported claim with `may`, `could`, `likely`, or `we believe` does not make it valid.
5. When external verification is required but no research tool is available, the agent states `External verification not performed.` and does not imply a current fact was verified.
6. In a separate-call test, the pre-check assigns stable claim IDs and must-preserve scope terms, the structural pass tags each factual or evaluative clause, and the post-check validates the whole clause, restores missing scope, and removes every ID from the final artifact.

## Structure and storyline criteria

1. The artifact states the main answer before its supporting points. It may give only the context required to understand the answer first; no sentence or slide number determines the result.
2. Every peer set answers one parent question and performs one logical role. Different topics do not fail merely because their nouns differ.
3. No names, facts, scenarios, or conclusions from skill examples appear unless the case supplies them.
4. The response contains the requested artifact, not drafting notes, framework labels, assumptions, claim ledgers, or self-check commentary.

## Case 1 — Short-form factual update

**Load:** `pyramid-source-integrity`, `pyramid-principle-core`, `pyramid-short-form`

**Prompt:**

> Draft an executive update of up to 120 words answering: What should leadership know about the application backlog? Use only these facts: 42 applications remain unresolved; 18 have been open longer than 30 days; staffing is unchanged; two applications await legal approval; no statutory deadlines have been missed.

**Case-specific checks:**

- The update does not claim the backlog grew, identify an unprovided cause, or predict a missed deadline.
- The 42 unresolved applications, 18 older applications, pending approvals, staffing, and deadline status retain their supplied meaning.
- The output does not force three supports or expose a `TAG:ASSUMED` note.

## Case 2 — Presentation with already-shared context

**Load:** `pyramid-source-integrity`, `pyramid-principle-core`, `pyramid-presentation`

**Prompt:**

> Create a ghost deck for leaders who already know the current onboarding process. The decision is to approve a four-week pilot that makes SSO optional during trial onboarding. Supplied evidence: 61% of non-converting trials stop before completing onboarding; 38 of 50 interviewed non-converters named SSO setup as the stopping point; the pilot requires two engineers for four weeks. Do not add facts.

**Case-specific checks:**

- The recommendation appears before its supporting evidence, without adding Situation slides the audience does not need.
- The output does not force the governing thought onto slide 3 or pad the deck to a preferred slide count.
- Each evidence headline states only an inference the supplied evidence supports.

## Case 3 — Audit of same-role, different-topic peers

**Load:** `pyramid-principle-core`, `pyramid-audit`

**Reader question:** What project-management controls are missing?

**Content to audit:**

> Project-management controls are missing:
> - Scheduling decisions have no accountable owner.
> - Cost forecasts are updated quarterly rather than monthly.
> - Requirements changes are not recorded.

**Case-specific checks:**

- The audit tests the stated parent question before classifying the bullets.
- It does not flag the set as mixed-kind merely because scheduling, cost, and requirements are different topics; all three are control gaps.
- It reports only violations demonstrated by the supplied content.

## Case 4 — Audit example isolation

**Load:** `pyramid-principle-core`, `pyramid-audit`

**Reader question:** Should the team keep the current triage process through September?

**Content to audit:**

> Service requests remain within the agreed response window. The team should keep the current triage process through September because all 86 requests received this quarter received an initial response within two business days.

**Case-specific checks:**

- The audit contains no vendor, migration, launch, Acme, or alternative-evaluation terminology unless it quotes the supplied content.
- The audit does not add urgency, cost, scheduling, or risk claims that the content does not establish.

## Case 5 — Long-form source-bound outline

**Load:** `pyramid-source-integrity`, `pyramid-principle-core`, `pyramid-long-form`

**Prompt:**

> Create a source-bound outline for an eventual 800-word decision brief. Reader question: What should the agency do with the current intake process? Decision: Keep the current triage process through September and add a required-document checklist. Use only these facts: all 86 requests received this quarter received an initial response within two business days; 14 requests required follow-up because the original submission was incomplete; the team spent 220 hours processing requests this quarter; no statutory deadlines were missed.

**Case-specific checks:**

- The supplied decision is the governing thought and appears before the body outline.
- Every heading and support point maps to a supplied fact or clearly qualified inference.
- The outline does not invent savings, delays, risk, compliance improvements, staffing needs, or expected checklist results.
- The output does not force a preferred number of sections or copy terminology from skill examples.

## Case 6 — Population and denominator preservation

**Load:** `pyramid-source-integrity`, `pyramid-principle-core`, `pyramid-short-form`

**Prompt:**

> Draft a factual executive note using only these facts: Among 50 interviewed non-converters, 38 named SSO setup as the stopping point. Separately, 61% of all non-converting trials stop before onboarding completes. The supplied material does not establish that the 50 interviewees represent all non-converting trials.

**Case-specific checks:**

- If the note uses 76%, it identifies that value as 38 of the 50 interviewees, not 76% of all non-converting trials.
- The note keeps the interview sample separate from the full trial population.
- The note does not claim that SSO causes the 61% stopping rate or that removing SSO will improve conversion.
- The output contains the note, not the internal claim ledger.

## Case 7 — Percentage-point and percent-change calculation

**Load:** `pyramid-source-integrity`

**Prompt:**

> Fact-check this claim: `Conversion increased 5% from Q1 to Q2.` Source data: Q1 conversion was 20%; Q2 conversion was 25%; both values use the same definition and population.

**Case-specific checks:**

- The report corrects the change to `5 percentage points`.
- If it also reports relative change, it calculates `(25% - 20%) / 20% = 25%` and labels that result as relative change.
- It does not use `5%`, `5 percentage points`, and `25%` as interchangeable values.
- It reports source integrity only; it does not create or audit a storyline.

## Case 8 — Different data definitions

**Load:** `pyramid-source-integrity`

**Prompt:**

> Fact-check this claim: `The team handled 1,240 customer tickets in Q2.` Source A is a support-queue export with 1,240 Q2 tickets including spam. Source B is a service-dashboard export with 1,184 Q2 tickets excluding spam. No source defines whether every non-spam ticket came from a customer.

**Case-specific checks:**

- The report does not verify `1,240 customer tickets`; Source A includes spam and does not support `customer`.
- It does not call 1,240 and 1,184 contradictory totals; it identifies their different inclusion rules.
- It may state `1,184 Q2 tickets excluding spam`, but it does not rename them `customer tickets` without a source definition.
- It identifies the missing definition needed to verify the original claim.

## Case 9 — External verification unavailable

**Load:** `pyramid-source-integrity`

**Prompt:**

> Fact-check this current claim: `Vendor X currently supports SAML 2.0.` No source is supplied, and no external research tool is available.

**Case-specific checks:**

- The claim receives `Unverified`, not `Supported` or `Contradicted`.
- The report states `External verification not performed.`
- It identifies current authoritative vendor documentation as the evidence needed to resolve the claim.
- It does not answer yes or no from model memory.
