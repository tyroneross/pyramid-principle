# Report Skeleton

Full-document scaffold templates and walkthroughs for long-form pyramid documents. Use these skeletons during Pass 1 to choose the right structural variant before building the key line. All structural rules derive from the canonical framework in `pyramid-principle-core`.

Source anchors: `minto-p5-pyramid-sorting`, `minto-p22-scqa`, `minto-p17-vertical-qa`, `minto-p96-mece`

---

## 1. Universal Skeleton

The universal skeleton applies to any long-form document regardless of type. Use it when no specific variant (section 2) is a closer fit, or as the base structure before adapting to a variant.

```
FRONT MATTER
└── Title: [Document title — asserted, specific, not vague]
└── Author / Date / Distribution: [as required by context]
└── Executive Summary (for documents >2,000 words):
    └── Governing thought (one sentence)
    └── Key line compressed (3–5 bullets, each one asserted sentence)
    └── Recommended action or decision, if applicable (one sentence)

INTRODUCTION — SCQA
└── Situation: [Context the reader already accepts — 1 paragraph]
    ↳ What: the domain, project, or decision context the reader shares with you
    ↳ Not: contested claims, recommendations, new data the reader hasn't seen
└── Complication: [What changed or what problem now exists — 1 paragraph]
    ↳ What: the event, finding, constraint, or gap that makes the Situation unstable
    ↳ Test: if the reader learns this and has no natural question, the Complication is weak
└── Question: [The question the Complication raises — explicit or implicit]
    ↳ Most common forms: "What should we do?" / "Why is this happening?" / "How do we fix it?"
└── Answer: [The governing thought — the document's single central claim — 1 sentence]
    ↳ Appears as the final sentence of the introduction
    ↳ Must directly answer the Question; specific enough to be disputed

GOVERNING THOUGHT PARAGRAPH
└── Restate and expand the governing thought in 2–3 sentences
└── Preview the key line (name the 3–5 points that support the governing thought)
└── Signal the document's logical order

KEY LINE — FIRST LEVEL
└── Point 1: [First key-line assertion — one declarative sentence]
    └── Sub-point 1a: [Assertion — answers the question Point 1 raises]
    └── Sub-point 1b: [Assertion]
    └── Sub-point 1c: [Assertion, if needed]
└── Point 2: [Second key-line assertion]
    └── Sub-point 2a
    └── Sub-point 2b
    └── Sub-point 2c
└── Point 3: [Third key-line assertion]
    └── Sub-point 3a
    └── Sub-point 3b
    └── Sub-point 3c

SECOND LEVEL (if document is >2,000 words)
└── Each sub-point from the key line may have its own sub-sub-points
└── Apply plural-noun test and MECE checks at each level independently
└── Stop when leaves require no further logical justification

CONCLUSION
└── One sentence: restate the governing thought in light of the evidence presented
└── Optional: restate the recommended action with the confidence level the evidence warrants
└── Do NOT summarize the document sections — restate the apex claim, not the structure
```

**Slot annotations:**

| Slot | Purpose | Common error |
|---|---|---|
| Front matter executive summary | Give time-constrained readers the full argument in 100 words | Making it a table of contents rather than a compressed pyramid |
| Situation | Establish shared context with no contestation | Including new data the reader hasn't seen yet |
| Complication | Create urgency and relevance for the governing thought | Omitting it; making the Answer feel unprompted |
| Answer (governing thought) | State the document's single most important claim before the body | Burying it mid-document or after all the evidence |
| Key-line point | Assert one supporting claim that answers the governing thought's raised question | Topic label ("Market overview") instead of assertion ("Market contraction reduces TAR by 18%") |
| Sub-key-line | Answer the question the key-line point raises | Restating the key-line point instead of supporting it |
| Conclusion | Restate governing thought; do not recap sections | Section-by-section summary that adds no new synthesis |

---

## 2. Variant Skeletons for Document Types

### Variant A — Analytical Report

**When it fits:** Findings-based work where the governing thought synthesizes what the analysis discovered. The reader's question is "what is happening / what does this mean?" Used when the primary output is insight, not a recommendation or action plan.

**Key-line order:** Structural (findings grouped by domain or theme) or comparative (ranked by significance or impact). Findings are inductive peers — each is an independent observation, and the governing thought is the inference from the pattern.

```
INTRODUCTION
└── Situation: [The analytical context — what was examined and why]
└── Complication: [What gap, anomaly, or decision triggered the analysis]
└── Answer: [The governing synthesis — what the analysis collectively shows]

KEY LINE (structural or comparative order — independent inductive findings)
└── Finding 1: [Most significant finding — asserted, not labeled]
    └── Evidence set 1a, 1b, 1c
└── Finding 2: [Second finding, independent of Finding 1]
    └── Evidence set 2a, 2b, 2c
└── Finding 3: [Third finding]
    └── Evidence set 3a, 3b, 3c

IMPLICATIONS
└── What the findings mean for the reader's decision or context
└── 2–3 implications as peers, each a one-sentence asserted consequence

CONCLUSION
└── Governing synthesis restated, with confidence level if appropriate
```

