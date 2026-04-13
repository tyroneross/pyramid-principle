---
name: pyramid-short-form
description: This skill should be used when the user asks to draft, outline, or structure short professional communication — "write an email", "draft a memo", "exec summary", "executive summary", "one-pager", "BLUF", "bottom line up front", "tl;dr this decision", "Slack update", "status note", "brief the team". Produces answer-first structured prose under ~500 words using a compressed SCQA intro (2–3 sentences) and a 3-point key line. Do NOT use this skill for multi-section reports or briefs (hand off to pyramid-long-form), for slide decks (pyramid-presentation), or for reviewing existing content (pyramid-audit).
version: 0.1.1
---

# Pyramid Short-Form

## Purpose

Generate short-form answer-first prose using Barbara Minto's Pyramid Principle. Target output length: ≤500 words. Structure: a 2–3 sentence compressed SCQA intro, a single governing-thought sentence, 2–3 MECE peer supports, and an optional one-sentence next step. Every word earns its place. Nothing runs long to signal effort.

This skill does not audit. It does not explain the Pyramid Principle. It drafts. For full rule grounding, load `pyramid-principle-core`. For violations diagnosis, load `pyramid-audit`.

## When to Invoke / When NOT to Invoke

**Invoke when the artifact is:**
- An email (any length, any audience)
- A Slack or IM update
- A status note, standup summary, or brief team update
- An executive summary or one-pager (standalone, ≤500 words)
- A BLUF or bottom-line-up-front note
- A decision memo that fits on one page

**Do not invoke — hand off instead:**
- Output will exceed 500 words, or requires multiple headed sections → `pyramid-long-form`
- Output is a slide deck or presentation outline → `pyramid-presentation`
- User supplied existing writing and wants structural critique → `pyramid-audit`
- User wants the rules explained before drafting → `pyramid-principle-core`

**The heuristic:** If the reader needs more than one screen of text, or if the communication requires multiple independent argument threads, the artifact is not short-form.

## Intake — Confirm Before Drafting

Before writing a single word, confirm five things. If any are unclear, ask. Do not infer silently.

1. **Reader's question** — What question is the reader trying to answer when they open this? State it in one sentence. "Should we proceed with the vendor change?" is a question. "The vendor situation" is not.
2. **The Answer** — What is the governing thought — the one-sentence claim that directly answers the reader's question? If the user hasn't stated it, surface it explicitly before drafting: "Governing thought: [X]. Proceeding on this basis — confirm or correct."
3. **2–3 supporting points** — What are the peer supports? List all candidates first, then reduce to the 2–3 that are MECE and same-kind. (See §The 3-Point Key Line Rule below.)
4. **Medium** — Email, memo, Slack, one-pager? This affects register and formatting, not structure. Slack gets plain text and bullets. Email memo gets prose paragraphs. One-pager may use light headers.
5. **Constraints** — Word limit, recipient role, required tone, deadline, sensitivity level.

Proceed once all five are confirmed. If the user is in a hurry, tag any inference explicitly: "TAG:ASSUMED — governing thought is X."

## Short-Form SCQA Compression

Short-form compresses all four SCQA moves into 2–3 sentences. In established working relationships where the Situation is fully shared, it can collapse further to Complication + Answer only.

**Compression rule:**
- 1 sentence: Situation + Complication fused ("The Q3 migration slipped two weeks when the vendor confirmed a delivery delay.")
- 0–1 sentence: Question — almost always implicit in short-form; do not state it unless the reader's context is ambiguous
- 1 sentence: Answer — the governing thought, stated directly

The Answer sentence is the most important sentence in the document. It belongs in the subject line (for email), the first sentence of the body, or both. Never bury it past the second sentence. (`minto-p22-scqa`)

For full SCQA treatment — four-move definition, pitfalls, long-form vs. presentation variants — load: `${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md`

## The 3-Point Key Line Rule

Short-form prefers exactly 3 peer supports. The cognitive basis: the mind groups information into MECE categories and retains sets of 3–5 most easily. Three is the most digestible non-trivial count. (`minto-p7-magical-number-seven`)

