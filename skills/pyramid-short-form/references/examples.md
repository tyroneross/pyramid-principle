# Short-Form Before/After Examples

Five paired examples. Each covers a common short-form structural failure, shows a realistic bad version, identifies the violations with anchor citations, and rewrites to a pyramid-compliant version. All scenarios use realistic professional contexts.

Source anchors referenced: `minto-p22-scqa`, `minto-p96-mece`, `minto-p7-magical-number-seven`, `minto-p5-pyramid-sorting`, `minto-p17-vertical-qa`

---

## Example 1 — Email with Buried Answer

**Scenario:** A product manager emails the VP of Engineering to flag that a third-party API dependency is blocking the Q3 feature launch.

---

**Before:**

> Subject: Update on Q3 feature launch dependencies
>
> Hi Sarah,
>
> I wanted to reach out and provide a quick update on where things stand with the Q3 feature launch. As you know, we've been working through the integration layer over the past few weeks.
>
> The engineering team has been doing a great job navigating the technical complexity here. One of the things that's come up as we've gotten deeper into the implementation is the Stripe webhook API — the version we're building against was deprecated in March and the new version has a different payload shape that requires changes to our event handling logic.
>
> This is going to take some additional engineering time. We're still working through exactly how much. There's also some uncertainty around whether this affects the feature scope.
>
> Happy to chat more about this if helpful.
>
> Thanks,
> Marcus

**What's wrong:**
- **Governing thought is absent** (`minto-p17-vertical-qa`): The email never states a decision or recommendation. "This will take additional engineering time" is a problem description, not a governing thought. The reader finishes the email not knowing what to do.
- **No Complication** (`minto-p22-scqa`): "As you know, we've been working through the integration layer" is Situation padding. The Complication — the deprecated API and its timeline impact — is buried in paragraph 3.
- **Topic-led subject line**: "Update on Q3 feature launch dependencies" is a container label, not a claim. The reader gains nothing from the subject before opening.
- **"Happy to chat" closing**: Signals the writer doesn't have a position. No call to action, no ask, no governing thought recovered at the end. (`minto-p22-scqa`)
- **Mixed content in middle paragraphs**: Team praise, a technical description, a vague consequence, and a scope question — four different things with no structure.

**After:**

> Subject: Q3 feature launch needs a 2-week extension — decision needed by Thursday
>
> The Stripe webhook API we're building against was deprecated in March; migrating to the new version requires rearchitecting our event handler and adds 2 weeks to the implementation. The Q3 ship date is no longer achievable without scope cuts.
>
> Recommend a 2-week extension to August 14. This keeps the feature scope intact and avoids a partial launch that would require a second release cycle within 30 days.
>
> The alternative is cutting the real-time notification component from Q3 scope and launching core functionality on time. This reduces launch risk but splits the feature across two releases.
>
> Need a decision by Thursday so engineering can replan the sprint.
>
> Marcus

**What changed:** The governing thought — "2-week extension recommended" — moved to the subject line and first sentence. The Complication is compressed into one clause of the opening sentence. Two alternatives (extend vs. cut scope) are now explicit and structured. The ask is specific and dated.

---

## Example 2 — Exec Summary That Describes Process Instead of Recommending

**Scenario:** A head of infrastructure writes an exec summary for the CTO recommending a cloud cost reduction initiative.

---

**Before:**

> Executive Summary: Cloud Infrastructure Cost Review
>
> Over the past six weeks, the infrastructure team conducted a comprehensive review of our cloud spend across AWS, GCP, and our legacy data center commitments. The team analyzed usage patterns, identified areas of potential optimization, and benchmarked our spend against industry peers.
>
> Several opportunities were identified in the course of the review. These include reserved instance coverage, idle resource decommissioning, and storage tier optimization. The team also looked at architectural patterns that could reduce inter-region data transfer costs.
>
> The review found that there are meaningful savings available. Work is ongoing to quantify the full opportunity. A follow-up report will be provided once the analysis is complete.

**What's wrong:**
- **No governing thought** (`minto-p17-vertical-qa`): The summary describes the process of the review, not the finding. "Meaningful savings available" is not a claim — it's a placeholder. The reader finishes with no position to evaluate.
- **Situation without Complication** (`minto-p22-scqa`): Six weeks of work is described, but no change or urgency is established. Why does the reader need to act now?
- **Process narration instead of recommendation**: "The team analyzed... identified... looked at..." tells the reader what was done, not what it means. Executive summaries lead with the conclusion.
- **Deferred answer**: "A follow-up report will be provided" is not a governing thought. If the analysis isn't complete, this document should not exist yet — or it should be reframed as a decision on whether to proceed.
- **Container label peer set**: "Reserved instances, idle resources, storage tier, inter-region transfer" — four categories with no parent claim that accurately summarizes the opportunity from all four. (`minto-p96-mece`)

