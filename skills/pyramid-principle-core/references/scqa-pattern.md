# SCQA Pattern

Canonical definition of the Situation/Complication/Question/Answer introduction framework, medium-specific guidance, worked examples, and common pitfalls. All rules derive from Barbara Minto, *The Pyramid Principle* (2009 revised edition).

Source anchor: `minto-p22-scqa`

---

## Definition

The SCQA pattern builds the preamble to any document, email, or presentation. Its purpose is to establish common ground with the reader before introducing the writer's central claim.

Minto's definition:

> Thus, you make sure your document is of interest by directing it toward answering a question that already exists in the reader's mind, or that would exist if he thought for a minute about what is going on around him. The introduction identifies that question by tracing the history of its origin.
>
> Since this history will be in the form of a narrative of events, it should follow the classic narrative pattern of development. That is, it should begin by establishing for the reader the time and place of a Situation. In that Situation something will have occurred (known as the Complication) that caused him to raise (or would cause him to raise) the Question to which your document will give him the Answer.
>
> This classic pattern of story-telling — Situation, Complication, Question, Answer — permits you to make sure that you and the reader are 'standing in the same place' before you take him by the hand and lead him through your thinking.

*(minto-p22-scqa)*

---

## The Four Moves

### Situation

The Situation is what the reader already knows and accepts. It establishes time, place, and context without introducing anything the reader would dispute. The Situation is not where new information lives — it is the shared foundation from which the document departs.

**What belongs here:**
- Recent events the reader is already aware of
- The current state of affairs that both parties accept
- A brief factual framing of the domain (company, market, project, problem space)

**What does not belong here:**
- Contested claims or interpretations
- The writer's recommendations or conclusions
- Evidence or data the reader hasn't seen (that belongs in the pyramid, not the intro)

The Situation should be brief. If the reader already knows the context, a sentence or two suffices. Padding the Situation with known information wastes the reader's time and delays the Complication, which is where the document's relevance is established.

### Complication

The Complication is the change, tension, problem, risk, or unexpected development that makes the Situation unstable or insufficient. It is the reason the document needs to exist. Without a Complication, the reader has no question — and without a question, the writer has nothing to answer.

**What belongs here:**
- The event or development that changed the stakes
- The constraint or conflict that has appeared within the Situation
- The gap between where things are and where they need to be

**Key test:** If the reader learns the Complication and has no natural question about what to do or think next, the Complication is weak or missing.

### Question

The Question is what the reader would naturally ask given the Situation and Complication together. In most professional writing, the Question is implicit — the writer constructs the Situation and Complication precisely so the Question arises without being stated.

**Common forms:**
- "What should we do?" (decision or action document)
- "Why is this happening?" (diagnostic or analytical document)
- "How do we get there?" (planning or implementation document)
- "Is this the right choice?" (evaluation or recommendation document)

Identifying the Question explicitly during drafting is essential even if it never appears in the document. It determines what the governing thought (Answer) must be, and it determines what counts as relevant support in the pyramid.

### Answer

The Answer is the governing thought: the document's single central claim. It is the apex of the pyramid. Everything in the document is either the SCQA introduction or a point that supports this Answer.

The Answer must:
- Directly answer the Question
- Be specific enough that it could be disputed (a vague Answer supports nothing)
- Be a complete claim, not a topic label ("We should migrate to the new platform by Q3" vs. "Migration")

State the Answer early and explicitly. Answer-first structure is the purpose of the entire framework — the SCQA preamble exists to earn the reader's readiness to receive the Answer at the top, before any supporting detail appears.

---

## Medium-Specific Guidance

### Short-Form (Email, Memo, Slack message, Brief note)

Compress all four SCQA moves into 2–3 sentences, or as few words as the shared context permits. In established working relationships where Situation is fully shared, the SCQA can collapse to Complication + Answer.

Target: The reader should understand the context, the urgency, and the central claim within the first 2–3 sentences of reading.

Example (compressed):
> "The vendor confirmed today that the delivery date slips to Q2 (Situation + Complication). To keep the product launch on track, we need to authorize the expedited production option by end of week (Answer)."

The Question ("What do we do about the slip?") is implicit.

### Long-Form (Report, Proposal, Analysis, Memo of 2+ pages)

Give each SCQA element its own sentence or paragraph. The Situation may span a short paragraph if context is complex or the audience has limited prior knowledge. The Complication warrants at least one focused paragraph. The Question may be stated explicitly. The Answer — the governing thought — appears as the concluding sentence of the introduction, before the document's body begins.

