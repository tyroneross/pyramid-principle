# Short-Form Patterns

Medium-specific templates with fillable skeletons. Each template defines what it is, when to use it, the structural skeleton with `[SLOT]` placeholders, slot notes, and a brief filled example. All structure follows Barbara Minto's Pyramid Principle applied to short-form artifacts (≤500 words).

Source anchors referenced: `minto-p22-scqa`, `minto-p96-mece`, `minto-p7-magical-number-seven`

---

## Pattern 1 — Exec Summary (Email Memo, <300 Words)

**What it is:** A self-contained executive memo that leads with the governing thought, supports it with three reasons or findings, and closes with an action or decision request. Suitable for leadership audiences who need the conclusion first and read supporting detail only if they choose to.

**When to use:** Sending a recommendation or finding to a senior stakeholder via email. Budget decisions, project gate approvals, vendor selections, staffing recommendations, policy changes. Any situation where the reader's time is limited and the decision or conclusion is the primary cargo.

**Skeleton:**

```
Subject: [Answer in subject line — the governing thought as a declarative phrase]

[Situation sentence] + [Complication sentence]. [Answer sentence — governing thought restated in full].

[Support 1 topic sentence]. [1–2 sentences of evidence or elaboration].

[Support 2 topic sentence]. [1–2 sentences of evidence or elaboration].

[Support 3 topic sentence]. [1–2 sentences of evidence or elaboration].

[Ask line: one sentence stating what action or decision is needed, by when, and from whom.]
```

**Slot notes:**
- **Subject line** — phrase the governing thought as a declarative, not a topic. "Recommend accelerating the Q3 hire" not "Q3 hiring update"
- **Situation** — one sentence of shared context the reader already accepts
- **Complication** — one sentence of the change or tension that makes action necessary
- **Answer sentence** — restate the governing thought in full; do not bury it after the complication
- **Support 1–3** — each a distinct reason, risk, or finding; all same-kind; all MECE (`minto-p96-mece`)
- **Ask line** — specific action, owner, and deadline; not "thoughts?" or "let me know"

**Filled example:**

```
Subject: Recommend pausing the EMEA expansion to protect Q3 margin

The EMEA pilot launched on budget six weeks ago, but last week's revised forecast 
shows it tracking 22% below the revenue target needed to break even by Q4. Pausing 
expansion now recovers $1.4M in committed spend and preserves Q3 margin.

Committed EMEA costs can be redirected within 30 days. The three market development 
contracts renew on rolling 30-day terms and can be suspended without penalty.

The North America pipeline is ready to absorb redeployed resources. Two enterprise 
accounts in final negotiations represent $2.1M in H2 revenue — higher certainty 
than the EMEA projection.

The pause does not close the market; it defers the expansion 6 months while the 
forecast model is recalibrated against real pilot data.

Decision requested by end of week: authorize the pause so contracts can be notified 
before the next billing cycle.
```

---

## Pattern 2 — Decision Memo (Short, <500 Words)

**What it is:** A structured memo that presents a recommended decision, the top reasons supporting it, the primary trade-off accepted, and an implementation note. Leads with the recommendation in the subject line and first sentence. Does not hedge.

**When to use:** Formalizing a decision recommendation for a single approver or small group. Hiring decisions, build-vs-buy choices, vendor selections, policy changes, scope trade-offs. When the decision is binary or has a clear preferred option.

**Skeleton:**

```
Subject: Recommend [recommended option] — decision needed by [date]

[Situation: 1 sentence of shared context]. [Complication: 1 sentence of what changed 
or what forced the decision]. Recommend [option] because [governing reason].

Reason 1: [topic sentence]. [1–2 supporting sentences].

Reason 2: [topic sentence]. [1–2 supporting sentences].

Reason 3: [topic sentence]. [1–2 supporting sentences].

Trade-off: [1 sentence naming what is accepted or given up with this choice, 
and why it is acceptable].

Next step: [specific action, owner, deadline].
```

**Slot notes:**
- **Subject line** — state the recommendation, not the topic. "Recommend Option A" not "Vendor Decision"
- **Governing reason** — the single highest-weight reason, embedded in the opening sentence
- **Reasons 1–3** — independent reasons (not steps, not evidence of one reason); all MECE (`minto-p96-mece`)
- **Trade-off** — name the real cost of the recommendation; omitting trade-offs signals the analysis is incomplete
- **Next step** — one action that moves the decision forward; named owner

**Filled example:**

```
Subject: Recommend Vendor B for the data pipeline contract — decision needed by Friday

Both vendors cleared technical review last month, but Vendor A's implementation 
timeline now conflicts with the Q2 data migration hard deadline. Recommend Vendor B 
because their 6-week delivery window is the only option that keeps the migration 
on track.

Delivery timeline. Vendor B commits to a 6-week end-to-end implementation; Vendor A 
requires 10 weeks. The migration must complete before the Q2 board close.

Total cost of ownership. Vendor B's 3-year contract comes in $180K lower than Vendor A 
when support and integration costs are included.

Reference strength. Three of our current enterprise customers use Vendor B's pipeline 
stack in production; two provided references confirming the 6-week delivery commitment 
has been met in comparable environments.

Trade-off: Vendor B's reporting UI is less mature. The analytics team has reviewed it 
and accepted the gap given that our primary use case is pipeline throughput, not 
self-service reporting.

Next step: Legal needs the draft contract by Wednesday to finalize by Friday. Confirm 
approval so procurement can proceed.
```