**After:**

> Decommissioning idle resources and restructuring our reserved instance coverage will recover $940K in annualized cloud spend — 18% of the FY25 infrastructure budget — with no impact to production systems.
>
> Idle resources account for $520K of the opportunity. Fourteen environments have had no production traffic in 90+ days; decommissioning takes 30 days and is fully reversible.
>
> Reserved instance coverage accounts for $310K. We are currently on on-demand pricing for 38% of our persistent compute; converting to 1-year reserved instances reduces that cost by 42%.
>
> Storage tier misclassification accounts for $110K. Eleven TB of archive data is stored in hot-access tiers; moving to cold storage has no operational impact and executes in one week.
>
> Recommend authorizing all three initiatives immediately. Total implementation time: 45 days. No engineering capacity required beyond the infrastructure team.

**What changed:** The governing thought — $940K recovery — is in the first sentence. Three MECE supports, all same-kind (cost reduction levers), each with a specific dollar amount and implementation note. The "follow-up analysis" deferral is replaced with a concrete ask.

---

## Example 3 — Slack Update That Mixes Status, Risks, and Decisions in One List

**Scenario:** A project lead posts a channel update on the Travel Planner app's database migration to Neon.

---

**Before:**

> Neon migration update for the team:
>
> - Migration scripts completed and tested in staging ✅
> - We still need to decide on the connection pool size before we go to prod
> - There's a risk that peak traffic spikes could hit the pool limit at launch
> - The Drizzle schema changes are merged and green
> - Someone needs to own the prod cutover runbook — hasn't been assigned
> - Better Auth sessions will need to be invalidated post-cutover and users re-authenticated
> - We're targeting next Tuesday for the prod push

**What's wrong:**
- **Mixed-kind peer set** (`minto-p96-mece`): The list contains status facts (scripts done, schema merged), open decisions (pool size), unassigned tasks (runbook), risks (traffic spikes), technical notes (session invalidation), and a date. Seven items with no single parent claim that accurately summarizes all seven.
- **No governing thought** (`minto-p17-vertical-qa`): The post opens with a topic label ("migration update") not a state claim. The reader can't tell whether the migration is on track, at risk, or blocked.
- **No plural-noun test passes** (`minto-p96-mece`): "Things related to the migration" is the only noun that could contain all seven items, which signals the list is a brain dump, not a structured update.
- **Decisions buried in status list**: The connection pool decision and the runbook ownership gap require action — but they're buried at equal visual weight with completed items.

**After:**

> Neon migration is on track for Tuesday's prod push — two decisions need to be made today.
>
> **Done:** Migration scripts tested in staging, Drizzle schema changes merged and green.
>
> **Decisions needed today:**
> - Connection pool size — no default is safe at our peak traffic estimate; @Tyrone to confirm the ceiling before prod config is locked
> - Runbook ownership — needs a named owner by EOD; @team who's taking it?
>
> **Known ahead of cutover:** Better Auth sessions will be invalidated post-cutover; users re-authenticate on next login. Not a blocker; comms template is ready.

**What changed:** The governing thought ("on track, two decisions needed") opens the post. Three structured groupings — done, decisions, known items — each typed with a same-kind label. Actions have named owners. The reader knows immediately: green status, two things require their response.

---

## Example 4 — Decision Memo Where Reasons Aren't MECE

**Scenario:** An engineering manager writes a memo recommending against promoting a senior engineer to staff level this cycle.

---

**Before:**

> Re: Promotion decision — Alex Chen, Senior Engineer
>
> After reviewing Alex's performance over the past 18 months, I am not recommending promotion to Staff Engineer at this time. The reasons for this recommendation are as follows.
>
> First, Alex has not yet demonstrated consistent cross-team technical leadership. While Alex has done strong work within the payments team, influence beyond the immediate team is a Staff-level expectation.
>
> Second, Alex's recent projects have shown strong technical execution. The refactor of the payments processing service shipped on time and the code quality was excellent.
>
> Third, Alex's impact in cross-functional settings has been limited. In the three cross-functional initiatives this year, Alex participated but did not drive the technical direction.
>
> Fourth, the timing isn't ideal given the team's current workload.

**What's wrong:**
- **Reasons 1 and 3 are not mutually exclusive** (`minto-p96-mece`): "Has not demonstrated cross-team technical leadership" (Reason 1) and "impact in cross-functional settings has been limited" (Reason 3) describe the same underlying gap — failure to lead beyond the immediate team. One is a restatement of the other. The reader can't distinguish them.
- **Reason 2 argues the opposite direction**: "Strong technical execution" is evidence that supports promotion, not against it. Mixing a pro-point into a list of reasons against creates a contradictory parent claim. The list cannot be "reasons not to promote" if one item is a reason to promote.
- **Reason 4 ("timing isn't ideal") is a different kind of thing**: The other reasons are about readiness; this one is about external conditions. Mixed kinds break the MECE requirement. (`minto-p96-mece`)
- **Parent claim can't summarize all four** (`minto-p5-pyramid-sorting`): "Four reasons not to promote" is not true when one reason supports promotion and two repeat the same gap.

