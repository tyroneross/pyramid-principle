# Common Violations

Catalog of the ten most frequent Pyramid Principle violations found in professional writing. For each violation: the name, what it looks like in practice, the anchor it violates, the typical fix, and the root cause — so the audit feedback is actionable, not merely diagnostic.

All rules derive from Barbara Minto, *The Pyramid Principle* (2009 revised edition). Anchor IDs reference `${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md`.

---

## Violation 1 — Topic-Led Opener

**What it looks like:**

> "This memo covers the background on our cloud infrastructure, including the history of our vendor relationships, spend trends from FY21 through FY24, and the current architecture. The following sections describe each area in turn."

The document opens with a description of its own contents rather than with the claim it makes. The reader learns what topics will be covered before learning what the document argues.

**Anchor violated:** `minto-p22-scqa`

The SCQA pattern requires the Situation and Complication to orient the reader, followed immediately by the Answer (governing thought). A topic-led opener substitutes a table of contents for an argument, leaving the reader without a governing thought to evaluate.

**Typical fix:** Replace the opening paragraph with SCQA structure. Identify what changed (Complication) and state the central recommendation or finding (Answer) in the first paragraph. The document's topics become section headings — they do not need to be announced in the opening.

**One-sentence rewrite direction:** Lead with the governing thought: the claim the memo makes about cloud infrastructure, not a description of what the memo contains.

**Why it happens:** Writers learn to write chronologically — describe the situation, analyze it, then conclude. This produces background-first structure that is natural to write but hard to read. The reader must hold all context in memory before the point is revealed. Answer-first feels presumptuous to writers but is what readers need.

---

## Violation 2 — Missing Complication in SCQA

**What it looks like:**

> "Our sales team has been using the current CRM for three years. The system is widely used across the organization. We recommend migrating to a new platform by Q3."

The document moves from Situation directly to Answer without a Complication. The reader receives a recommendation without understanding what problem or change makes it necessary now.

**Anchor violated:** `minto-p22-scqa`

Minto defines the Complication as the change or tension that makes the Situation unstable. Without it, the Question never arises in the reader's mind — and without the Question, the Answer has no purchase. The reader's natural response is: "Why now? What's wrong with what we have?"

**Typical fix:** Identify the specific event, finding, risk, or constraint that makes the Answer necessary. State it explicitly between the Situation and the Answer. The Complication is the reason the document exists.

**One-sentence rewrite direction:** Insert a Complication sentence identifying what changed or what problem was discovered — the specific trigger that makes CRM migration urgent.

**Why it happens:** Writers who are close to their material take the Complication for granted. They know why the recommendation is urgent, so they skip establishing that urgency for the reader. The result is a recommendation that feels arbitrary or unmotivated to anyone outside the writer's immediate context.

---

## Violation 3 — Buried Governing Thought

**What it looks like:**

> [Two pages of background, analysis, and data tables] ... "In conclusion, we recommend pausing the expansion and redirecting resources to the core product."

The governing thought — the document's central claim — appears at the end, after all supporting material. The reader must process two pages of evidence without knowing what it is evidence for.

**Anchor violated:** `minto-p17-vertical-qa`

The vertical Q/A structure requires the governing thought at the apex: stated first, so that every piece of evidence below it is received as an answer to the question the governing thought raises. When the governing thought is buried, the pyramid is inverted — the reader encounters the base before the apex, which is exactly the structure Minto's framework is designed to avoid.

**Typical fix:** Move the governing thought to the first paragraph. The background and analysis become the pyramid's supporting levels — they remain, but they appear after the claim they support, not before it.

**One-sentence rewrite direction:** State the recommendation ("pause the expansion") in the first paragraph, then let the analysis that follows function as the justification the reader will receive knowing what it supports.

**Why it happens:** The writer used a "build up to the conclusion" structure, reasoning that the reader needs the evidence to accept the recommendation. This reasoning is backwards: the reader needs the claim first so they can evaluate each piece of evidence against it. Building up to a conclusion produces suspense; it does not produce comprehension.

---

## Violation 4 — Mixed-Kind Peer Set

**What it looks like:**

> "Three reasons we should proceed with the acquisition:
> 1. The target has 2.3M active users
> 2. Due diligence should be completed within 60 days
> 3. Competitive pressure from the EU market makes delay costly"

Item 1 is evidence (a fact about the target). Item 2 is a process step (a timeline). Item 3 is a risk-based argument. These are three different kinds of things, not three instances of the same kind.

**Anchor violated:** `minto-p5-pyramid-sorting`