---

### Variant B — Research Synthesis

**When it fits:** Aggregating multiple sources, studies, or data streams into a unified argument. The reader's question is "what does the evidence show?" The key-line points are named insights — claims that synthesize across sources, not summaries of individual sources.

**Key-line order:** Structural (insights grouped by theme) or comparative (ranked by evidentiary strength or practical importance). Each insight is inductive — an inference from multiple independent sources.

```
INTRODUCTION
└── Situation: [The research question or domain context]
└── Complication: [Why existing evidence is insufficient, contested, or needs synthesis]
└── Answer: [The governing synthesis — what the evidence, taken together, shows]

METHODOLOGY BRIEF (1–2 paragraphs — contextual scaffolding, not a key-line section)
└── What sources were reviewed, how selected, material limitations

KEY LINE (named insights — structural or comparative order)
└── Insight 1: [Named, asserted claim synthesized across sources]
    └── Sub-points: evidence from specific sources that collectively support the claim
└── Insight 2: [Named, asserted claim]
    └── Sub-points: supporting evidence
└── Insight 3: [Named, asserted claim]
    └── Sub-points: supporting evidence

IMPLICATIONS
└── What the synthesis means for practice, policy, or the reader's decision

CONCLUSION
└── Governing synthesis restated; confidence qualified if evidence is contested
```

---

### Variant C — Strategic Proposal

**When it fits:** Making a case for a course of action to an audience that controls resources or approval. The reader's question is "should we do this?" The governing thought is the recommendation and its headline justification.

**Key-line order:** Structural — the four pillars of a proposal case (opportunity, approach, resources, outcome). This matches the reader's evaluative sequence and should not be reordered without a specific reason grounded in the reader's context.

```
INTRODUCTION
└── Situation: [The current context — what exists or what the opportunity is]
└── Complication: [Why status quo is insufficient or the opportunity is time-constrained]
└── Answer: [The recommendation — what to do and why it is the right move]

KEY LINE (structural order — pillars of the case)
└── Point 1 — Opportunity: [What the opportunity is and why it is real]
    └── Market evidence, customer evidence, or strategic rationale
└── Point 2 — Approach: [What specifically is proposed — mechanism, scope, timeline]
    └── Key milestones; how the approach addresses the complication
└── Point 3 — Resource ask: [What is required — budget, headcount, time]
    └── Quantified requirements; comparison to status-quo cost if applicable
└── Point 4 — Expected outcome: [What success looks like and when]
    └── Metrics, milestones, or decision criteria for evaluating success

RISKS AND MITIGATIONS
└── Top 2–3 risks, each with its mitigation
└── Never list risks without mitigations — unmitigated risks undermine the recommendation

CONCLUSION
└── Recommendation as call to action: "Approving X by [date] enables Y."
```

---

### Variant D — Decision Brief

**When it fits:** The reader must make a specific decision. The document advocates for the right choice and gives the reader everything needed to make it. The governing thought is the recommendation. The reader's question is "what should we decide?"

**Key-line order:** Structural — the three pillars of a recommendation (reasons, risks, implementation). Not comparative unless multiple options are genuinely equally viable.

```
INTRODUCTION
└── Situation: [The decision that needs to be made and by when]
└── Complication: [What makes this non-trivial — tradeoffs, constraints, or stakes]
└── Answer: [The recommendation — clear, specific, actionable]

KEY LINE (structural order — pillars of the recommendation)
└── Point 1 — Reasons: [The 2–3 reasons the recommendation is correct]
    └── Sub-points: each reason independently stated and evidenced
└── Point 2 — Risks and mitigations: [Top risks and how they are addressed]
    └── Sub-points: each risk with its specific mitigation
└── Point 3 — Implementation: [What happens next if the decision is made]
    └── Owner, timeline, first concrete action

CONCLUSION
└── Recommendation as the specific decision to record: "Approve X / Reject Y / Defer to Z."
```

---

### Variant E — Problem-Solving Memo

**When it fits:** A problem has been identified and the memo is structured analysis of its cause, response options, and recommended option. The reader's question is "what is causing this and what should we do?"

**Key-line order:** Chronological (problem → diagnosis → options → recommendation). One of the few cases where a near-sequential logic holds across the full key line — each step follows logically from the one before. The recommendation follows inductive reasoning from the options comparison.

