# Slide Headline Rules

Deep dive on the single most-violated rule in deck construction: every slide headline must assert a claim, not name a topic. Covers the assertion rule, grammar parallelism, length discipline, verb strength, specificity requirements, and ten before/after rewrites.

All rules derive from Barbara Minto, *The Pyramid Principle* (2009 revised edition). Source anchors: `minto-p17-vertical-qa`, `minto-p96-mece`, `minto-p5-pyramid-sorting`.

---

## 1. The Assertion Rule

A slide headline is not a label for the slide's contents. It is a claim the audience can agree or disagree with.

Minto's definition of an idea — applicable directly to slide headlines:

> What you put into each box in the pyramid structure is an idea. I define an idea as a statement that raises a question in the reader's mind because you are telling him something he does not know. Making a statement to a reader that tells him something he does not know will automatically raise a logical question in his mind — for example, Why? or How? or Why do you say that? The writer is now obliged to answer that question horizontally on the line below.

*(minto-p17-vertical-qa)*

A topic-label headline raises no question. "Market Overview" tells the audience that the next slide will contain information about the market. That is all. The audience does not know what to think about the market, what the writer believes about the market, or what the market implies for the decision at hand.

An assertion headline raises a question. "Three competitors entered our primary segment in the past 90 days, cutting our uncontested market share from 40% to 12%" tells the audience exactly what to think — and immediately raises a question: "Why do you say that?" or "So what does that mean for us?" The slide body, chart, or evidence answers that question.

**The operational test:** Read the headline. Can the audience agree or disagree with it? If yes, it is an assertion. If the only possible response is "okay, I see what this section is about," it is a topic label. Rewrite it.

**The second test:** Remove the slide body, chart, and bullets. Does the headline still communicate the point the slide was trying to make? If yes, it is an assertion. If the headline becomes meaningless without the visual, it was a label — the visual was carrying the argument, not the headline.

---

## 2. Parallel Grammar Across Peers

All headline slides within the same peer set — same section, same level — must use the same grammatical form. (`minto-p5-pyramid-sorting`, `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/rules-of-pyramid.md`)

Three valid forms:

**Full sentence headlines:** Subject + verb + object or complement. Most common for assertion-style decks.
> "Mid-market conversion dropped 31% following the June pricing change"
> "Enterprise ACV held steady while mid-market ACV declined 18%"
> "Churn concentrated in accounts activated between March and June"

**Noun-phrase headlines with embedded assertion:** A compressed assertion without a full verb, where the noun phrase itself carries the claim.
> "Three execution risks that block Q3 delivery without intervention"
> "Two pricing levers that recover mid-market conversion within 30 days"
> "One architectural change that eliminates the single point of failure"

**Question-answer pairs:** Used in specific contexts where the audience's question is the frame (more common in board decks).
> "Why did conversion drop? A pricing change isolated to the mid-market segment"

**The rule: one form per peer set.** Do not mix full sentences and noun phrases in the same section. Do not mix question-answer pairs with full sentences. If Slide 5 uses a full sentence headline, Slides 6 and 7 in the same section use full sentence headlines.

Mixed grammar signals mixed logical structure. Parallel grammar signals that the slides are genuinely peers — they belong to the same grouping, answering the same parent question.

---

## 3. Length Discipline

Ideal: under 12 words.
Maximum: under 16 words.

A headline that runs 20+ words is usually a paragraph opener masquerading as a headline. The excess typically falls into one of three categories:

**Qualifications and hedges:** "While results are preliminary and subject to revision, the data seems to suggest that mid-market conversion may have declined following the pricing change." Strip the hedges. Either the claim holds or it doesn't — state the claim.

**Compound claims:** "Mid-market conversion dropped 31% and enterprise conversion held steady and the difference is attributable to the June pricing tier change." Three claims in one headline is three slides trying to occupy one slot. Split them.

