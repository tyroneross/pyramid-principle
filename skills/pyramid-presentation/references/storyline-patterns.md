# Storyline Patterns

Slide-by-slide templates for six common presentation types. Each template names the deck type, when it fits, the logic mode and ordering rule that governs it, typical slide count, and a worked example with assertion-style headlines throughout.

All rules derive from Barbara Minto, *The Pyramid Principle* (2009 revised edition). Source anchors: `minto-p22-scqa`, `minto-p96-mece`, `minto-p63-deduction-induction`, `minto-p17-vertical-qa`.

---

## Template 1: Recommendation Deck

**What it is:** A deck built around a single recommendation that the audience must decide to accept or reject. The recommendation is stated in the opening, before supporting evidence.

**When it fits:**
- Leadership approvals (budget, headcount, vendor selection, architecture change)
- Cross-functional proposals requiring sign-off
- Any situation where the audience holds decision authority and needs a structured case

**Logic mode and order:** Inductive key line. The 3–5 supporting reasons are independent and same-kind (all "reasons the recommendation is sound" or "reasons the current approach fails"). Comparative order within the key line if one reason is stronger than others; structural order if reasons cover distinct domains (financial, operational, strategic).

**Typical slide count:** 8–14 slides.

### Skeleton

| # | Zone | Headline stub |
|---|------|--------------|
| 1 | Opening — Situation | [Context the audience already accepts — current state of system/process/market] |
| 2 | Opening — Complication | [What changed or what risk/gap appeared that makes the current approach insufficient] |
| 3 | Governing Thought | [Recommendation stated directly: "We should [action] by [date] because [governing reason]"] |
| 4 | Key Line | [3–4 reasons this recommendation is sound, listed as asserted phrases] |
| — | SECTION DIVIDER | Reason 1 stated as full assertion |
| 5 | Support for Reason 1 | Specific evidence supporting reason 1 |
| 6 | Support for Reason 1 | Additional evidence if needed |
| — | SECTION DIVIDER | Reason 2 stated as full assertion |
| 7 | Support for Reason 2 | Specific evidence |
| — | SECTION DIVIDER | Reason 3 stated as full assertion |
| 8 | Support for Reason 3 | Specific evidence |
| 9 | Risks and mitigations | [Optional: "Two risks are manageable with existing resources"] |
| 10 | Implementation | [Optional: "Three implementation steps span 8 weeks with no production disruption"] |
| 11 | Closing — Governing Thought | [Restatement of recommendation with earned confidence] |
| 12 | Ask | [Explicit decision required: "We need approval of X by [date] to begin Y"] |

### Notes

Do not bury the recommendation. Audiences that see "Background → Analysis → Recommendation" structure spend the first two-thirds of the deck uncertain whether they are being asked to decide anything. State the recommendation on Slide 3. Audiences can engage critically with a recommendation they've seen — they cannot engage critically with a recommendation they haven't seen yet.

### Worked Example: Infra Proposal

**Context:** Engineering team proposing a migration from single-region to multi-region AWS deployment to the CTO and VP Engineering.

- Slide 1: "All production services run in a single AWS region today, consistent with our early-stage architecture"
- Slide 2: "Three outages in the past six months each traced to single-region dependencies, totaling 14 hours of customer-facing downtime"
- Slide 3: "Migrating to active-active multi-region eliminates the single point of failure responsible for all three outages"
- Slide 4 (key line): "Three factors make this migration viable now: failure risk is quantified, a reference architecture exists, and the 10-week timeline fits the H2 roadmap gap"
- Divider: "Failure risk is quantified and growing — the cost of inaction now exceeds migration cost"
- Slide 5: "Each outage generated $180K in SLA credits; three recurrences would cost more than the full migration project"
- Divider: "A proven reference architecture reduces execution risk to near zero"
- Slide 6: "AWS published a validated active-active pattern for our stack in January; three customers of comparable scale have deployed it"
- Divider: "The H2 roadmap has a 10-week gap that the migration fits without displacing product work"
- Slide 7: "No product sprint is displaced; the migration runs alongside a documentation and debt-reduction quarter"
- Slide 8 (closing): "Migrating to multi-region this quarter prevents recurrence of the three outage patterns that cost us 14 hours of downtime"
- Slide 9 (ask): "Approve the $340K migration budget and 10-week engineering allocation by end of this week"

---

## Template 2: Decision Brief Deck

**What it is:** A deck presenting two or more options to a decision-making audience, with a recommendation stated upfront and options compared directly.

**When it fits:**
- Vendor selection
- Build vs. buy vs. partner decisions
- Architecture or product direction choices where leadership must choose

