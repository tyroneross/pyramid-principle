# LLM Adaptation

**Modern extension — not in the 2009 source.**

This file applies Minto's Pyramid Principle to the specific failure modes of LLM-generated output and provides prompt patterns that enforce pyramid structure in generation tasks. The rules in this file derive from the canonical framework in `rules-of-pyramid.md`, `scqa-pattern.md`, `vertical-horizontal-logic.md`, and `mece-grouping.md` — but the analysis of LLM-specific failure modes and the prompt engineering techniques are a modern extension with no counterpart in Minto's text.

---

## Why LLM Outputs Violate Pyramid Structure

LLMs trained on general text reproduce the structural patterns of that text. Most text — web articles, forum posts, documentation, email threads — is not written in pyramid structure. It is organized chronologically (background first, conclusion last), topically (grouped by subject area rather than by reasoning logic), or associatively (each sentence follows loosely from the one before). LLMs default to these patterns unless explicitly instructed otherwise.

The result is predictable structural violations:

### 1. Background Before Answer

LLM outputs frequently open with context, history, or qualification before stating the central claim. This is the inverse of answer-first structure. The reader is asked to hold a growing body of context in working memory before being told what it adds up to.

**Pattern:** "X has been a challenge for the industry for several years. Many approaches have been tried. Recent developments include Y and Z. Given all of this, the recommendation is..."

**Pyramid violation:** The governing thought appears last. Everything before it is the SCQA preamble or pyramid support — but in the wrong order. The reader can't evaluate the argument while reading the support, because they don't know the conclusion until the end.

### 2. Weak or Absent Category Labels

LLMs produce bullet lists with container labels or no labels at all. "Key considerations," "important factors," "things to keep in mind" — these are placeholders that carry no inferential content. The items in the list may be individually correct but the list doesn't argue anything.

**Pattern:**
> Key considerations:
> - Cost implications
> - Timeline risks
> - Stakeholder alignment requirements

**Pyramid violation:** No parent inference. The reader cannot evaluate this list because it makes no claim. The reader doesn't know whether these considerations make the proposal viable or unviable, urgent or deferred.

### 3. Mixed Bullets Without a Unifying Question

LLMs produce bullet lists that mix kinds: a reason, a step, an example, and a caveat all appear at the same level, each introduced with a dash. The plural-noun test has no valid answer. The list is associative, not logical.

**Pattern:**
> - The migration requires 6 weeks of engineering time
> - Similar migrations have been completed successfully at Acme Corp
> - Ensure stakeholder buy-in before starting
> - There are three phases: discovery, execution, validation

**Pyramid violation:** No single question-type is answered. The reader cannot form a parent inference because the items don't belong to a common set.

### 4. Evidence Without Inference

LLMs state data and examples without stating the conclusion those data support. The reader is expected to perform the inductive step themselves.

**Pattern:**
> "Customer satisfaction scores declined 12% in Q3. Support ticket volume increased 34%. Three enterprise clients escalated concerns to account managers."

Without the parent inference ("Performance degradation is now visibly affecting customer retention"), the reader has three facts but no structured argument. This is data, not reasoning.

### 5. Deductive-Inductive Confusion

LLMs often produce lists that are structurally ambiguous — they could be read as a deductive chain or as independent inductive members, but neither reading fully holds. The parent claim doesn't accurately summarize the list under either interpretation.

---

## Prompt Patterns That Enforce Pyramid Structure

Each pattern targets a specific violation. Apply them individually or in combination.

### Pattern 1: State the Reader's Question Explicitly

Instruct the model to identify the reader's question before producing any output. The governing thought (Answer) must directly answer this question.

**In-prompt instruction:**
> "Before responding, identify the specific question this document must answer for the reader. State it explicitly in your reasoning. Every claim in the document must ultimately serve as an answer to that question or as support for the answer."

**Why it works:** Forces the model to anchor to a reader-centric question rather than a topic. Prevents associative organization by establishing a logical target from the start.

