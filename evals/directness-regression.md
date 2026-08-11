# Structure and Source-Integrity Regression Cases

Use these cases after changing the source-integrity, core, or sibling skills. Use the light source check unless a case requests `use only these facts`, a claim packet, or another strict-mode condition. In strict mode, run three separate stages: a source-integrity pre-check, the named structural skill, and a source-integrity post-check. When testing a smaller drafting model, use the strongest available verification model for source checks and deterministic tools for material calculations.

## Source-integrity criteria

1. Before structuring, the agent gives every factual claim and derived value a specific source, exact locator, confidence level, and confidence reason. A bare label such as `user input`, `company data`, `derived`, or a dash fails. Strict mode also requires stable IDs and a complete source register.
2. High-confidence points may be stated directly; Medium points require attribution or a limitation; Low points stay out of central support; Unverified points are excluded as facts. The structural skill does not assign or upgrade these levels.
3. A derived value records its inputs, formula or query, tool, validation result, and rounding. Its confidence never exceeds its lowest-confidence required input. Strict mode uses stable input claim IDs.
4. Before structuring, the agent checks every material claim against the case sources. When the prompt says `use only these facts`, the artifact uses only the supplied decision, supported facts, and valid derived calculations; it adds no new interpretation or prediction.
5. The agent preserves every number's value, unit, denominator, population, period, and qualifier. If it derives a value, the source-integrity check can reproduce the formula and rounding.
6. The agent does not attribute an aggregate to a subgroup, compare incompatible data, fill a missing value, convert correlation into cause, or present an unverified claim as fact.
7. After drafting, the agent checks every factual or evaluative clause, headline, table entry, and number against the cleared claim set and corrects or deletes any mismatch. Qualifying an unsupported claim with `may`, `could`, `likely`, or `we believe` does not make it valid.
8. When external verification is required but no research tool is available, the agent states `External verification not performed.` and does not imply a current fact was verified.
9. In a separate-call test, the pre-check assigns stable claim IDs and must-preserve scope terms, the structural pass tags each factual or evaluative clause, and the post-check validates the whole clause, restores missing scope, and removes every ID from the final artifact.

## Structure and storyline criteria

1. The artifact states the main answer before its supporting points. It may give only the context required to understand the answer first; no sentence or slide number determines the result.
2. Every peer set answers one parent question and performs one logical role. Different topics do not fail merely because their nouns differ.
3. No names, facts, scenarios, or conclusions from skill examples appear unless the case supplies them.
4. The response contains the requested artifact, not drafting notes, framework labels, assumptions, claim ledgers, or self-check commentary.
5. Each sentence makes one main claim and uses a specific subject with an active verb when the meaning allows.
6. Validated measures replace vague adjectives or adverbs when the source supplies them; the artifact does not invent data to sound precise.
7. Supporting statements repeat or precisely resolve the parent claim's key terms, and each sentence begins from information the reader already has before adding the new point.

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

## Case 10 — Complete source and confidence trace

**Load:** `pyramid-source-integrity`

**Prompt:**

> Create a source-integrity claim packet and visible source trace from this supplied material. Source SRC-1: the user describes attached file `operations-q2.csv`, row `region=all`, columns `resolved_count=72` and `total_count=100`, captured 2026-07-05. Source SRC-2: the current prompt's second supplied fact states the target resolution rate is 80%. Data points: the Q2 resolution rate was 72%; the target was 80%; the gap was 8 percentage points. The files and target source have not been independently checked.

**Case-specific checks:**

- The source register defines `SRC-1` with the supplied filename and capture date and defines `SRC-2` as the current prompt's second supplied fact.
- The 72% point names `SRC-1` and retains the row and columns as its local locator; together, the source record and locator identify the complete evidence.
- The 80% point names `SRC-2` and locates the current prompt's second supplied fact; it does not use bare `user input` as the source.
- Both supplied points receive `Medium` with a reason that they were supplied but not independently checked. The output attributes the source or states the limitation.
- The 8-percentage-point value uses a calculation source ID that resolves in the source register and retains input IDs for both supplied points, formula `80% - 72% = 8 percentage points`, the named deterministic tool and validation status, and confidence no higher than `Medium`. Model or mental arithmetic does not count as the tool.
- The derived point remains `Medium`; passing arithmetic validation does not authorize direct, unqualified presentation.
- The calculated point's integrity status is `Derived`, not `Supported`.
- The trace does not assign numerical confidence percentages, repeat the confidence action in a `permitted use` field, or let the structural layer change confidence.

## Case 11 — Specific language without invented causation

**Load:** `pyramid-source-integrity`, `pyramid-principle-core`, `pyramid-short-form`

**Prompt:**

> Rewrite this status note using only the cleared facts. Vague note: `The plant improvement initiative is progressing significantly. The operational team successfully made meaningful process improvements. Some vendor issues are being actively addressed.` Cleared facts: In May, the maintenance team changed work-order routing at the Dayton plant. Median approval time fell from 6 days to 4 days across 120 work orders. Procurement is reviewing two supplier contracts. The supplied facts do not establish that the routing change caused the approval-time decline or that the contract review addresses an identified issue.

**Case-specific checks:**

- The note names the maintenance team, Dayton plant, work-order routing, approval time, work-order population, procurement, and supplier contracts.
- It replaces `significantly`, `successfully`, and `meaningful` with the supplied facts rather than another adjective.
- It does not claim that routing reduced approval time or that procurement is resolving a vendor problem.
- Each sentence makes one main claim with an active verb.

## Case 12 — Parent-to-bullet term continuity

**Load:** `pyramid-principle-core`, `pyramid-short-form`

**Prompt:**

> Write a short operational finding followed by three complete-sentence bullets. Finding: Three control gaps add four days to monthly close. Supplied supports: Finance analysts manually reconcile vendor codes, adding two days. Regional teams submit files in four formats, adding one day. The controller approves exceptions after close, adding one day. Add no facts.

**Case-specific checks:**

- The finding appears before the three supports.
- Every bullet states one control gap, names the actor, uses an active verb, and retains its measured delay.
- The bullets use one grammatical pattern and perform the same logical role.
- The wording keeps `control gaps` and `monthly close` logically visible rather than replacing them with vague synonyms.

## Case 13 — Given-to-new sentence flow

**Load:** `pyramid-principle-core`, `pyramid-short-form`

**Prompt:**

> Rewrite this paragraph so each sentence connects logically to the next. Original: `Customer wait time rose in June. The scheduling team changed the booking rules. Forty appointments moved to the following week. The clinic should review the rule change.` Cleared relationship: The booking-rule change moved 40 appointments to the following week, which increased June wait time. The clinic should review that rule change.

**Case-specific checks:**

- The first sentence states the supplied cause and measured result without adding a new cause or degree.
- The next sentence picks up `booking-rule change` before stating the review action.
- The paragraph uses no ornamental synonym that obscures whether the same rule change is under discussion.
