# Diagnostic Checklist

Rule-indexed checklist for pyramid audits, organized by the five audit steps. For each check: the rule, the source anchor, the question to ask of the content, red flags indicating a violation, and severity guidance.

All rules derive from Barbara Minto, *The Pyramid Principle* (2009 revised edition). Anchor IDs reference `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`.

---

## Step 1 — Governing Thought Checks

The governing thought is the apex of the pyramid: the single most important claim the document makes. All other checks depend on it. Never skip this step.

---

### GT-1: Governing thought is stated

**Rule:** Every document must have a single explicit governing thought — the claim from which all supporting material flows.

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** Read the opening paragraph, subject line, first slide title, or first section heading. Is there a complete, arguable claim stated explicitly? Not a topic label, not a process description — a claim.

**Red flags:**
- The opening paragraph describes background or context only, with no assertion
- The first statement is a process description ("This memo outlines...") rather than a claim
- The only place a claim appears is the conclusion — buried past the midpoint
- The document title is a noun phrase ("Q3 Infrastructure Review") with no predicate

**Severity:** Blocker if absent entirely. Important if present but weak (a claim that could be true under any circumstances).

---

### GT-2: Governing thought is answer-first

**Rule:** The governing thought must appear at the opening — before supporting evidence, analysis, or background.

**Source anchor:** `minto-p17-vertical-qa`

**Question to ask:** At what point in the document does the reader first encounter the central claim? Is it within the first 10% of the document?

**Red flags:**
- The document leads with data or analysis, then arrives at a recommendation at the end
- The governing thought appears in a "conclusion" or "summary" section after all evidence
- The opening paragraph is pure Situation with no Answer anywhere near it

**Severity:** Important. Buried governing thought is one of the most common and high-impact violations — it forces the reader to hold all the evidence in memory before understanding what it supports.

---

### GT-3: Governing thought answers the reader's question

**Rule:** The governing thought must directly answer the specific question the reader brings to the document. A governing thought that answers a related-but-different question produces a structurally valid pyramid that argues for the wrong thing.

**Source anchor:** `minto-p22-scqa`

**Question to ask:** State the reader's question (inferred or supplied). Read the governing thought. Does the governing thought directly answer that question, or does it answer a different question?

**Red flags:**
- The reader's question is "what should we do?" but the governing thought describes what happened
- The reader's question is "is this approach viable?" but the governing thought recommends an unrelated action
- The governing thought is so general ("We face significant challenges") that it could answer almost any question

**Severity:** Blocker if the governing thought answers a fundamentally different question. Important if it partially addresses the question but with insufficient specificity.

---

### GT-4: Governing thought is a complete claim, not a container label

**Rule:** The governing thought must be a claim — a statement with a predicate that asserts something specific enough to be disputed. A topic label ("Launch Strategy") is not a governing thought.

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** Could a reasonable person disagree with this statement? If no one could dispute it (it is trivially true or purely descriptive), it is not a claim.

**Red flags:**
- The governing thought is a noun phrase without a verb
- The governing thought is a statement of fact with no evaluative or directive implication
- The governing thought uses hedging language that makes it unfalsifiable ("There are several factors worth considering")

**Severity:** Blocker.

---

## Step 2 — SCQA Introduction Checks

Apply to any document, email, memo, or presentation that opens with an introductory section. Skip only for continuation documents (replies, follow-on sections) where the Situation and Complication were established in a prior exchange.

Source authority for all SCQA checks: `minto-p22-scqa`.

---

### SCQA-1: Situation is present and grounded in shared context

**Rule:** The Situation establishes context the reader already knows and accepts. It does not introduce contested claims, recommendations, or new information.

**Source anchor:** `minto-p22-scqa`

**Question to ask:** Does the opening establish what the reader already knows? Is it composed only of accepted background — not the writer's interpretations or conclusions?

**Red flags:**
- The Situation contains contested claims the reader might dispute
- The Situation is padded with history the reader already knows, consuming space that belongs to the Complication
- The Situation is absent — the document opens directly with the Complication or the Answer

**Severity:** Nit if padded. Important if absent when a shared Situation is genuinely needed to orient the reader. Nit if the reader clearly shares context and brevity is appropriate.

---

### SCQA-2: Complication is present and specific

**Rule:** The Complication introduces the change, tension, risk, or problem that makes the Situation unstable. Without a Complication, the reader has no question — and without a question, the Answer has no purpose.

**Source anchor:** `minto-p22-scqa`

**Question to ask:** What specifically changed, broke, appeared, or was discovered? Is there a concrete event or finding that creates urgency?

**Red flags:**
- No Complication exists — the document goes directly from Situation to Answer
- The Complication is vague ("there are some concerns") without specifying what changed
- The Complication is actually a restatement of the Situation ("we've always had this challenge")
- The Complication and Situation are blended in a single sentence ("We've been growing fast but are now facing a slowdown")