**Logic mode and order:** Inductive opening (recommendation is the governing thought, stated before options are described). Comparative order for the options section — options are ranked or compared on explicit criteria, not presented neutrally.

**Typical slide count:** 8–12 slides.

### Skeleton

| # | Zone | Headline stub |
|---|------|--------------|
| 1 | Situation | [What decision needs to be made and by when] |
| 2 | Complication | [Why this decision is non-trivial: constraints, tradeoffs, or conflicting priorities] |
| 3 | Governing Thought | ["We recommend Option X because [governing reason]"] |
| 4 | Key Line | ["We evaluated three options on cost, risk, and timeline"] |
| — | SECTION DIVIDER | "Option A: [name] — [one-line characterization]" |
| 5 | Option A profile | Evidence: cost, timeline, risk, fit with constraints |
| — | SECTION DIVIDER | "Option B: [name] — [one-line characterization]" |
| 6 | Option B profile | Evidence: cost, timeline, risk, fit with constraints |
| — | SECTION DIVIDER | "Option C: [name] — [one-line characterization]" |
| 7 | Option C profile | Evidence: cost, timeline, risk, fit with constraints |
| 8 | Comparison | ["Option A dominates on risk; Option B on speed; Option C is viable only if [condition]"] |
| 9 | Rationale for recommendation | ["Option A is recommended because it is the only option that satisfies all three constraints"] |
| 10 | Closing | [Restatement of recommendation] |
| 11 | Ask | [Decision required, owner, deadline] |

### Notes

The comparison slide is the logical center of a decision brief. It names the criteria, shows where each option stands, and states the governing inference ("Option A dominates on risk and cost; Option B only wins if timeline is the sole criterion"). Without this slide, the audience must perform the comparison themselves. The comparison slide does it for them.

The recommendation appears before the options are described — not after. This lets the audience evaluate the options with the recommendation in mind, rather than trying to form their own view before seeing the writer's.

### Worked Example: Auth Platform Selection

**Context:** Product and engineering leadership deciding whether to build, buy, or extend the current auth system.

- Slide 1: "Our current auth system handles 200K users and runs on a 4-year-old custom implementation that predates our B2B segment"
- Slide 2: "The B2B pipeline requires SSO, SCIM, and audit logging — none of which the current system supports without a full rebuild"
- Slide 3: "We recommend purchasing WorkOS to unlock B2B auth requirements within 6 weeks, avoiding a 6-month internal rebuild"
- Slide 4: "We evaluated three paths on delivery speed, total cost over 24 months, and internal engineering load"
- Divider: "Build: fastest learning, slowest delivery, highest engineering load"
- Slide 5: "A full internal rebuild delivers in 6 months, consumes two senior engineers for the full period, and creates ongoing ownership debt"
- Divider: "Buy (WorkOS): fastest delivery, predictable cost, minimal internal footprint"
- Slide 6: "WorkOS delivers SSO, SCIM, and audit logging in 6 weeks at $48K/year with a 3-week integration effort"
- Divider: "Extend current system: lowest upfront cost, high technical risk"
- Slide 7: "Extending the existing system avoids licensing cost but requires 4 months of high-risk refactoring on undocumented legacy code"
- Slide 8: "WorkOS is the only option that meets all three constraints: delivery within 6 weeks, under $50K/year, and no senior engineering burn"
- Slide 9 (closing): "Purchasing WorkOS unblocks 8 enterprise deals in the pipeline and requires 3 weeks of integration work"
- Slide 10 (ask): "Approve the WorkOS contract and assign one engineer to the integration by next Monday"

---

## Template 3: Analytical / Findings Deck

**What it is:** A deck synthesizing research, data analysis, or discovery work into named, asserted insights. The audience is typically a leadership or cross-functional team receiving results they did not run themselves.

**When it fits:**
- User research readout
- Market analysis or competitive landscape
- Internal audit findings
- Any work where the output is "here is what we found and what it means"

**Logic mode and order:** Inductive key line — findings are independent insights, each a named pattern or conclusion. Structural or comparative order within each section, depending on whether the finding describes parts of a system or ranks alternatives.

**Typical slide count:** 10–18 slides.

### Skeleton

