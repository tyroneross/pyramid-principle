# Rules of the Pyramid

Canonical statement of the three structural rules, the four valid logical orders, the magical-number constraint, a worked example, and failure signals. All rules derive from Barbara Minto, *The Pyramid Principle* (2009 revised edition).

Source anchor: `minto-p5-pyramid-sorting`

---

## Why Structure Matters

Minto's foundational claim is that the mind already imposes pyramid structure on information as it arrives. The writer's job is to provide that structure explicitly rather than leaving the reader to construct it:

> The person who seeks to learn what you think about a particular subject by reading what you have to say about it faces a complex task. Even if your document is a short one — say only about 2 single-spaced pages — it will contain roughly 100 sentences. He must take in each of these, digest them, relate them, and hold them together. He will invariably find the job easier if they come to him as a pyramid, beginning at the top and working downward. This conclusion reflects some fundamental findings about the way the mind works. Specifically:
>
> - The mind automatically sorts information into distinctive pyramidal groupings in order to comprehend it.
> - Any grouping of ideas is easier to comprehend if it arrives presorted into its pyramid.
> - This suggests that every written document should be deliberately structured to form a pyramid of ideas.

*(minto-p5-pyramid-sorting)*

This is not a stylistic preference. It is a claim about cognition: pre-sorted structure reduces processing load regardless of content complexity.

---

## The Three Rules

Every valid pyramid must satisfy all three rules simultaneously. Failing any one breaks the logical structure, even if the other two hold.

### Rule 1: Ideas at Any Level Summarize the Ideas Grouped Below

The idea at each level is not a heading or label — it is a substantive claim that the ideas below it collectively prove, explain, or justify. The apex (the governing thought) is the single most important assertion the document makes. Every level below it answers the question that the level above raises.

**What this means operationally:**

- Take any non-leaf node in the pyramid. Remove all its children. The parent idea must still be a complete, meaningful claim — not a category bucket.
- Read the children without the parent. The parent must be the conclusion a reader would naturally draw from reading those children — not merely a label for the topic area they share.
- If the parent says "there are three challenges," that is a container, not a summary. The summary would be: "Three structural challenges make the Q3 launch high-risk."

### Rule 2: Ideas Within a Grouping Are the Same Kind of Thing

Peers on the same level must share a common question-type they answer. A grouping of reasons all answers the question "Why?" A grouping of steps all answers the question "How does it proceed?" A grouping of risks all answers "What could go wrong?"

**The test:** Name the set with a plural noun. If a single plural noun accurately describes every member, the grouping is likely valid. If naming the set requires listing exceptions or qualifications, the grouping contains mixed kinds.

Valid: "three customer acquisition channels" (all answer "what channels exist?")
Invalid: a list containing a channel, a conversion tactic, and a retention metric (they answer three different questions)

### Rule 3: Ideas Within a Grouping Follow a Logical Order

The sequence of peers is determined by the nature of the set, not the writer's convenience. The four valid orders are described in the next section. Arbitrary sequence signals that the writer has not determined what kind of set the peers form — which means the parent summary cannot be precise.

---

## The Four Valid Logical Orders

Apply exactly one order per peer set. The correct order is determined by what the set represents, not personal preference.

### Deductive Order

Use when the set forms a chain of reasoning. Each point follows from the prior. The chain ends in a "therefore" conclusion. The parent summarizes that conclusion. Remove any link and the chain breaks.

Example:
1. All major competitors have reduced prices by 20%+ this quarter.
2. Our current pricing is now 25% above the next closest competitor.
3. Therefore, we are at material risk of accelerating customer churn.

Parent: "Pricing misalignment now poses an immediate churn risk."

### Chronological Order

Use when the set represents a process, action plan, or sequence of events in time. Order is first-to-last. The parent names the outcome that the sequence produces or the process being described.

Example:
1. Conduct stakeholder interviews (weeks 1–2)
2. Synthesize findings into a design brief (week 3)
3. Run design sprint with cross-functional team (weeks 4–5)

Parent: "A three-phase discovery process produces a validated design brief by week 5."

### Structural Order

Use when the set represents parts of a whole — a system, an organization, a geography, a product — arranged spatially or categorically. The parent names the whole. Order follows the structure itself (top-to-bottom, geographic, functional).

