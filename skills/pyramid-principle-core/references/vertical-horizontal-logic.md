# Vertical and Horizontal Logic

Canonical definition of the two structural relationships within a pyramid: vertical (question/answer dialogue) and horizontal (deductive or inductive reasoning). Includes verbatim source quotes, worked examples, and a mixed-logic violation. All rules derive from Barbara Minto, *The Pyramid Principle* (2009 revised edition).

Source anchors: `minto-p17-vertical-qa`, `minto-p63-deduction-induction`

---

## Concept 1: Vertical Logic — Question/Answer Dialogue

### Definition

The vertical relationship is the mechanism by which the pyramid holds the reader's attention and controls what information appears, and when.

Minto's definition:

> The vertical relationship serves marvelously to help capture the reader's attention. It permits you to set up a question/answer dialogue that will pull him with great interest through your reasoning.
>
> What you put into each box in the pyramid structure is an idea. I define an idea as a statement that raises a question in the reader's mind because you are telling him something he does not know.
>
> Making a statement to a reader that tells him something he does not know will automatically raise a logical question in his mind — for example, Why? or How? or Why do you say that? The writer is now obliged to answer that question horizontally on the line below.

*(minto-p17-vertical-qa)*

### How It Works

Every non-leaf idea in the pyramid raises a question. The level immediately below answers it. This is not a loose metaphor — it is the operational rule for placing every piece of information.

**The three reader questions:**

- **Why?** — The reader doubts or wants justification for the claim. The level below must provide reasons.
- **How?** — The reader wants to know the mechanism, process, or method. The level below provides steps or explanations.
- **Why do you say that?** — The reader wants evidence for a claim being made. The level below provides data, examples, or proof.

The writer's job before placing any idea is to ask: "What question does my governing thought raise?" The key-line answers that question. "What question does each key-line point raise?" The next level down answers each of those. This continues until the leaf level, where ideas are either self-evident or reference external sources.

### What Vertical Logic Excludes

The vertical mechanism is as much an exclusion rule as an inclusion rule. Information that does not answer the reader's current question does not belong at that level of the pyramid. It either belongs further down, at a different level, or outside the pyramid entirely.

This is why pyramid documents feel purposeful: every sentence is an answer to the question the prior sentence raised. Nothing is present merely because the writer found it interesting or related.

**Test:** Read only the governing thought. Ask: what question does this raise? Now read the key-line points. Do they collectively and directly answer that question? If a key-line point answers a different question, it is in the wrong place.

### The "Why? / How? / Why do you say that?" Pattern in Practice

Work through the pyramid top-down, using this dialogue at each level transition:

1. State the idea at level N.
2. Ask: what question does this raise in a skeptical reader?
3. The ideas at level N+1 must collectively answer that specific question.
4. If any idea at level N+1 raises a different question from what level N raised, remove it from that grouping.
5. Repeat at each level until the leaf level.

**Example:**

Governing thought: "Our Q3 product launch faces three unresolved risks that could push delivery into Q4."

Reader question raised: *Why do you say that? / What are the three risks?*

Key line:
1. The engineering team has not yet validated the new payment integration.
2. The regulatory filing for the EU market is pending and has an uncertain timeline.
3. Beta testing has surfaced a performance regression that has not been diagnosed.

Each key-line point answers "what is the risk?" — the question the governing thought raised. No point answers a different question (e.g., "what should we do?" or "how did we get here?").

Reader question raised by Point 1: *Why do you say that? / What's the status?*

Next level below Point 1:
1a. Integration testing began two weeks late due to API specification changes.
1b. Current test pass rate is 67%; launch threshold is 95%.
1c. Engineering estimates 3 additional weeks to resolution, which falls after the planned launch date.

Each sub-point answers "what's the evidence that the integration is unvalidated?" — the question Point 1 raised.

---

## Concept 2: Horizontal Logic — Deductive or Inductive Reasoning

### Definition

The horizontal relationship describes how peers at the same level relate to one another and how the parent above them is formed.

Minto's definition:

> Deduction presents a line of reasoning that leads to a 'therefore' conclusion, and the point above is a summary of that line of reasoning, resting heavily on the final point. Induction defines a group of facts or ideas to be the same kind of thing, and then makes a statement (or inference) about that sameness. The deductive points derive from each other; the inductive points do not.

*(minto-p63-deduction-induction)*

A peer group is one or the other — never both. The parent claim is formed differently depending on which mode applies.

### Deductive Horizontal Logic

In a deductive grouping, each point derives from the point before it. The sequence is a logical chain. The parent summarizes the conclusion the chain reaches, resting most heavily on the final point.