| # | Zone | Headline stub |
|---|------|--------------|
| 1 | Situation | [What was studied and why — the research context] |
| 2 | Complication | [What made this question urgent or unresolved] |
| 3 | Governing Thought | ["Three findings from [study] point to a single underlying pattern: [central insight]"] |
| 4 | Key Line | [Named findings, each asserted in one phrase] |
| — | SECTION DIVIDER | Finding 1: full assertion |
| 5–7 | Evidence for Finding 1 | Charts, quotes, or data supporting the finding |
| — | SECTION DIVIDER | Finding 2: full assertion |
| 8–10 | Evidence for Finding 2 | Charts, quotes, or data |
| — | SECTION DIVIDER | Finding 3: full assertion |
| 11–13 | Evidence for Finding 3 | Charts, quotes, or data |
| 14 | Implications | ["These findings imply three changes to [product/strategy/process]"] |
| 15 | Closing | [Governing thought restated with implication framing] |
| 16 | Recommended next steps | [Optional if decisions or actions follow from findings] |

### Notes

Section dividers name the inference, not the data source. "Customer interviews" is a topic label. "Customers overwhelmingly equate 'ease of use' with time-to-first-value, not interface simplicity" is an assertion. The section divider must carry the finding, not the methodology.

Evidence slides within each finding section should be in structural or comparative order — presenting different facets of the same finding, or ranking data points from strongest to weakest signal.

### Worked Example: User Research Readout

**Context:** Product team presenting findings from 22 customer interviews about onboarding drop-off.

- Slide 1: "We interviewed 22 customers across three segments to understand why trial-to-paid conversion has held at 18% for three quarters"
- Slide 2: "Funnel data shows that 61% of trials that don't convert never complete onboarding — but we had no behavioral data explaining why"
- Slide 3: "Three barriers account for the majority of onboarding abandonment, and all three are addressable without a full product redesign"
- Slide 4 (key line): "Barriers: required SSO setup before first value; unclear 'next step' after initial configuration; pricing confusion at the end of trial"
- Divider: "Mandatory SSO configuration at step 3 blocks users who lack admin access to complete setup"
- Slides 5–6: Session recording data + interview quotes showing the SSO drop-off pattern
- Divider: "Users who pass SSO still abandon because no clear 'first win' is signposted after configuration"
- Slides 7–8: Task completion data + quotes showing confusion about what to do next
- Divider: "Trial-end pricing presentation confuses rather than converts — users don't understand what they're being asked to buy"
- Slides 9–10: Click data + interview quotes on pricing confusion
- Slide 11: "All three barriers are removable with targeted changes: SSO deferral, onboarding checklist, and pricing copy revision"
- Slide 12 (closing): "Removing these three barriers could recover a meaningful share of the 61% who abandon before first value"
- Slide 13 (ask): "Approve 6-week sprint to test SSO deferral and onboarding checklist against control group"

---

## Template 4: Strategy Deck

**What it is:** A deck making the case for a multi-horizon strategic direction — typically presented to leadership or board audiences that hold resource allocation authority.

**When it fits:**
- Annual strategic planning
- Product strategy or platform direction
- New market entry or expansion proposals
- Company-level pivots or repositioning

**Logic mode and order:** Inductive key line with structural or comparative order. Strategy decks typically organize around "where we're going + why it wins + how we get there + what it requires." The governing thought is the strategy thesis stated as a single directional claim.

**Typical slide count:** 12–20 slides.

### Skeleton

| # | Zone | Headline stub |
|---|------|--------------|
| 1 | Situation | [Current market position and business context] |
| 2 | Complication | [Market shift, competitive pressure, or internal constraint that makes current trajectory insufficient] |
| 3 | Governing Thought | ["Our strategy for the next 18 months is [direction] — the only move that [outcome claim]"] |
| 4 | Key Line | ["Three pillars: [opportunity thesis], [approach], [resource investment]"] |
| — | SECTION DIVIDER | "The opportunity: [market claim asserted]" |
| 5–7 | Market evidence | TAM, competitive gap, customer signal — each with claim headline |
| — | SECTION DIVIDER | "The approach: [how we win, asserted]" |
| 8–10 | Approach detail | Product moves, GTM, differentiators — each asserted |
| — | SECTION DIVIDER | "The roadmap: [outcome timeline asserted]" |
| 11–13 | Phased roadmap | Each phase named by its outcome, not its activities |
| — | SECTION DIVIDER | "The investment: [resource requirement asserted with ROI framing]" |
| 14–15 | Headcount and budget | Specific and bounded — not "we need more resources" |
| 16 | Expected outcomes | [Asserted OKR-level outcomes, not vague goals] |
| 17 | Closing | [Strategy thesis restated as forward-looking claim] |
| 18 | Ask | [Decision or resource commitment required] |

### Notes

Roadmap slides fail most often by naming activities instead of outcomes. "Phase 1: Discovery and planning" is an activity. "Phase 1 produces a validated architecture decision and a committed vendor by end of Q2" is an outcome. Name each roadmap phase by what it delivers.