**Severity:** Important when absent or blended. This is the most common and damaging SCQA failure — it removes the reader's motivation to engage with the Answer. Nit when present but vague rather than absent.

---

### SCQA-3: Question is implied or stated clearly

**Rule:** The Question is the natural inquiry the reader would have after reading the Situation and Complication together. It is often implicit. When it is stated, it must be the question the reader actually has — not a question the writer found convenient.

**Source anchor:** `minto-p22-scqa`

**Question to ask:** Read the Situation and Complication together. What question would a reasonable reader ask next? Does the document's Answer address that question?

**Red flags:**
- The document states a question the reader would not naturally have given the S and C
- The document's Answer addresses a different question than the one the S and C raise
- The Question is over-stated (long rhetorical framing) when context makes it obvious

**Severity:** Important if the stated Question is wrong (answers a different reader question than what the content actually addresses). Nit if it is simply over-stated.

---

### SCQA-4: Answer is explicit and placed at the opening

**Rule:** The Answer — the governing thought — appears early and explicitly. It is not implied, not withheld until the end, and not embedded in the middle of a paragraph.

**Source anchor:** `minto-p22-scqa`

**Question to ask:** At what point does the reader first encounter a complete, arguable claim? Is it in the first paragraph or on the first slide?

**Red flags:**
- The document ends with "In conclusion, we recommend..." — the Answer is buried
- The Answer is implied through a series of supporting points but never explicitly stated
- The opening contains only Situation and Complication with no Answer — the Answer appears two pages later

**Severity:** Important.

---

## Step 3 — Vertical (Q/A Logic) Checks

The vertical relationship governs what information appears and when. Every non-leaf idea raises a question; the level below must answer that specific question.

Source authority: `minto-p17-vertical-qa`.

---

### VL-1: Each major claim raises a clear question

**Rule:** Every idea in the pyramid raises a question in the reader's mind. The writer is obligated to answer it on the level below. (`minto-p17-vertical-qa`)

**Source anchor:** `minto-p17-vertical-qa`

**Question to ask:** For each major heading, topic sentence, or key-line point: what question does this statement naturally raise in a skeptical reader? (Why? How? Why do you say that?)

**Red flags:**
- A claim is made that raises an obvious question, but the document moves on without answering it
- A heading states a conclusion, but the following paragraph provides background rather than justification
- A claim raises "Why?" but the level below supplies a process description answering "How?"

**Severity:** Important.

---

### VL-2: Material below each claim answers that claim's specific question

**Rule:** The level immediately below must answer the question the level above raised — not a related question, not an interesting tangent, not background.

**Source anchor:** `minto-p17-vertical-qa`

**Question to ask:** Read the claim at level N. Read the material at level N+1. Does the N+1 material directly answer the question that N raised, or does it answer a different question?

**Red flags:**
- Level N claims something is wrong; level N+1 describes what was done historically (answers "what happened?" not "why is it wrong?")
- Level N states a recommendation; level N+1 describes the current state rather than justifying the recommendation
- Level N raises a "Why?" question; level N+1 supplies steps (a "How?" answer)

**Severity:** Important.

---

### VL-3: No information arrives before its question is raised

**Rule:** Information belongs at the level where it answers the question raised by the level above. Presenting information before the question it answers has been raised creates confusion — the reader doesn't know why they are receiving it.

**Source anchor:** `minto-p17-vertical-qa`

**Question to ask:** Is there data, context, or analysis that appears early in the document but whose purpose only becomes clear later?