Example (describing a product architecture):
1. Data ingestion layer
2. Processing and enrichment layer
3. Delivery and API layer

Parent: "The platform is a three-layer architecture from raw ingestion to API delivery."

### Comparative Order

Use when the set represents options, alternatives, or ranked findings. Order is determined by the ranking criterion (largest to smallest, highest to lowest priority, strongest to weakest case). The parent states the basis of comparison or the leading conclusion.

Example:
1. Option A: automated migration (lowest risk, 12-week timeline)
2. Option B: phased manual migration (medium risk, 8-week timeline)
3. Option C: big-bang cutover (highest risk, 4-week timeline)

Parent: "Three migration options span a risk/speed tradeoff from low-risk 12 weeks to high-risk 4 weeks."

---

## The Magical-Number Constraint

Source anchor: `minto-p7-magical-number-seven`

> What he points out is that the mind cannot hold more than about seven items in its short-term memory at any one time. Some minds can hold as many as nine items, while others can hold only five (I'm a five myself). A convenient number is three, but of course the easiest number is one.
>
> What this means is that when the mind sees the number of items with which it is being presented begin to rise above four or five, it starts to group them into logical categories so that they can be retained.

*(minto-p7-magical-number-seven)*

**Operational rules from this constraint:**

- Prefer 3 items per grouping. Three is the most natural cognitive cluster.
- Up to 5 is acceptable when the items genuinely cannot be categorized further.
- Beyond 5, always look for a valid intermediate categorization. A flat list of 7+ items is almost always a sign that sub-categories exist but have not been identified.
- Never exceed 7. If a peer set has 8+ items, the grouping is broken. Find the sub-structure.

The constraint applies at every level of the pyramid, not only at the key-line level.

---

## Worked Example: From Flat List to Categorized Pyramid

**Original flat list (unstructured):**

To prepare for the product launch, the team must:
1. Brief the sales team on pricing
2. Finalize press release
3. Configure production environment
4. Train support staff on common questions
5. Brief the sales team on competitive positioning
6. Enable feature flags in production
7. Prepare FAQ document for support
8. Coordinate embargo timing with PR agency

**Problems with this list:**
- 8 items exceeds the cognitive limit
- Items span four different functions (sales, PR, engineering, support) with no grouping
- No sequence is implied — chronological, comparative, and structural concerns are mixed
- A parent summary would have to say "eight things to do," which carries no meaning

**Restructured as a pyramid:**

Parent: "Launch readiness requires coordinating four workstreams by Day 0."

Key line:
1. Sales enablement (briefings on pricing and competitive positioning)
2. PR coordination (press release finalization, embargo timing with agency)
3. Technical readiness (production environment configuration, feature flag enablement)
4. Support preparation (staff training, FAQ document)

Now each grouping satisfies all three rules:
- Each sub-group summarizes its children (Rule 1)
- Each sub-group contains like items — all steps within one function (Rule 2)
- The key-line is in structural order, organized by workstream (Rule 3)
- No group exceeds 3 items

---

## Failure Signals

The following patterns indicate a pyramid violation. Use these as a diagnostic checklist when reviewing structure:

**Top doesn't summarize below**
The governing thought is a topic label ("Launch Plan") rather than a claim ("The launch plan depends on resolving three unresolved risks"). If the top can be true regardless of what's below, it isn't summarizing.

**Mixed-kind peers**
The peer set contains items from different question-types: a reason, a step, and a fact appear at the same level. The plural-noun test fails — no single noun accurately names all members.

**Arbitrary sequence**
Peers appear in the order they were thought of, not in a logical order. No single ordering logic (deductive, chronological, structural, comparative) explains the sequence. This usually means the set type hasn't been identified, which means the parent summary can't be exact.

**Unnested list exceeds 5 items**
A flat list with 6+ peers that has not been categorized. Almost always indicates that sub-groups exist but haven't been identified. Re-examine for the plural-noun test at an intermediate level.

**Parent is a container, not an inference**
The parent says "Three issues with the current approach" (container) instead of "Three issues that collectively make the current approach non-viable" (inference). The container carries no logical weight; the inference does.