**Context that belongs in the SCQA:** "Given that we changed pricing in June and were tracking whether this would affect mid-market accounts specifically, the results show conversion dropped 31% in that segment." The setup belongs in the opening slides. The headline is the finding: "Mid-market conversion dropped 31% in the six weeks following the pricing change."

**When a claim genuinely requires more than 16 words:** Break it into two slides. The first slide states the setup claim; the second states the conclusion. This is almost always a better structure than one overloaded headline.

---

## 4. Verb Strength

Strong verbs make assertions land. Weak verbs signal that the headline is still a topic label in disguise.

**Strong verbs in headlines — use these:**
- grew, declined, dropped, accelerated, recovered
- blocked, enabled, eliminated, caused, drove
- exceeded, missed, hit, fell short of, surpassed
- shifted, reversed, outperformed, underperformed
- confirmed, contradicted, validated, disproved

**Weak verbs that signal topic labels — rewrite these:**
- is, are, was, were (linking verbs — replace with the actual dynamic claim)
- has, have (possession without movement — usually implies a stronger verb exists)
- provides, offers, gives (vague positive claims — name the specific benefit)
- involves, includes, covers (container-label verbs — state the inference instead)
- shows, demonstrates, indicates (weak evidential verbs — make the claim the chart shows)

**Test:** Replace every linking verb ("X is Y") with a dynamic verb ("X grew / declined / shifted / blocked"). If the headline becomes specific and falsifiable with the dynamic verb, the original was a topic label. If the claim is genuinely about a static property ("The API is deprecated"), the linking verb is acceptable — but check whether a dynamic alternative exists ("The API's deprecation blocks all three B2B integrations").

**Example:**

| Original (weak) | Rewritten (strong) |
|---|---|
| "Revenue is growing" | "Revenue grew 28% YoY, ahead of plan for the third consecutive quarter" |
| "The team has capacity concerns" | "Engineering is at 94% allocation — a 6-week slip in any current sprint delays the Q4 launch" |
| "Customer satisfaction shows improvement" | "NPS recovered 12 points in Q3, reversing a two-quarter decline" |

---

## 5. Specificity Over Hedging

Specific claims are stronger than hedged claims. Hedging in a headline signals the writer doesn't trust their own conclusion.

**Specific claims:**
- "Three factors" not "several factors"
- "12% decline" not "significant decline"
- "All five enterprise accounts that churned cited the same issue" not "some enterprise accounts had concerns"
- "Within 6 weeks" not "in the near term"

**Why hedging weakens headlines:**

A hedged headline ("Performance may have declined somewhat in certain segments") signals uncertainty about whether the claim is true. But slide headlines are assertions — they must be claims the writer is prepared to defend with evidence on the same slide. If the evidence is ambiguous enough that only a hedged claim is honest, state the evidence directly ("Conversion data for June–August shows a consistent 20–30% decline across the mid-market segment") rather than asserting a hedged conclusion.

**The exception:** When genuine uncertainty is the point — when the absence of clear data is itself a finding — name the uncertainty specifically. "Three weeks of data are insufficient to determine whether the decline is structural or seasonal" is a specific claim about uncertainty. It is more honest and more useful than "results are mixed."

---

## 6. Before/After Rewrites

Ten topic-label headlines and their assertion rewrites. Each rewrite explains why the fix works.

---

**1. Board deck — financial performance**

| Before | After |
|---|---|
| "Q3 Financial Overview" | "Q3 ARR hit $4.2M — on plan for enterprise, $310K below plan for mid-market" |

*Fix: "Overview" is a container. The after-version states the finding. The audience now knows the financial result and where the gap is before seeing any data.*

---

**2. Product strategy — market position**

| Before | After |
|---|---|
| "Competitive Landscape" | "Three direct competitors entered our segment in Q3, reducing our uncontested market share from 40% to 12%" |

*Fix: "Landscape" names a topic category. The after-version states the specific development and its consequence, which is the actual finding.*

---

**3. Infrastructure proposal — current state**

