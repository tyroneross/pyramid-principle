# Directness Regression Cases

Use these cases after changing the core or a sibling skill. Run each case with `pyramid-principle-core` plus the named sibling skill, then evaluate the returned artifact against the shared criteria.

## Shared criteria

1. The artifact states the main answer before its supporting points. It may give only the context required to understand the answer first; no sentence or slide number determines the result.
2. Every factual claim maps to the case facts. New inferences or recommendations are distinguishable from supplied facts and identify their support.
3. Every peer set answers one parent question and performs one logical role. Different topics do not fail merely because their nouns differ.
4. No names, facts, scenarios, or conclusions from skill examples appear unless the case supplies them.
5. The response contains the requested artifact, not drafting notes, framework labels, assumptions, or self-check commentary.

## Case 1 — Short-form factual update

**Load:** `pyramid-principle-core`, `pyramid-short-form`

**Prompt:**

> Draft an executive update of up to 120 words answering: What should leadership know about the application backlog? Use only these facts: 42 applications remain unresolved; 18 have been open longer than 30 days; staffing is unchanged; two applications await legal approval; no statutory deadlines have been missed.

**Case-specific checks:**

- The update does not claim the backlog grew, identify an unprovided cause, or predict a missed deadline.
- The 42 unresolved applications, 18 older applications, pending approvals, staffing, and deadline status retain their supplied meaning.
- The output does not force three supports or expose a `TAG:ASSUMED` note.

## Case 2 — Presentation with already-shared context

**Load:** `pyramid-principle-core`, `pyramid-presentation`

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

**Load:** `pyramid-principle-core`, `pyramid-long-form`

**Prompt:**

> Create a source-bound outline for an eventual 800-word decision brief. Reader question: What should the agency do with the current intake process? Decision: Keep the current triage process through September and add a required-document checklist. Use only these facts: all 86 requests received this quarter received an initial response within two business days; 14 requests required follow-up because the original submission was incomplete; the team spent 220 hours processing requests this quarter; no statutory deadlines were missed.

**Case-specific checks:**

- The supplied decision is the governing thought and appears before the body outline.
- Every heading and support point maps to a supplied fact or clearly qualified inference.
- The outline does not invent savings, delays, risk, compliance improvements, staffing needs, or expected checklist results.
- The output does not force a preferred number of sections or copy terminology from skill examples.