**After:**

> Alex is not ready for Staff Engineer this cycle. The gap is cross-team technical leadership — the defining Staff-level distinction Alex has not yet demonstrated.
>
> Alex has not led technical direction in cross-functional settings. In three cross-functional initiatives this year, Alex participated and delivered but did not drive the approach, align the teams, or shape the architecture across group boundaries.
>
> Alex has not built an influence footprint outside the payments team. Staff-level engineers are recognized as technical authorities across at least two teams; no engineer outside payments currently routes technical questions to Alex.
>
> Alex's within-team execution is strong — the payments refactor shipped on time with excellent quality. This cycle is about readiness for the next level, not current performance. The recommendation is to defer with a 6-month development plan focused on cross-team scope.

**What changed:** One governing thought, one defined gap (cross-team leadership), two MECE supports (performance in cross-functional settings + influence footprint), same-kind (both evidence of the same gap from different angles but now scoped differently). The pro-evidence is moved to its correct position — a contextualizing clause that explains the scope of the recommendation, not a competing peer.

---

## Example 5 — One-Pager That Opens with Background and Never Reaches the Answer

**Scenario:** A finance lead writes a one-pager on whether to expand the company's R2 storage contract ahead of the Travel Planner app scaling for summer.

---

**Before:**

> R2 Storage Contract Review
>
> Background
>
> The company has been using Cloudflare R2 for object storage since March 2025, when we migrated from Supabase Storage following the Travel Planner data model overhaul. At the time of migration, the team selected R2 for its egress-free pricing model and regional latency characteristics.
>
> Since then, the Travel Planner app has been in steady growth. Summer camp bookings opened in Q1 and adoption has been ahead of projections. Storage usage has grown 3.1x since the migration.
>
> Current Situation
>
> We are currently on the developer tier of R2, which includes 10GB of storage and 1M class A operations per month. At current growth rates, we will exceed the free tier limits in approximately 6 weeks.
>
> Considerations
>
> There are several factors to consider when thinking about whether to upgrade the R2 plan. Cost is one factor. Another consideration is whether our current architecture is optimal for scale. We should also think about whether there are alternative providers.
>
> The team is currently evaluating these options and will provide a recommendation once the analysis is complete.

**What's wrong:**
- **No governing thought, ever** (`minto-p17-vertical-qa`): The one-pager ends without a recommendation. "Will provide a recommendation once the analysis is complete" means this document should not have been written yet — or the writer is avoiding commitment.
- **Background section before any claim** (`minto-p22-scqa`): Three paragraphs of history before the reader knows what the document argues. The Situation and Complication are present but separated by a header and written as a chronicle rather than compressed preamble.
- **Container-labeled "Considerations" section** (`minto-p5-pyramid-sorting`): "Several factors to consider — cost, architecture, alternatives" is not a key line. These are topic areas, not a MECE peer set with a parent inference. No claim is made about any of them.
- **Plural-noun test fails** (`minto-p96-mece`): "Considerations" is not a valid plural noun. The items inside don't share a question-type.
- **Complication buried under formatting**: The actual urgency — "6 weeks until we exceed the free tier" — is in the middle of the document under a section header, not in the opening sentence where it drives the reader's question.

**After:**

> Upgrade to the R2 paid tier now. At current growth, the Travel Planner app exceeds the free-tier limit in 6 weeks; the paid tier costs $47/month at projected usage and eliminates the risk of service degradation at peak summer traffic.
>
> Timing is fixed. The developer tier caps at 10GB and 1M operations/month. At 3.1x growth since March, we cross both limits around June 1 — peak booking season for summer camps.
>
> Cost is manageable. Projected June usage (32GB storage, 4.2M class A operations) bills at $47/month on the paid tier. No contract commitment; billing scales with usage.
>
> No architecture change required. R2 remains the correct provider; the egress-free model becomes more valuable at scale, not less. The upgrade is a tier change, not a migration.
>
> Recommended action: upgrade the R2 plan this week. Cloudflare applies the upgrade immediately; no downtime or migration required.

**What changed:** The governing thought — "upgrade now" — is the first sentence. The compressed SCQA is woven into the first two sentences (Situation: 3.1x growth since March; Complication: 6 weeks to limit; Answer: upgrade). Three MECE supports, all same-kind (reasons the upgrade is correct), each with a specific fact. The deferred-recommendation ending is replaced with a concrete action.