**Red flags:**
- A section opens with data the reader must hold in memory without knowing why
- A supporting argument appears before the claim it supports has been made
- The conclusion appears after a long section of unframed evidence (the reader doesn't know what the evidence is for)

**Severity:** Important.

---

### VL-4: No hanging assertions — every claim is supported

**Rule:** Every non-leaf assertion in the pyramid must have ideas below it that provide justification, steps, or evidence. A claim with nothing below it is asserted rather than argued.

**Source anchor:** `minto-p17-vertical-qa`

**Question to ask:** For each major claim in the document: is there supporting material directly below it, or does the document move on to a new topic?

**Red flags:**
- A strong claim is made in a heading, then the following paragraph transitions to a different topic without supporting the claim
- The document contains single-item "bullet points" that assert without elaborating
- A recommendation is made but the rationale is absent

**Severity:** Important if the hanging assertion is a key-line point. Nit if it is a minor sub-point.

---

## Step 4 — Horizontal (MECE + Logic-Mode) Checks

Source authorities: `minto-p96-mece`, `minto-p63-deduction-induction`.

---

### HL-1: Peer set passes the plural-noun test

**Rule:** Every peer set must be nameable with a single plural noun that accurately describes all members, excludes non-members, and requires no qualification to include any member. (`minto-p5-pyramid-sorting`, `minto-p96-mece`)

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** Name this peer set with a plural noun. Does that noun accurately describe every member without exception or qualification?

**Red flags:**
- The set mixes kinds: one item is a reason, another is a step, another is a fact — no single noun fits all
- The label used is "key points," "considerations," "items," or "things" — nouns that impose no constraint
- Qualifying language is needed to include all members ("these are mostly risks, plus one recommendation")

**Severity:** Important.

---

### HL-2: Peers are mutually exclusive

**Rule:** No item in a peer set should belong in more than one peer. Overlapping items signal that the categorization is too coarse or that two items describe the same underlying phenomenon. (`minto-p96-mece`)

**Source anchor:** `minto-p96-mece`

**Question to ask:** For any two items in the peer set: could the same underlying fact, event, or entity be correctly described by both? If yes, the items are not exclusive.

**Red flags:**
- Two items in a list share the same root cause (e.g., slow response time and reduced headcount, where the former is caused by the latter)
- Two items describe the same phenomenon from different angles (e.g., "high churn" and "low retention")
- A finding appears under two different section headings

**Severity:** Important.

---

### HL-3: Peers are collectively exhaustive

**Rule:** The peer set accounts for all relevant instances of the thing being grouped. A significant omission invalidates the parent claim's summary. Exhaustiveness is relative to the parent claim's scope. (`minto-p96-mece`)

**Source anchor:** `minto-p96-mece`

**Question to ask:** After reading all items, ask: could the parent claim be true even if there were a significant item not in this list? If yes, the set is not exhaustive relative to the parent.

**Red flags:**
- The parent says "three risks" but there is an obvious fourth risk the reader would immediately identify
- A grouping claims to cover all options but omits a widely-known alternative
- The parent's scope claim ("all channels," "every stakeholder") is not matched by the list

**Severity:** Important when a glaring omission is present. Nit when exhaustiveness is bounded and the omission is peripheral.

---

### HL-4: Peer set uses a single logic mode — deductive or inductive, not both

**Rule:** A peer group uses deductive logic (each point derives from the prior, ending in a "therefore" conclusion) or inductive logic (each point is an independent member of a like category) — never both in the same grouping. Mixing modes breaks the parent claim. (`minto-p63-deduction-induction`)

**Source anchor:** `minto-p63-deduction-induction`

**Question to ask:** Does any point in the peer set derive from a prior point (deductive), while another point stands independently (inductive)? If yes, the modes are mixed.

**Red flags:**
- A deductive chain (premise → premise → therefore) is followed by an additional independent point that was not part of the chain
- The parent summarizes a conclusion from a chain, but one item in the set is actually an independent supporting fact
- The word "therefore" or "thus" appears mid-list, suggesting the list is actually a chain, but the list contains items before and after the conclusion

**Severity:** Important.

---

### HL-5: Parent accurately summarizes children — inference, not container

**Rule:** The parent idea in any grouping must be the inference or conclusion drawn from the set below — not a container label naming the topic. A container label says "there are things here." An inference says "this is what those things mean." (`minto-p5-pyramid-sorting`)

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** Change one child item substantially to something different. Does the parent label remain valid? If yes, the parent is a container. A genuine inference would break.

**Red flags:**
- Parent says "Issues with the launch" (would be true regardless of what the issues are)
- Parent says "Market considerations" (a topic name, not an inference about what the considerations mean)
- Parent says "There are several factors" (true for any set of factors on any topic)
- Parent says "Three things to consider" rather than "Three execution gaps that put Q3 at risk"

**Severity:** Important.

---

## Step 5 — Ordering Checks

Source authority: `minto-p5-pyramid-sorting`.

---

### OR-1: A valid order is applied to each peer set

**Rule:** Every peer set follows one of the four valid logical orders: deductive, chronological, structural, or comparative. The order is determined by the nature of the set, not the writer's convenience.

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** For each peer set, identify which order was applied. Can a single order explain the sequence? If not, the sequence is arbitrary.

**Red flags:**
- The items appear in the order they were written, with no discernible logic
- A list of steps is not in time order
- A comparative ranking (e.g., options by risk) is not sorted by the ranking criterion
- A structural decomposition (e.g., regional divisions) is not in a consistent spatial or categorical sequence

**Severity:** Important if the ordering violation makes the parent summary inaccurate. Nit if the order is slightly inconsistent but the set type is clear.

---

### OR-2: One order is applied consistently within a peer set

**Rule:** A single ordering principle applies to all peers in a set. Mixing chronological and comparative order within one peer set signals that the set type has not been determined.

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** Does the sequence switch ordering principles mid-list? (e.g., first two items are in time order, then items switch to comparative order by priority)

**Red flags:**
- First items ordered by time, then later items ordered by importance
- A ranked list that begins with the highest-priority item, then includes lower-priority items out of rank order
- A structural decomposition that follows organizational units for some items and geographic regions for others

**Severity:** Important.

---

### OR-3: Order matches the nature of the peer set

**Rule:** The correct order is determined by what the set represents. Chronological order applies to processes. Structural order applies to parts of a whole. Comparative order applies to ranked options. Deductive order applies to argument chains.

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** What does this peer set represent? Does the order applied match what the set represents?

**Red flags:**
- A process (which should be chronological) is ordered by importance instead
- Options being evaluated (which should be comparative) are ordered by the time they were identified
- An argument chain (which requires deductive order) is presented as a ranked list

**Severity:** Nit-to-Important depending on whether the mis-ordered set creates reader confusion or merely looks inconsistent.

---

## Step 6 — Heading Checks (Long-Form and Presentations)

Apply only when auditing reports, proposals, multi-section memos, or slide decks. Skip for short-form email or single-section documents.

---

### HD-1: Headings assert the point, not the topic

**Rule:** Section headings in a pyramid document make a claim (inference) about what the section argues — they do not merely name the topic. A topic heading is a container; a point heading is a mini-governing-thought for that section.

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** Read each heading in isolation. Does it assert a claim, or does it name a subject area?

**Red flags:**
- Headings like "Market Analysis," "Financial Review," "Risks" — these are topic names, not claims
- Headings contain no verb or predicate
- A heading could describe any set of children, regardless of what the children actually say

**Severity:** Important for long-form documents where headings guide reader navigation. Nit for short-form where headings are primarily organizing devices.

---

### HD-2: Peer headings are parallel

**Rule:** Headings at the same level of a document share grammatical form and logical level. Mixed grammatical structures at the same level signal mixed kinds in the peer set.

**Source anchor:** `minto-p5-pyramid-sorting`

**Question to ask:** Are all headings at the same level grammatically parallel — all noun phrases, all action imperatives, or all full declarative sentences?

**Red flags:**
- One heading is a question, another is a noun phrase, another is a full sentence
- Headings at the same level represent different levels of the pyramid (one is a sub-point, another is a main point)
- Grammatical form switches inconsistently within the same section level

**Severity:** Nit.

---

## Quick Audit Checklist

For use during rapid review. Check each item as Pass (P) or Fail (F). Any Fail warrants a finding in the audit report.

**Governing Thought**
- [ ] GT-1: Governing thought stated explicitly (`minto-p5-pyramid-sorting`)
- [ ] GT-2: Governing thought answer-first — appears in opening (`minto-p17-vertical-qa`)
- [ ] GT-3: Governing thought answers the reader's question (`minto-p22-scqa`)
- [ ] GT-4: Governing thought is a claim, not a container label (`minto-p5-pyramid-sorting`)

**SCQA Introduction** *(skip if continuation document)*
- [ ] SCQA-1: Situation present and grounded in shared, undisputed context (`minto-p22-scqa`)
- [ ] SCQA-2: Complication present and specific (`minto-p22-scqa`)
- [ ] SCQA-3: Question implied or stated correctly (`minto-p22-scqa`)
- [ ] SCQA-4: Answer explicit and placed at opening (`minto-p22-scqa`)

**Vertical Logic**
- [ ] VL-1: Each major claim raises a clear question (`minto-p17-vertical-qa`)
- [ ] VL-2: Material below each claim answers that claim's specific question (`minto-p17-vertical-qa`)
- [ ] VL-3: No information arrives before its question is raised (`minto-p17-vertical-qa`)
- [ ] VL-4: No hanging assertions — every key claim is supported (`minto-p17-vertical-qa`)

**Horizontal Logic**
- [ ] HL-1: Peer set passes the plural-noun test (`minto-p5-pyramid-sorting`)
- [ ] HL-2: Peers are mutually exclusive (`minto-p96-mece`)
- [ ] HL-3: Peers are collectively exhaustive relative to parent claim (`minto-p96-mece`)
- [ ] HL-4: Single logic mode — deductive XOR inductive, not both (`minto-p63-deduction-induction`)
- [ ] HL-5: Parent is inference label, not container label (`minto-p5-pyramid-sorting`)

**Ordering**
- [ ] OR-1: Valid order applied to each peer set (`minto-p5-pyramid-sorting`)
- [ ] OR-2: One order applied consistently within each peer set (`minto-p5-pyramid-sorting`)
- [ ] OR-3: Order matches the nature of the peer set (`minto-p5-pyramid-sorting`)

**Headings** *(long-form and presentations only)*
- [ ] HD-1: Headings assert the point, not the topic (`minto-p5-pyramid-sorting`)
- [ ] HD-2: Peer headings are parallel (`minto-p5-pyramid-sorting`)