```
INTRODUCTION
└── Situation: [The problem as it currently stands — what is observable]
└── Complication: [Why the problem requires immediate structured attention]
└── Answer: [The governing recommendation — what should be done and why]

KEY LINE (chronological order)
└── Point 1 — Problem: [Precise statement of the problem and its measured impact]
    └── Sub-points: evidence quantifying scope, duration, and cost
└── Point 2 — Root cause: [The diagnosed cause — what is actually driving the problem]
    └── Sub-points: evidence linking cause to observed symptoms
└── Point 3 — Options: [The 2–3 viable response options and their tradeoffs]
    └── Sub-points: each option with its cost, timeline, and risk profile
└── Point 4 — Recommendation: [The recommended option and the reasoning for it]
    └── Sub-points: why this option dominates on the criteria that matter most

CONCLUSION
└── Recommendation as specific action: "Implement Option 2 by [date]. Owner: [X]."
```

---

## 3. Section-Intro Templates

Use these templates when opening any section that has sub-sections. Target: 30–60 words total.

**Template A — Straightforward single question:**
> [Parent question restated in one line]. [Answer this section gives — one declarative sentence]. [Preview of sub-points: "This section establishes three sub-claims: X, Y, and Z."]

**Template B — Transition from prior section:**
> [Name the prior section's point in 5–8 words]. [State the question that point raises — which this section now answers]. [Answer sentence]. [Preview if sub-sections follow].

**Template C — Complex section with its own SCQA:**
> [Situation specific to this section — 1 sentence]. [Complication that makes this section's answer necessary — 1 sentence]. [Answer this section gives — 1 sentence, this section's governing claim]. [Preview of sub-points if present].

**Template D — Evidence-heavy section:**
> [State the claim this section proves — 1 sentence]. [Name the type of evidence below: "Three data sets support this claim."]. [Optional: name the most striking piece of evidence to orient the reader].

**Template E — Options section:**
> [State the decision context — "Two viable options exist for [problem]."]. [Name the criterion used to evaluate them]. [State which option the analysis supports and why — if the recommendation has already been made].

---

## 4. Heading Grammar Patterns

Every heading asserts the point of the section it heads. All headings within a peer set share the same grammatical form.

### Valid pattern 1 — All noun phrases (subject + predicate compressed)

```
VALID:
  2. Three Execution Risks to the Q3 Launch
    2.1 Engineering Timeline Compression Creates Delivery Risk
    2.2 Regulatory Approval Uncertainty Extends the Critical Path
    2.3 Unresolved Beta Feedback Blocks the Launch Gate

NOT VALID (mixed):
  2. Three Execution Risks to the Q3 Launch
    2.1 Engineering Timeline Compression Creates Delivery Risk   ← full sentence
    2.2 Regulatory Uncertainty                                   ← topic label
    2.3 How to Handle Beta Feedback                              ← question/instruction
```

### Valid pattern 2 — All complete declarative sentences

```
VALID:
  3. Market Contraction Reduces Total Addressable Revenue by 18%
    3.1 Enterprise segment growth has stalled for three consecutive quarters.
    3.2 SMB churn now exceeds new-customer acquisition.
    3.3 Pricing pressure has compressed average contract value by 12%.

NOT VALID (mixed):
  3. Market Contraction Reduces Total Addressable Revenue by 18%
    3.1 Enterprise segment growth has stalled.    ← sentence (OK alone)
    3.2 SMB Churn                                 ← topic label (broken)
    3.3 Average Contract Value Considerations     ← topic label (broken)
```

### Invalid pattern — topic labels (never use)

```
INVALID:
  4. Financial Overview         ← container, not assertion
    4.1 Revenue                 ← container
    4.2 Costs                   ← container
    4.3 Projections             ← container

CORRECTED:
  4. Financial Performance Is On Track With One Forward Risk
    4.1 Revenue grew 14% YoY, ahead of the 11% plan target.
    4.2 Operating costs are within 2% of budget through Q3.
    4.3 EU contract renewal creates an 8% Q4 revenue risk if unresolved.
```

### Parallelism fix — how to standardize a broken heading set

**Broken set (mixed forms):**
- 2.1 The regulatory approval process takes 6–9 months
- 2.2 Technical integration complexity
- 2.3 How we will manage the vendor relationship

**Step 1:** Identify the question all three sections answer. Here: "What are the execution challenges?"

**Step 2:** Choose one grammatical form. Declarative sentences work well for findings; noun phrases for named structural components.

**Step 3:** Rewrite all headings in that form:
- 2.1 Regulatory approval adds 6–9 months to the critical path
- 2.2 Technical integration requires dedicated engineering for two full quarters
- 2.3 Vendor relationship management requires a dedicated owner to prevent scope creep

All three are now complete declarative sentences asserting findings — parallel, specific, and falsifiable.