The investment section must be specific and bounded. "We will need engineering resources" is not a slide — it is a placeholder. "Six engineers over 12 months and $1.2M in infrastructure investment, with positive unit economics by month 18" is a claim the audience can evaluate.

### Worked Example: Platform Strategy

**Context:** Product leadership presenting a platform consolidation strategy to the executive team.

- Slide 1: "We operate three separate customer-facing products built on divergent tech stacks — a result of two acquisitions in 2023"
- Slide 2: "Customers in our enterprise segment increasingly demand cross-product data integration that our current architecture cannot support"
- Slide 3: "Consolidating onto a unified platform by Q4 is the only path to enterprise-grade integration without a 2-year parallel build"
- Slide 4: "Three pillars: the integration gap is a real and growing customer need; a unified platform is achievable on current infrastructure; a 14-month roadmap delivers this within the planning horizon"
- [Sections follow for each pillar with evidence]
- Slide 17 (closing): "A unified platform positions us as the only vendor in our segment that can deliver cross-product data integration out of the box"
- Slide 18 (ask): "Approve the 14-month platform consolidation roadmap and the reallocation of 4 engineers from product development to platform work"

---

## Template 5: Data Story Deck

**What it is:** A deck built primarily from charts, tables, or quantitative analysis where the argument is carried through a deliberate sequence of data visualizations, each under an assertion headline naming the inference from the data.

**When it fits:**
- Quarterly business reviews
- Performance or metrics readouts
- Analytics or data science presentations
- Research-heavy findings where the primary evidence is quantitative

**Logic mode and order:** Inductive key line. Charts are grouped into sections by the inference each group supports, not by data source or collection order. Comparative order within sections when ranking signals by strength; chronological order when the story is specifically about change over time.

**Typical slide count:** 10–16 slides plus appendix.

### Skeleton