**The syllogistic form is the cleanest example:**
- Major premise: a general statement about the world
- Minor premise: a specific observation about the situation at hand
- Conclusion: what follows necessarily from the two premises

**Worked example:**

1. Software vendors are legally liable for security flaws in products used in regulated industries, under the updated DORA framework effective January 2025.
2. Our product is classified as critical infrastructure under DORA and is deployed by three EU financial institutions.
3. Therefore, unpatched security vulnerabilities in our product now create direct legal liability for the company.

Parent: "Unpatched vulnerabilities now create direct legal liability under DORA."

The parent rests on the conclusion (Point 3). Remove Point 1 or Point 2 and the conclusion doesn't follow. The chain is load-bearing: every link matters.

**Key feature of deductive groupings:**
- Order is fixed: you cannot rearrange the points without breaking the logic
- The parent is a restatement of the final "therefore" conclusion
- The reader must accept each prior step to accept the conclusion

### Inductive Horizontal Logic

In an inductive grouping, each point is an independent member of a like set. No point derives from another. The parent makes an inference about what all members have in common — a claim that is true given the set as a whole, not derivable from any single member.

**Worked example:**

1. Customer support tickets mentioning "slow load times" increased 43% month-over-month in March.
2. Average page load time on mobile rose from 2.1s to 3.8s between February and March.
3. Three enterprise clients escalated performance complaints to their account managers in Q1.

Parent: "Performance degradation is now visibly affecting user experience and client relationships."

The parent is an inference — it synthesizes the meaning of the three independent data points. No single point says "performance is visibly affecting client relationships." The inference arises from the pattern across the set.

**Key feature of inductive groupings:**
- Points are independent: rearranging them doesn't break the logic
- The parent is an inference, not a restatement of one point
- Adding or removing a point changes the strength of the inference but doesn't invalidate the structure (as long as the remaining members remain the same kind of thing)

### The Rule: One Mode Per Grouping

A peer set uses deductive logic or inductive logic — never both in the same grouping.

**Why mixing fails:**

A deductive grouping requires the parent to summarize the final conclusion of a chain. An inductive grouping requires the parent to make an inference about a set of like items. If a grouping mixes deductive steps and independent inductive members, no single parent claim can accurately summarize both relationships simultaneously.

### Worked Example of a Mixed-Logic Violation

**The broken grouping:**

Governing thought: "We should adopt a zero-trust security model immediately."

Key line:
1. All major financial-sector breaches in the past two years exploited perimeter-based models. *(inductive — an independent data point)*
2. Our current architecture assumes a trusted internal network. *(inductive — a description of current state)*
3. Therefore, our perimeter model creates the same vulnerability profile. *(deductive conclusion from 1 and 2)*
4. Zero-trust eliminates lateral movement risk by authenticating every internal request. *(inductive — a property of the solution)*

**Why this is broken:**

Points 1, 2, and 3 form a deductive chain. Point 3 is a conclusion that follows from Points 1 and 2. Point 4 is an independent inductive point about the solution's properties.

The parent claim ("adopt zero-trust immediately") has to summarize both the deductive chain (our perimeter model is vulnerable) and the inductive point (zero-trust eliminates lateral movement). These are different relationships. No single governing thought can accurately summarize a chain plus an independent additional fact.

**The fix:**

Restructure into two separate groupings:

First grouping (deductive chain — the problem):
1. All major financial-sector breaches in 2023–24 exploited perimeter models.
2. Our current architecture assumes a trusted internal network.
3. Therefore, our perimeter model creates the same breach vulnerability profile.
Parent: "Our perimeter model exposes us to the same attack vectors that caused recent industry breaches."

Second grouping (inductive — the solution's properties):
1. Zero-trust authenticates every internal request, eliminating lateral movement.
2. Zero-trust provides continuous device posture verification regardless of network location.
3. Zero-trust enables granular access logging for compliance and forensics.
Parent: "Zero-trust eliminates the three attack vectors our current model leaves open."

The governing thought now summarizes two sub-arguments: the problem and the solution. Each sub-argument uses a single, consistent reasoning mode.

---

## Summary: Choosing the Right Mode

| Signal | Use Deductive | Use Inductive |
|---|---|---|
| Points derive from one another? | Yes | No |
| Can you rearrange the points freely? | No | Yes |
| Parent is a "therefore" conclusion? | Yes | No |
| Parent is an inference from a pattern? | No | Yes |
| Removing a point breaks the logic? | Yes | Not structurally |

When uncertain, ask: "Does Point 2 only make sense because Point 1 was stated?" If yes, the grouping is deductive. If Point 2 would stand on its own regardless of Point 1, the grouping is inductive.