Target: The introduction runs no longer than one page. The reader finishes it knowing exactly what the document argues before reading any supporting material.

### Presentation (Slides)

Map the SCQA across opening slides, not prose. A common pattern:

- **Slide 1 (title or context slide):** Situation — the state of affairs the audience already knows
- **Slide 2 (so what slide):** Complication — why the current situation is insufficient or has changed
- **Slide 3 (governing thought or recommendation slide):** Answer — the central claim, stated as the slide title, before evidence or detail

The Question may appear on Slide 2 as a framing device ("So we face a critical question:") or may be entirely implicit.

The Answer slide is the most important slide in the deck. Many presentations bury the governing thought halfway through. In pyramid structure, the Answer appears before the evidence — often as the third slide, after the Situation and Complication have prepared the audience.

---

## Worked Examples

### Example 1 — Good SCQA

**Context:** An internal recommendation memo on infrastructure costs.

> Our cloud infrastructure spend grew 34% year-over-year, reaching $2.8M in FY24 — in line with our revenue growth trajectory and already approved in the annual budget. (Situation)
>
> However, our Q1 audit identified $680K in committed spend on services that are no longer in active use, including three legacy environments and two deprecated data pipelines. (Complication)
>
> [Implicit question: What should we do about the waste?]
>
> Decommissioning the five identified resources will recover $680K in annualized spend without any impact to production systems, and the work can be completed within 30 days. (Answer)

**Why this works:**
- Situation establishes shared context the reader already knows (spend grew, it was approved)
- Complication introduces new information that creates urgency (waste identified in audit)
- The Question is obvious and implicit
- The Answer directly addresses the Question with specificity (amount, timeline, risk)

### Example 2 — Bad SCQA (with rewrite)

**Original:**

> This memo is about our cloud infrastructure costs. We have been spending a lot on cloud and we need to think about what to do. There are several things we could do to address this situation and I will outline them in this document.

**Problems:**
- Situation is vague ("spending a lot") and not grounded in shared context
- No Complication — there is no change or tension; "spending a lot" is a condition, not a trigger
- No Question — the reader has no urgent problem to solve
- The Answer is absent — "outline several things" is not a governing thought
- The reader finishes the opening with no idea what the document argues

**Rewrite:**
> Cloud spend is on budget and expected — FY24 came in at $2.8M, approved in the annual plan. (Situation) Our Q1 audit found $680K tied to services no longer in use. (Complication) Decommissioning these five resources recovers that spend within 30 days at zero production risk. (Answer)

---

## Common Pitfalls

**Pitfall 1: Starting with the Answer before establishing the Situation**

Beginning with "We recommend migrating to the new platform" before the reader knows what's wrong with the current one. The Answer lands without weight because the Complication hasn't been established. Result: the reader reads the recommendation skeptically or questions whether the document understands their context.

**Fix:** Build the Situation and Complication first, even briefly. The Answer lands harder when the reader has just been shown the gap it closes.

**Pitfall 2: Skipping the Complication**

Writing a Situation and then immediately stating the Answer, with no Complication in between. This is the "and therefore we recommend..." pattern. Without the Complication, the reader doesn't understand why change is needed. The document reads as a solution looking for a problem.

**Fix:** Identify the specific event, finding, constraint, or change that makes the Answer necessary. That is the Complication. Without it, the document's urgency is implied but not established.

**Pitfall 3: Asking a question the reader doesn't actually have**

Constructing a SCQA for a document the reader wasn't expecting to receive. The writer frames a Question that the reader doesn't naturally arrive at given the Situation and Complication. This signals that the writer hasn't thought carefully about the reader's prior state or actual needs.

**Fix:** Work backwards. Identify the reader's starting state (Situation). Identify what changed or what problem exists for the reader specifically (Complication). Identify the question the Complication naturally raises for this reader. Then confirm the Answer addresses that question — not a related but different question the writer found more interesting.

**Pitfall 4: A Situation that contains the Complication**

Mixing the two: "We've been growing fast but are now facing a slowdown." This combines background with the new development in a single sentence, which blurs the line between what's already known and what's changed. The reader can't tell where shared ground ends and the urgent news begins.

**Fix:** Separate cleanly. Situation = what was true and accepted. Complication = what just changed or what has now come to light. The transition between them is the document's central hook.