**Count rules:**
- 2 peers — acceptable; use when the case genuinely has only two limbs
- 3 peers — preferred; the default target
- 4 peers — acceptable; use only if all four are clearly distinct and the parent accurately summarizes all four
- 5+ peers — do not output; collapse into sub-groupings or split into two key lines

**All peers must pass the plural-noun test** — name the set with a plural noun before writing. "Three reasons the launch is at risk" is valid. "Three things to note" is not. (`minto-p96-mece`)

**All peers must be same-kind** — reasons, or risks, or recommendations, or steps. Never mix kinds in one key line. A grouping of one recommendation, one piece of evidence, and one context note is not a valid peer set — it has no single parent claim that accurately summarizes all three.

**MECE check before proceeding:**
- Mutually exclusive: no two peers describe the same underlying phenomenon
- Collectively exhaustive: no significant peer is missing given the parent claim

## Prose or Bullets? Choose by Structure

Short-form supports render as either prose paragraphs or bullet points. The choice is not stylistic. It follows from how many peers the key line has and how independent they are.

**Decision rule:**

- **Prose** when the key line has 1–2 supports, or when supports flow sequentially and benefit from connective tissue. A short email with one main reason and a brief rationale reads better as paragraphs. Bullets fragment prose that is already scannable.
- **Bullets** when the key line has 3–7 same-kind supports that are independently assertable. Especially when several supports need to stand on their own. Bullets expose the peer set structurally so the reader sees the shape of the argument at a glance.
- **Hybrid** is the common middle ground. Open with one sentence stating the Answer, bullet the key line with complete-sentence supports, close with a sentence naming the next step.

**Grounding in the Pyramid Principle.** The mind groups pre-sorted items of 3–7 most easily (`minto-p7-magical-number-seven`). Below that threshold, bulleting imposes structure on content that does not need it. Above the threshold, the set needs categorizing rather than flat bulleting, which in short-form usually means the artifact should be long-form instead. Every peer set, whether in prose or bullets, must still satisfy MECE and the plural-noun test (`minto-p96-mece`).

**Bullet discipline, when bullets are chosen:**

- Each bullet is a complete sentence with a subject, verb, and claim. Not a fragment. Not a noun phrase. A bullet reading "Cost reduction" is a topic label, not a support.
- Each bullet answers the same implicit question raised by the Answer sentence above it. "Why should I agree?" or "How does this work?" or "What are the risks?"
- Parallel grammar across the bullets in one set. All declarative sentences, or all imperative, or all subject-first. Do not mix.
- Do not use bullets when you have only one or two supports. Two bullets look structurally impoverished; the prose version reads as confident.

**Prose discipline, when prose is chosen:**

- Each support is one short paragraph: 2–4 sentences, leading with the claim.
- The first sentence of each paragraph is the point that paragraph proves. Evidence and elaboration follow.
- Section transitions are implicit. Prose short-form is too compact for explicit "Next, ..." connectives.

## Output Shapes

Four standard short-form shapes. Choose based on medium and purpose. Within each shape, render supports as prose or bullets per the decision rule above.

### BLUF (Slack, IM, exec alert)

For rapid reader decisions in 30 seconds or less. Bullets almost always. The medium expects scanning, and the 3-point key line is precisely the case the bullet rule serves.

```
[Answer sentence: the governing thought, full and declarative]

- [Support 1, complete sentence]
- [Support 2, complete sentence]
- [Support 3, complete sentence]
```

No preamble. No sign-off. If context is genuinely needed, add one Complication sentence before the Answer.

### Exec Summary / One-Pager (email memo to leadership)

Compressed SCQA, Answer, 3 supports, optional next step. Total under 500 words. Support format depends on count and independence:

- **1–2 supports**: render as prose paragraphs. Example: a recommendation email where the governing reason has one main justification and a short risk note.
- **3–7 supports**: render as bullets, each a complete sentence. Example: an exec summary recommending a migration with three MECE reasons (cost, quality, risk profile).
- **Hybrid**: opening sentence states the Answer, bullets expose the key line, closing sentence names the ask or next step. This is often the cleanest form for email.