| Before | After |
|---|---|
| "Current Architecture" | "All production traffic routes through a single availability zone — the source of all three Q3 outages" |

*Fix: A description of "current architecture" tells the audience nothing about why this slide exists. The after-version asserts the architectural fact that creates the problem the proposal addresses.*

---

**4. Research readout — finding section**

| Before | After |
|---|---|
| "User Research Findings" | "Users abandon onboarding at the SSO step because they lack admin credentials at signup time" |

*Fix: "Findings" is a category, not a finding. The after-version states the specific behavioral discovery — the claim the section proves.*

---

**5. Analytics deck — chart slide**

| Before | After |
|---|---|
| "Monthly Active Users by Cohort" | "Cohort retention has declined for four consecutive quarters — new cohorts now churn 40% faster than 2022 cohorts at the same tenure" |

*Fix: "Monthly Active Users by Cohort" describes the chart, not what the chart says. The after-version states the conclusion the chart supports.*

---

**6. Strategy deck — roadmap**

| Before | After |
|---|---|
| "Q4 Roadmap" | "Q4 delivers three milestones that unlock the enterprise pricing tier: SSO, audit logging, and multi-seat billing" |

*Fix: "Q4 Roadmap" is a label for a section of time. The after-version asserts what the roadmap achieves and why it matters for the governing argument.*

---

**7. Decision brief — option comparison**

| Before | After |
|---|---|
| "Build vs. Buy Analysis" | "WorkOS is the only option that meets all three constraints: delivery within 6 weeks, under $50K/year, and no senior engineering burn" |

*Fix: "Build vs. Buy Analysis" describes the activity performed. The after-version states the conclusion the analysis reached — which is what the slide exists to communicate.*

---

**8. Sales pitch — customer benefit**

| Before | After |
|---|---|
| "How Our Platform Helps Teams" | "Teams using this platform resolve incidents 3x faster by eliminating manual triage across 4 disconnected tools" |

*Fix: "How our platform helps teams" is vague positive framing. The after-version states the specific outcome with a specific mechanism — a claim the audience can evaluate.*

---

**9. Status update — risk**

| Before | After |
|---|---|
| "Key Risks and Considerations" | "Two unresolved vendor dependencies put the November launch at risk if not escalated this week" |

*Fix: "Key Risks and Considerations" is a container. The after-version states the specific number, the specific consequence, and the specific urgency — a claim the audience must act on or disagree with.*

---

**10. Closing slide**

| Before | After |
|---|---|
| "Summary and Next Steps" | "The mid-market pricing correction is the single highest-leverage action available to us in Q4 — it requires a decision today" |

*Fix: "Summary and Next Steps" is a procedural label. The closing slide should restate the governing thought — the central argument the entire deck built — not describe what kind of slide it is.*

---

## 7. When a Slide Has No Assertable Headline

Two situations arise where a slide cannot carry an assertion headline:

**Situation A: The evidence is real but the claim isn't formed yet.**

The data exists but the writer hasn't decided what it means. This is a drafting problem, not a slide problem. Stop. Form the claim before building the slide. What is the one conclusion this evidence supports? State that as the headline. If the evidence supports multiple conclusions, pick the one that belongs in this deck's argument and cut the rest (or move them to an appendix).

**Fix:** Ask "What would a smart colleague say about this data if they had 10 seconds?" The answer is usually the headline.

**Situation B: The slide is structural connective tissue with no argumentative content.**

A slide between sections that says "Now let's look at the financials" or "Moving on to the recommendation" has no claim. It is a transition sentence that escaped into its own slide.

**Fix:** One of two options:
1. Absorb the transition into the section divider that follows it. Section dividers open each body section with an assertion; the connective language belongs there.
2. Cut the slide entirely. The argument advances when the next section divider asserts its point — the transition slide adds nothing.

A slide that cannot carry an assertion headline is either a slide that isn't ready (form the claim first) or a slide that doesn't belong (cut it or merge it). There is no third option.