---

## Pattern 3 — BLUF Slack / IM Update

**What it is:** A single declarative sentence followed by three bullets. Total length: 4–6 lines. The reader has the answer in 10 seconds. No preamble, no context setup unless the situation is genuinely unfamiliar to the reader.

**When to use:** Status pushes, quick decisions, escalation alerts, "FYI for awareness" drops to a channel, async stand-ins for a sync meeting. When the reader is already in context and the message's job is to surface the conclusion, not build toward it.

**Skeleton:**

```
[Answer sentence — full declarative governing thought.]

- [Support 1 — one line]
- [Support 2 — one line]
- [Support 3 — one line]

[Optional: one-line next step or ask, only if action is required.]
```

**Slot notes:**
- **Answer sentence** — must stand alone; if the reader reads only this, they have what they need
- **Supports** — one clause each; no sub-bullets; not a brain dump; all same-kind (`minto-p7-magical-number-seven`)
- **Next step** — omit if purely informational; include if action is needed

**Filled example:**

```
The infra migration is on track to complete this Friday as planned.

- All 12 services migrated; 3 remaining are low-traffic and scheduled for Thursday night
- No production incidents; rollback was tested and confirmed ready on Tuesday
- Monitoring dashboards are live and showing nominal traffic patterns post-migration

No action needed — will post a completion note Friday.
```

---

## Pattern 4 — Weekly Status Note

**What it is:** A structured three-move update: current state → what changed this period → what's next. Each move is one sentence or one short paragraph. Not a narrative of what happened. Not a list of everything done. A signal to the reader on where things stand and what they need to know.

**When to use:** Weekly or sprint-level updates to a manager, stakeholder group, or team channel. Project health checks. Any recurring status communication where the reader's question is "where do things stand and is there anything I need to act on?"

**Skeleton:**

```
Subject: [Project name] status — [date or period]

State: [One sentence: overall status and the single most important fact about it.]

Changed: [One sentence or short paragraph: what is materially different from last 
period. If nothing changed, say so — don't pad.]

Next: [One sentence or short paragraph: the key action or milestone between now and 
the next update, and who owns it.]

[Optional flag: if there is a decision or blocker that requires the reader's attention, 
state it explicitly on a new line: "Needs: [specific ask]."]
```

**Slot notes:**
- **State** — net health signal plus the one fact that most determines whether the project is on track
- **Changed** — new information only; never repeat what was in the prior update
- **Next** — the most important upcoming milestone or action, not a full task list
- **Needs** — include only if something is genuinely required from the reader; omit otherwise

**Filled example:**

```
Subject: SpeakSavvy iOS status — week of Apr 7

State: Build is green and in external TestFlight review; no blockers to the Apr 14 
release target.

Changed: The pronunciation scoring rubric shipped Wednesday and passed QA; the 
analytics dashboard is live in staging with real session data.

Next: Apple review completes by Apr 10 per average review time; release candidate 
goes to production Friday pending no review flags.

Needs: Confirm whether the App Store listing copy update from Tuesday is approved — 
marketing needs 24 hours to finalize screenshots if changes are required.
```

---

## Pattern 5 — Inbound Request Response (Email)

**What it is:** A reply to a colleague's question or request that leads with the direct answer (yes / no / conditional), states the reasons, and closes with any required action. Does not make the reader wade through context before receiving the answer to their own question.

**When to use:** Responding to any question that has a clear answer: "Can we move the deadline?" / "Should we proceed with the hire?" / "Is the API ready?" / "Do we have budget for this?" Applies whether the answer is yes, no, or conditional.

**Skeleton:**

```
[Answer: Yes / No / Conditional — in the first sentence, with the governing reason.]

[Reason 1: one sentence.]

[Reason 2: one sentence.]

[Reason 3 (if needed): one sentence.]

[Conditional or caveat, if any: one sentence naming what would change the answer.]

[Next step or ask, if any: one sentence.]
```

**Slot notes:**
- **Answer line** — state the answer and the primary reason in one sentence. "Yes — the deadline can move because the vendor dependency resolved." Not "I've looked into this and..."
- **Reasons** — each a distinct reason; all same-kind (reasons, not a mix of reasons + caveats + background)
- **Conditional** — use only if the answer is genuinely conditional; do not hedge for hedging's sake
- **Next step** — include only if action follows from the answer

**Filled example:**

```
Yes — proceed with the hire; the role is funded and the candidate clears the bar.

Budget is confirmed through Q3: the headcount was included in the approved plan 
and finance confirmed available budget last week.

The candidate's technical assessment scored in the top quartile for the role: 
strong systems design, meets bar on the coding portion, no gaps flagged by the panel.

Start date works for the team: the project ramp doesn't require full capacity until 
week 6, which aligns with a May 1 start.

One caveat: the offer needs to go out by Friday to keep the candidate from accepting 
another offer currently in play.

Next step: send the offer letter to legal today for same-day review.
```