| # | Zone | Headline stub |
|---|------|--------------|
| 1 | Situation | [What metric or question the deck addresses, and the time period] |
| 2 | Complication | [What the data revealed that wasn't expected or that requires action] |
| 3 | Governing Thought | ["The data shows [central finding] — driven by [primary cause]"] |
| 4 | Key Line | [3–4 named insights: each is a claim, not a data category] |
| — | SECTION DIVIDER | Insight 1 as full assertion |
| 5–7 | Charts supporting insight 1 | Each with claim headline — "Chart shows X" is wrong; "X grew 40% in March alone" is right |
| — | SECTION DIVIDER | Insight 2 as full assertion |
| 8–10 | Charts supporting insight 2 | Each with claim headline |
| — | SECTION DIVIDER | Insight 3 as full assertion |
| 11–12 | Charts supporting insight 3 | Each with claim headline |
| 13 | Implications | [What the findings mean for decisions or next steps] |
| 14 | Closing | [Governing finding restated with confidence from evidence] |
| Appendix | Raw data, methodology, additional breakdowns | Not in the argument — available for questions |

### Notes

The single most common data-deck failure: charts grouped by metric type rather than by the question they answer. Revenue charts in one section, engagement charts in another, retention charts in a third. This is data organized by collection method, not by argument. Reorganize by the inference: "Three signals that growth is decelerating" (which might include revenue, engagement, and retention charts in the same section because they all support the same inference).

Headlines on chart slides must name the conclusion, not describe the chart. "Monthly active users by cohort" is a chart label. "Cohort retention has declined four consecutive quarters, driven by users acquired through paid channels" is the claim the chart supports.

### Worked Example: Q3 Performance Review

**Context:** Growth team presenting Q3 business metrics to the executive team.

- Slide 1: "Q3 ended with $4.2M ARR across 380 customers — consistent with our 18-month growth trajectory"
- Slide 2: "New bookings in Q3 fell 22% below Q2, while churn reached its highest rate since Q4 2023"
- Slide 3: "Q3 underperformance traces to a single root cause: a drop in mid-market conversion following the June pricing change"
- Slide 4: "Three metrics confirm the pricing-change hypothesis: new trial conversion, ACV by segment, and churn by cohort all broke trend at the same point"
- Divider: "Trial-to-paid conversion dropped 31% in the week following the June pricing update and has not recovered"
- Slides 5–6: Conversion funnel chart + cohort comparison chart, each with assertion headlines
- Divider: "Mid-market ACV declined 18% while enterprise ACV held, isolating the impact to the price-sensitive segment"
- Slides 7–8: ACV by segment chart + segmented pricing sensitivity data
- Divider: "Churn in Q3 was concentrated in accounts activated between March and June — confirming new pricing is the explanatory variable, not product quality"
- Slides 9–10: Churn by activation cohort + support ticket analysis
- Slide 11: "Reverting the mid-market pricing tier and introducing annual pre-pay incentives is expected to recover 60% of the conversion gap"
- Slide 12 (closing): "Q3 weakness is pricing-driven and addressable — Q4 performance depends on a pricing correction in the next 30 days"
- Slide 13 (ask): "Approve the revised mid-market pricing tier effective November 1"

---

## Template 6: Board / Status Deck

**What it is:** A strategic-level periodic update to a board, steering committee, or senior leadership group. Emphasis on decisions required, flags, and forward-looking signals — not a recitation of activity completed.

**When it fits:**
- Quarterly board updates
- Investor updates
- Executive steering committee reviews
- Any periodic review where the audience holds governance-level authority

**Logic mode and order:** Structural order for the key line (financial, operational, strategic — organized by domain). Within each domain, assertions state the current position and the one forward-looking signal that matters most. Flags and decisions required are isolated explicitly — not buried in performance data.

**Typical slide count:** 8–14 slides (brevity is a feature of board decks, not a constraint).

### Skeleton

| # | Zone | Headline stub |
|---|------|--------------|
| 1 | Situation + Complication (combined) | "[Company name] entered [period] with [position]; [one key development] has changed the outlook for [specific dimension]" |
| 2 | Governing Thought | ["The period's headline: [single most important status claim] — [one decision required]"] |
| 3 | Key Line | [3 domains: financial position, operational status, strategic priorities — each with asserted summary] |
| — | SECTION DIVIDER | "Financial: [asserted financial position]" |
| 4 | Revenue and burn | Specific numbers with YoY or QoQ comparison, assertion headline |
| 5 | Forward indicator | "One financial signal warrants attention: [specific claim about leading indicator]" |
| — | SECTION DIVIDER | "Operations: [asserted operational status]" |
| 6 | Key metric performance | Each metric with claim headline ("NPS held at 72; customer health score declined in enterprise segment") |
| 7 | Risk or flag | "One operational flag requires board awareness: [specific, specific, specific]" |
| — | SECTION DIVIDER | "Strategy: [asserted strategic position]" |
| 8 | Strategic initiatives | Each initiative stated by its current status and the next critical milestone |
| 9 | Decisions required | "[N] decisions require board input this quarter" |
| 10 | Closing | [Period headline restated; forward outlook in one sentence] |

### Notes

Board decks fail most often when they bury the decision in slide 11 of 12. State the governing thought — including the decision required — on Slide 2. The board can then evaluate everything that follows in light of the ask, rather than sitting through twelve slides wondering what they are being asked to do.

Flags and risks belong in dedicated slides, not embedded in performance slides. A risk sentence on Slide 4 in a financial performance section is invisible. A dedicated slide titled "One operational risk warrants board attention this quarter: [specific claim]" is visible and actionable.

Avoid "we are on track" headlines. "On track" is a container label. "Enterprise pipeline coverage hit 3.2x target, positioning Q4 to close $1.8M above plan" is an assertion.

### Worked Example: Q3 Board Update

- Slide 1: "We ended Q3 at $4.2M ARR with solid enterprise growth; a pricing change in June created a mid-market headwind that is now the company's primary near-term risk"
- Slide 2: "Q3 performance was on plan except for mid-market, where a correctable pricing issue requires a board-approved repricing decision today"
- Slide 3: "Three domains: financial position is healthy; operations show one flag; strategy has one decision that can't wait until Q4"
- Divider: "Financial: ARR on plan; one forward indicator warrants attention"
- Slide 4: "$4.2M ARR, 18% QoQ growth — enterprise segment outperformed by $140K; mid-market missed by $310K"
- Slide 5: "New trial starts declined for the second consecutive quarter — a leading indicator that Q4 pipeline is thinner than model assumes"
- Divider: "Operations: NPS stable; one customer health flag in enterprise segment"
- Slide 6: "NPS held at 68 overall; enterprise customer health scores declined for two consecutive quarters in accounts above $50K ARR"
- Slide 7: "One enterprise account representing $420K ARR has escalated to legal review — this is not yet a churn risk but requires board awareness"
- Divider: "Strategy: platform roadmap on track; pricing decision cannot wait"
- Slide 8: "Platform consolidation is 6 weeks ahead of schedule; the team expects beta readiness by November 15"
- Slide 9: "Decision required today: approve revised mid-market pricing tier effective November 1 to arrest the conversion decline"
- Slide 10 (closing): "Q3 is a healthy quarter with one correctable pricing issue; Q4 outcome depends on a pricing decision made this week"