Rule 2 of the pyramid requires that ideas within a grouping be the same kind of thing — all answering the same question-type. This peer set contains a data point (answering "what is the target?"), a process point (answering "how long will it take?"), and a risk point (answering "why now?"). No single parent claim can accurately summarize all three.

**Typical fix:** Separate into valid groupings by kind. The evidence about users belongs in a different grouping from the timeline argument and the competitive-pressure argument. Alternatively, if the intent is three independent reasons, reframe each item to answer the same question: "Why is the acquisition strategically sound?" — then each item should be a reason that answers that question.

**One-sentence rewrite direction:** Pick one question this peer set answers (e.g., "why is acquisition strategically sound?") and revise each item to answer only that question — cutting or relocating items that answer a different question.

**Why it happens:** Writers generate lists by brainstorming what seems relevant, not by first identifying the question the list must answer. The result is a mixed-kind set that cannot have a precise parent summary.

---

## Violation 5 — Non-Exclusive Peers (Overlap)

**What it looks like:**

> "Two factors driving customer churn:
> 1. Low product adoption after onboarding
> 2. Customers are not receiving adequate support during the first 90 days"

Low adoption and inadequate early support are not independent factors — inadequate support during onboarding is a likely cause of low adoption. The two items describe the same phenomenon at different levels of abstraction.

**Anchor violated:** `minto-p96-mece`

Minto's MECE requirement mandates that peers be mutually exclusive: no item should belong in more than one peer. Overlapping items signal that the categorization is too coarse or that a cause/effect relationship has been mistaken for two parallel causes. The parent "Two factors" is false — there may be one factor (inadequate support) with one downstream effect (low adoption).

**Typical fix:** Determine whether the relationship between the items is causal (one causes the other) or parallel (both are independent causes of the same outcome). If causal, restructure vertically: make the root cause the peer-level item and the downstream effect a sub-point. If genuinely parallel, revise to make the distinction crisp.

**One-sentence rewrite direction:** Determine whether inadequate support causes low adoption — if so, state one cause ("inadequate early support drives low adoption") rather than listing a cause and its effect as two separate peers.

**Why it happens:** Brainstormed lists often contain items at different levels of abstraction. Without applying the mutual exclusivity test, the writer inadvertently lists a cause alongside its effect, or describes the same phenomenon from two angles.

---

## Violation 6 — Non-Exhaustive Peers (Missing Item)

**What it looks like:**

> "Three barriers to market entry in Southeast Asia:
> 1. Regulatory complexity in Vietnam and Indonesia
> 2. Local competitor entrenchment in the mid-market
> 3. Currency volatility in the region"

A knowledgeable reader would immediately identify a fourth barrier — distribution infrastructure — that is as significant as any of the three listed. The parent claim ("three barriers") is false.

**Anchor violated:** `minto-p96-mece`

Collective exhaustiveness requires that the peer set account for all relevant instances of the thing grouped, relative to the parent claim's scope. A glaring omission invalidates the parent: if the parent says "the barriers" and the reader immediately identifies a major barrier that is absent, the set is not exhaustive and the parent's claim is wrong.

**Typical fix:** Either add the missing item and revise the parent count, or narrow the parent claim's scope to accurately match the set ("Three regulatory and competitive barriers" excludes infrastructure, making the set exhaustive within its stated scope).

**One-sentence rewrite direction:** Add distribution infrastructure as a fourth barrier, or revise the parent to "three competitive and regulatory barriers" to accurately scope what the set covers.

**Why it happens:** Writers stop listing when they have enough items (typically three) without checking whether the parent's claim of completeness is actually warranted. The fix requires thinking from the reader's vantage point: what would an expert reader immediately flag as missing?

---

## Violation 7 — Mixed Logic Mode

**What it looks like:**

> "We should sunset the legacy API:
> 1. Maintaining two API versions increases engineering overhead by ~40%
> 2. The legacy API accounts for less than 3% of active requests
> 3. Therefore, the cost of maintaining the legacy API far exceeds its usage value
> 4. The new API provides improved rate limits and OAuth 2.0 support"

Items 1, 2, and 3 form a deductive chain (premises → therefore-conclusion). Item 4 is an independent inductive point about the new API's properties. The grouping mixes deductive and inductive logic in one peer set.

**Anchor violated:** `minto-p63-deduction-induction`

Minto's rule is explicit: "The deductive points derive from each other; the inductive points do not." Mixing modes breaks the parent claim — the summary needed for the deductive chain (the "therefore" conclusion) cannot also serve as the inference label for an independent additional point about the new API's features.

**Typical fix:** Separate into two groupings. Keep the deductive chain as its own argument with its own parent (the "therefore" conclusion). Create a second inductive grouping for the benefits of the new API. The governing thought then synthesizes both sub-arguments.