### Decision Memo (short)

Same shape as exec summary. The Answer explicitly frames the recommended decision: "Recommend [X] because [governing reason]." Supports follow the decision rule above. Add one sentence flagging the trade-off accepted.

### Status Update

Structured form of SCQA: What's the state, what changed, what's next. Each move is one sentence or one short paragraph. Not a narrative. Not a brain dump. Each move answers its question and stops. Status updates often fit the bullet rule when "what changed" and "what's next" have 3 or more items each.

## Drafting Workflow

Execute these steps in order. Do not assemble until step 5.

1. **Write the reader's question** — on a scratch line, in one sentence. This is a drafting tool; it may not appear in the output.
2. **Write the Answer** — one declarative sentence. This is the governing thought. Everything else exists to support it.
3. **List all candidate supports** — write every relevant point without filtering. Then reduce to the 2–3 that are MECE and same-kind. Discard the rest; they may belong in a follow-up or a reference, not in this artifact.
4. **Compress the SCQA** — write the 1–2 sentence intro. Situation + Complication. Question implicit. Answer stated on the next line.
5. **Assemble in order:** SCQA intro → Answer sentence → 3 supports → (optional) next step.
6. **Check the word budget** — if over 500 words, cut evidence, not structure. Trim the support paragraphs, not the key line.

## Self-Check Before Returning

Run these six gates before returning any output. Do not skip. For a full structural audit, direct to `pyramid-audit`.

1. **Answer in position.** Is the governing thought in the subject line or first body sentence? If it appears past the second sentence, move it.
2. **Peers are MECE and same-kind.** Name the peer set with a plural noun. Does the noun accurately describe every peer? Do any two peers describe the same underlying thing?
3. **SCQA does its job.** Does the opening establish a Situation, a Complication, and make the Answer's necessity obvious, even compressed to 2 sentences?
4. **Prose-vs-bullets matches the peer count.** Did the shape follow the decision rule? 1–2 supports as prose, 3–7 as bullets, complete sentences either way.
5. **Every sentence earns its place.** Read each sentence and ask: "If this were deleted, would the reader have everything they need?" If yes, delete it.
6. **First-sentence test.** If the reader only reads the first sentence, do they have the answer? If not, the governing thought is buried.

## Common Short-Form Mistakes

**Topic-led opener.** "This email is to provide an update on the Q3 launch status." The first sentence consumes the reader's attention and delivers no claim. Replace with the Answer.

**Answer hidden behind process.** "After reviewing the three vendors in detail, weighing cost, timeline, and support quality, we have arrived at a recommendation." The reader has now waited through 22 words to receive nothing. Start with the recommendation.

**Mixed-kind bullet list.** Bullets that include a recommendation, a piece of evidence, a risk, and a next step — four different question-types in one list. The parent claim cannot accurately summarize them. (`minto-p96-mece`) Split into typed groupings or convert to prose with clear structure.

**"Thoughts?" ending.** No governing thought, no call to action, no answer to the reader's real question. Every short-form artifact must close with a next step or a clear position — not an invitation for the reader to fill the structural gap.

**Complication-less opener.** Starting with the Answer before any Situation or Complication has been established. The Answer lands without weight because the reader doesn't know what changed. Two sentences of compressed SCQA make the Answer hit harder. (`minto-p22-scqa`)

## Additional Resources

- **`references/patterns.md`** — Medium-specific fillable templates for exec summary, decision memo, BLUF, status update, and inbound request response
- **`references/examples.md`** — Five paired before/after examples showing common short-form failures and their pyramid-compliant rewrites

Canonical rule detail:

```
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/scqa-pattern.md
${CLAUDE_PLUGIN_ROOT}/skills/pyramid-principle-core/references/mece-grouping.md
${CLAUDE_PLUGIN_ROOT}/docs/source-anchors.md
```
