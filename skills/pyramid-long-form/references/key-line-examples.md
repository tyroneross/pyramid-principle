# Key Line Examples

Three fully worked key-line examples at decreasing levels of abstraction. Each example shows the complete architecture from reader's question through governing thought, key line, and one second-level sub-key-line, with annotations explaining the structural choices.

Source anchors: `minto-p5-pyramid-sorting`, `minto-p17-vertical-qa`, `minto-p63-deduction-induction`, `minto-p96-mece`, `minto-p22-scqa`

---

## Example 1 — Q3 Product Strategy Recommendation

### Scenario

Novatek is a B2B SaaS company offering project analytics software. The CPO has asked the strategy team to assess whether the current Q3 roadmap should be maintained, deprioritized in favor of an enterprise tier launch, or rebalanced toward integrations. The document goes to the executive leadership team, who have final say over roadmap commitments. They have two weeks to decide before engineering commitments are locked.

### Reader's Question

Should Novatek maintain the current Q3 roadmap, shift resources to the enterprise tier launch, or rebalance toward integrations?

### Governing Thought

Novatek should shift the majority of Q3 engineering capacity to the enterprise tier launch, delaying two current roadmap items by one quarter, because enterprise revenue potential outweighs the cost of the delay under all three customer-impact scenarios modeled.

### Key Line (inductive order — three independent reasons)

1. Enterprise tier launch unlocks a $4.2M ARR opportunity that current roadmap items cannot address.
2. The two items proposed for deferral carry low customer-impact risk based on usage data and NPS signals.
3. Delaying the integrations roadmap by one quarter does not materially affect Q3 partner commitments.

**Reasoning mode:** Inductive. Each key-line point is an independent finding — a separate observation that supports the governing thought. No point derives from the prior point. The governing thought is the inference from the pattern: taken together, these three points justify the recommendation.

**Why not deductive:** A deductive key line would form a chain (premise → premise → therefore conclusion). Here, each point stands independently — Point 2 would remain true even if Point 1 were false. Independent points → inductive key line.

### Sub-Key-Line for Point 1 (the enterprise tier opportunity)

**Point 1 restated:** Enterprise tier launch unlocks a $4.2M ARR opportunity that current roadmap items cannot address.

**Question Point 1 raises:** Why do you say that? What makes up the $4.2M, and why can't current roadmap items address it?

**Sub-key-line (structural order — three dimensions of the opportunity):**

1a. Fourteen enterprise-qualified leads in the pipeline have declined to convert due to the absence of SSO and role-based access controls — features the enterprise tier would include.
1b. Enterprise average contract value is $180K ARR versus $22K for the current mid-market tier, making a 23-account addressable market worth $4.2M.
1c. No current Q3 roadmap item adds enterprise-qualifying features; the roadmap is focused on UX improvements and reporting enhancements that do not clear enterprise procurement thresholds.

**Sub-key-line reasoning:** These three sub-points answer three distinct questions Point 1 raises: (a) what is the blocked demand evidence?, (b) what is the financial math?, (c) why can't the existing roadmap address it? Each is a separate structural fact — structural order, not deductive.

### Annotation

**Order chosen:** Inductive — the three key-line points are independent findings; rearranging them does not break the logic. The parent (governing thought) is an inference from the pattern, not a "therefore" conclusion from a chain.

**MECE check:** The plural noun is "reasons to shift capacity." Each point answers "why shift?" and no two overlap: Point 1 is about opportunity magnitude, Point 2 is about deferral risk, Point 3 is about partner impact. Collectively exhaustive: a reader asking "why shift?" would not identify a major reason the list misses.