### Pattern 2: Require Answer-First Output

Explicitly prohibit background-before-answer structure.

**In-prompt instruction:**
> "State the governing thought — the single most important claim — in the first sentence of the document body. Do not open with context, history, or qualification. The supporting detail follows the governing thought, not before it."

**Why it works:** Overrides the default associative pattern. The model must commit to a claim before producing support, which makes it harder to produce vague openings.

### Pattern 3: Require SCQA Introduction When Context Needs Setup

When the reader needs context before the Answer will land, require SCQA structure explicitly.

**In-prompt instruction:**
> "Open with a short SCQA introduction: Situation (what the reader already knows), Complication (what changed or what problem exists), Question (what question the reader now has), Answer (your governing thought). The introduction should be 2–4 sentences. The Answer is the document's central claim — not a summary of the topic."

**Why it works:** Prevents the common error of turning the introduction into an extended background section with no Answer at the end.

### Pattern 4: Require Grouped Supports of One Kind

Force the model to apply the plural-noun test to every bullet list.

**In-prompt instruction:**
> "For every list of supporting points, name the list with a specific plural noun before generating the items. The noun must accurately describe every item in the list. Use forms like 'three risks to...', 'four steps in...', 'two reasons why...'. Do not use container labels like 'key points', 'considerations', or 'factors'."

**Why it works:** Forces the model to commit to a question-type for each list before populating it. Items that don't fit the named kind surface as violations before they appear in the output.

### Pattern 5: Require Explicit Reasoning Mode Declaration

Force the model to label each grouping as deductive or inductive.

**In-prompt instruction:**
> "For each group of supporting points, declare whether the group uses deductive logic (each point derives from the prior; parent is the 'therefore' conclusion) or inductive logic (each point is an independent member of a like set; parent is an inference about the pattern). A group may use one mode only — not both."

**Why it works:** Makes mixed-logic groupings visible. The model must choose a mode and then check that all items conform to it.

### Pattern 6: Require Self-Check Before Returning

Require the model to verify structural validity before finalizing any output.

**In-prompt instruction:**
> "Before returning the response, perform a self-check: (1) Does the governing thought directly answer the reader's question? (2) Does each parent claim accurately summarize the items below it — not just name the topic area? (3) Does each peer set contain only one kind of thing, nameable with a specific plural noun? (4) Does each grouping use a consistent reasoning mode (deductive or inductive, not both)? Fix any violations before returning."

**Why it works:** Self-checking catches violations that instruction-following alone misses. The model evaluates its own output against the structural rules rather than assuming structure was followed.

---

## Reusable Template Skeleton

The following is a fillable skeleton for prompts that must produce pyramid-structured output. Replace bracketed items with task-specific content.

```
You are producing [document type: email / memo / report / presentation outline] for [audience description].

The reader's question is: [specific question in the reader's mind].

Structure requirements:
1. Open with SCQA if context is needed: Situation (shared), Complication (new), Answer (governing thought). Otherwise open directly with the governing thought.
2. The governing thought directly answers the reader's question. State it in the first sentence of the document body.
3. Support the governing thought with [N] key points. Each key point must be the same kind of thing, named by a specific plural noun: [preferred noun if known, e.g. "risks", "steps", "reasons"].
4. Each group of sub-points uses either deductive logic (chain → therefore conclusion) or inductive logic (independent members → pattern inference). Declare the mode for each group.
5. Before returning, self-check: does every parent accurately summarize its children? Does every peer set pass the plural-noun test? Fix violations.

Content constraints: [any topic-specific constraints, e.g. "focus on Q3 execution risks only", "no more than 400 words", "use data from the attached report"].
```

This skeleton is approximately 160 words. Expand or compress based on the model and task. The critical elements are: (1) reader's question stated explicitly, (2) answer-first requirement, (3) plural-noun grouping requirement, (4) deductive/inductive mode declaration, (5) self-check requirement.