**One-sentence rewrite direction:** Restructure as two groups — one deductive (the cost/usage argument for sunsetting) and one inductive (the benefits of the new API) — each with its own parent claim, both supporting the governing thought.

**Why it happens:** Writers often add supporting material to an argument without realizing they have shifted from a deductive chain to an inductive set. The "moreover" reflex — tacking on additional support after a chain conclusion — is the most common trigger.

---

## Violation 8 — Arbitrary Ordering

**What it looks like:**

> "Key findings from the user research:
> 1. Users find the checkout process confusing
> 2. The mobile app has a 4.2-star rating in the App Store
> 3. Feature requests cluster around notification customization
> 4. Onboarding completion rate is 34%"

No discernible ordering principle explains this sequence. The items are not ranked by importance, are not in time order, are not in structural order (funnel → purchase → post-purchase), and form no deductive chain.

**Anchor violated:** `minto-p5-pyramid-sorting`

Rule 3 of the pyramid requires that ideas within a grouping follow a logical order — one of the four valid orders chosen by the nature of the set. Arbitrary sequence signals that the writer has not determined what kind of set the peers form, which in turn means the parent summary cannot be precise.

**Typical fix:** Identify the most useful order for this specific set. If these are findings ranked by severity, use comparative order (most critical first). If they describe different stages of the user journey, use structural order (awareness → onboarding → purchase → retention). The chosen order should then drive revision of the parent label.

**One-sentence rewrite direction:** Rank findings by severity (highest impact first) or regroup them by stage of the user journey — whichever makes the parent inference accurate.

**Why it happens:** Lists assembled through brainstorming or research aggregation tend to preserve the order in which items were encountered or discovered, not the logical order that serves the reader. Ordering is the last step writers typically apply, and they often skip it when they have "enough" items.

---

## Violation 9 — Container Label Instead of Inference Label

**What it looks like:**

> "**Operational Issues**
> - Server response times have exceeded SLA thresholds 12 times in Q1
> - Two deployment failures required rollback in the past six weeks
> - On-call rotation is understaffed by 40%"

The heading "Operational Issues" tells the reader that there are issues, not what the issues mean or what should be done about them.

**Anchor violated:** `minto-p5-pyramid-sorting`

Rule 1 of the pyramid requires that ideas at any level summarize the ideas grouped below them. A container label like "Operational Issues" names a topic area without asserting anything. It would remain valid regardless of what the child items said. An inference label — the correct form — makes a claim that is specifically true given all three children: e.g., "Three operational failures indicate system reliability has deteriorated to a point that requires immediate remediation."

**Typical fix:** Read all the child items and ask: what do these collectively mean? What claim is true given all of them? That claim becomes the inference label. The inference label must be falsified by changing the children — if it remains valid after changing a child, it is still a container.

**One-sentence rewrite direction:** Replace "Operational Issues" with a claim that the three findings collectively support — e.g., "Q1 operational failures indicate system reliability risk that requires immediate intervention."

**Why it happens:** Container labels are the path of least resistance: they are always true, always acceptable, and require no synthesis. The effort to produce an inference label requires actually reading the children and drawing a conclusion — which is exactly what the Pyramid Principle demands and what most writers defer until they are forced.

---

## Violation 10 — Process Description Substituted for Judgment

**What it looks like:**

> "In Q1, the team conducted 12 customer interviews, synthesized the findings, reviewed them with the product council, and identified three areas of concern. The findings were then presented to leadership."

The document describes what was done rather than recommending what should be done or asserting what the findings mean. The reader finishes the paragraph knowing a process occurred but not what to conclude from it.

**Anchor violated:** `minto-p5-pyramid-sorting`

The governing thought must be a substantive claim — a judgment, recommendation, or finding — not a description of work performed. A process description answers "what happened?" when the reader's question is "what should we do?" or "what does this mean?" Substituting a process description for a governing thought means the pyramid has no apex — it is a flat list of activities with no summary inference.

**Typical fix:** Identify the judgment the process was performed to produce. What did the interviews reveal? What should leadership do with the findings? The governing thought must be that judgment, not the process that produced it.

**One-sentence rewrite direction:** Replace the process description with the conclusion it produced: "Q1 customer research identified three product gaps that require prioritization before the H2 roadmap is finalized."

**Why it happens:** Process-description writing is common in organizations where work product is measured by activity rather than output. Writers document what they did as a form of accountability. The shift to pyramid structure requires claiming ownership of a judgment, which can feel presumptuous. The Pyramid Principle treats that judgment as the entire point of the document.