**Anchors:** Governing thought grounded in `minto-p22-scqa` (Answer is the document's central claim). Key-line inductive mode grounded in `minto-p63-deduction-induction`. MECE structure grounded in `minto-p96-mece`.

---

## Example 2 — Infrastructure Migration Proposal

### Scenario

Fieldworks Engineering is a 200-person software consultancy running its internal tooling — project management, time tracking, invoicing, and client portals — on a self-managed on-premise server stack. The VP of Engineering has been tasked with producing a migration proposal to move these systems to a managed cloud platform. The proposal goes to the COO and CFO, who will approve or reject the migration budget. Primary concerns: cost, operational risk during migration, and long-term maintainability.

### Reader's Question

Should Fieldworks Engineering migrate its internal tooling to a managed cloud platform, and if so, how should the migration be executed?

### Governing Thought

Fieldworks should migrate to a managed cloud platform by end of Q2, executing a phased migration in three workstreams over 14 weeks, which reduces five-year total cost of ownership by 31% while keeping operational risk within acceptable thresholds throughout.

### Key Line (chronological order — the three phases of execution)

1. Phase 1 (Weeks 1–4): Migrate non-critical internal tools — project management and time tracking — to validate the cloud environment and establish rollback procedures before touching revenue-impacting systems.
2. Phase 2 (Weeks 5–10): Migrate the invoicing system with a parallel-run period, maintaining the on-premise instance live until the cloud instance has processed one full billing cycle without error.
3. Phase 3 (Weeks 11–14): Migrate client portals and decommission on-premise infrastructure, following sign-off from the client success team on portal feature parity.

**Reasoning mode:** Chronological. Each phase occurs in time sequence and depends on prior phases completing successfully. Phase 2 cannot begin until Phase 1 validates the environment; Phase 3 cannot begin until the invoicing system is confirmed stable. The parent (governing thought) names the outcome the sequence produces: a completed migration within the stated timeframe and cost.

**Why not structural or inductive:** The three phases are not independent. They are sequentially dependent — removing or reordering any phase breaks the risk logic. Sequential dependency → chronological key line.

### Sub-Key-Line for Phase 2 (invoicing migration)

**Point 2 restated:** Migrate the invoicing system with a parallel-run period, maintaining the on-premise instance live until the cloud instance has processed one full billing cycle without error.

**Question Point 2 raises:** How does the parallel-run work, and what criteria trigger cutover?

**Sub-key-line (chronological order — three steps within Phase 2):**

2a. In Week 5, deploy the cloud invoicing instance and begin routing all new invoice creation to it while on-premise remains live for all existing invoices and client-initiated queries.
2b. In Weeks 6–9, run both systems in parallel through one complete monthly billing cycle; the cutover gate is zero discrepancies in invoice totals, tax calculations, and payment confirmations between systems.
2c. In Week 10, after the billing cycle gate is cleared by Finance, redirect all invoicing traffic to cloud and archive the on-premise instance in read-only state for 90 days before decommission.

**Sub-key-line reasoning:** The three steps are sequential and dependent. Step 2b cannot begin until 2a is complete; 2c cannot begin until 2b's gate is cleared. Chronological order is correct at both the key-line and sub-key-line levels.

### Annotation

**Order chosen:** Chronological — the phases are a time-sequenced process with dependencies between steps. The parent (governing thought) names the outcome the process produces and the timeline. `minto-p5-pyramid-sorting` grounds why the pre-sorted sequence reduces reader processing load.

**MECE check:** The plural noun is "migration phases." Each phase is a distinct time block with a distinct scope and a distinct completion criterion. No two phases overlap: Phase 1 covers non-critical tools, Phase 2 covers invoicing, Phase 3 covers client portals. Collectively exhaustive: all systems are covered across the three phases.

**Anchors:** Chronological order grounded in `minto-p63-deduction-induction` (the four logical orders). Vertical Q/A dialogue — each phase raises "how does this work?" and the sub-key-line answers it — grounded in `minto-p17-vertical-qa`. MECE peer check grounded in `minto-p96-mece`.

---

## Example 3 — Customer Research Synthesis

### Scenario

Meridian Health is a digital health platform offering remote patient monitoring tools for chronic disease management. The product team commissioned a 12-week qualitative research program: 60 patient interviews, 20 clinician interviews, and a longitudinal diary study with 40 participants. The research synthesis goes to the product leadership team to inform the next annual planning cycle. The team's primary question: what are the friction points in the current patient experience, and which are most worth addressing?

### Reader's Question

What are the most significant friction points in Meridian's current patient experience, and which represent the highest-value opportunities for product investment?

### Governing Thought

Three friction points — symptom logging burden, alert fatigue from undifferentiated notifications, and unclear care team response expectations — account for the majority of patient disengagement and represent addressable product opportunities with high confidence across all three research methods.

### Key Line (comparative order — ranked by research confidence and disengagement impact)

1. Symptom logging burden is the highest-confidence friction point: all three methods converge on it, and 67% of churned patients cited it as their primary disengagement reason.
2. Alert fatigue from undifferentiated notifications is the second-ranked friction point: confirmed by diary study and clinician interviews, with clinicians reporting that patients explicitly ask to reduce notification frequency.
3. Unclear care team response expectations are the third-ranked friction point: confirmed by patient interviews and diary study, with patients reporting uncertainty about when and whether the care team reviews their logged data.

**Reasoning mode:** Inductive, with comparative order. Each key-line point is an independent finding from the research, ranked by the strength of convergent evidence and its association with disengagement. No point derives from the prior point; all three could stand independently. The parent is the inference: these three friction points, ranked in this order, represent the most actionable opportunities.

**Why comparative, not structural:** The three findings are of the same kind (friction points) but differ materially in evidentiary strength and measured disengagement impact. Ranking them by strength-of-evidence makes the comparative order correct: the reader needs to know which is best-evidenced, not merely that three friction points exist.

### Sub-Key-Line for Finding 1 (symptom logging burden)

**Point 1 restated:** Symptom logging burden is the highest-confidence friction point: all three methods converge on it, and 67% of churned patients cited it as their primary disengagement reason.

**Question Point 1 raises:** What specifically makes symptom logging burdensome, and what does the evidence show across each method?

**Sub-key-line (structural order — three dimensions of the finding):**

1a. Patient interviews (n=60): 41 of 60 patients described the daily logging prompt as "too detailed" or "taking too long," with a median reported time of 8 minutes per log entry versus a perceived acceptable threshold of 2–3 minutes.
1b. Diary study (n=40): logging completion rates dropped from 91% in Week 1 to 54% by Week 6, with participant notes citing friction specifically at the symptom-severity rating scale and the free-text field.
1c. Clinician interviews (n=20): 17 of 20 clinicians reported that they primarily use three data points from each log entry (pain level, energy level, activity minutes) and described the remaining fields as "rarely reviewed" — meaning the burden on patients is not matched by clinical utility.

**Sub-key-line reasoning:** The three sub-points are structural — each comes from a different research method and adds a different dimension of evidence for the same claim. They are not sequential (not chronological) and do not derive from each other (not deductive). All three are needed to establish convergent evidence across methods; the parent claim of "highest confidence" rests on all three simultaneously.

### Annotation

**Order chosen:** Comparative — the three friction points are ranked by research confidence and disengagement impact, from strongest to weakest evidence. The reader needs to make allocation decisions; ranked order gives them immediate prioritization.

**MECE check:** The plural noun is "patient friction points." Each point is a distinct experience failure: logging burden (input friction), alert fatigue (notification friction), response uncertainty (expectation friction). No two overlap: a patient could experience any combination of these independently. Collectively exhaustive relative to the governing thought: the three findings are positioned as the majority-accountable friction points, not an exhaustive list of all friction.

**Anchors:** Comparative order grounded in `minto-p63-deduction-induction`. Inductive reasoning mode (each point is an independent finding) grounded in `minto-p63-deduction-induction`. Vertical Q/A dialogue at the sub-key-line level grounded in `minto-p17-vertical-qa`. MECE validation grounded in `minto-p96-mece`.

---

## When to Change Order Mid-Key-Line

Do not. Choose one logical order for the key line and hold it through all peers.

A key line that switches from chronological to comparative partway through has no single governing logic. The parent claim cannot accurately summarize a set whose members are related by two different ordering principles simultaneously. The parent would have to be vague enough to cover both — which means it becomes a container label rather than an inference.

**The test:** State the logical order rule you applied. Now read the key line as if you are the reader. Does every peer fit that rule? If a peer fits a different rule better than the stated one, remove it from the key line and find the correct place for it.

**If you genuinely need two ordering principles**, the key line has mixed content and should be split into two sub-key-lines under a higher-level governing thought. Each sub-key-line gets its own ordering rule. The governing thought then becomes an inference from both groups.

**Example of when splitting is correct:** A strategic proposal key line that mixes "three reasons to act" (inductive/comparative) with "four implementation phases" (chronological). Split into: (1) a reasons sub-key-line under "The case for acting is strong" and (2) a phases sub-key-line under "The migration executes in four phases." Both sit under a governing thought that connects case and execution.
