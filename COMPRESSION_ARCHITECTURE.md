# SKALE Compression Architecture

This document defines what SKALE is actually trying to compress in essay-style legal examinations and how compression progress should be measured across training years.

The central working hypothesis is that an essay answer does not require every learned legal item to exist as an independent memorized unit. A large part of the task may be decomposable into a reusable reasoning system plus a much smaller set of domain-specific legal payloads and output labels.

This is a hypothesis to be tested, not an assumption to be protected from failure.

---

## 1. Four-layer decomposition

For essay questions, separate the learner-facing system into four kinds of information.

```text
Reasoning Core
    +
Legal Knowledge Payload
    +
Legal Output Vocabulary
    +
Residuals
    ↓
Scorable Essay Answer
```

These layers should not be collapsed into one undifferentiated body of "legal knowledge."

### 1.1 Reasoning Core

The reusable procedure for deciding what to do with a problem.

Examples of candidate operations:

- identify the legally relevant actor / right-holder / claim;
- distinguish rule-level and application-level attacks;
- classify the legal relationship or restriction;
- select and justify an analytical framework;
- convert facts into legally meaningful reasons;
- compare purpose, fit, burden, alternatives, requirements, effects, or procedural states as appropriate;
- construct the strongest opposing position;
- render an independently reasoned conclusion.

The Reasoning Core is intended to answer:

> How should I think through this problem?

It should be reusable across many questions and, where evidence permits, across multiple doctrines.

### 1.2 Legal Knowledge Payload

Positive-law or doctrine-specific information that cannot safely be regenerated from general reasoning alone.

Examples:

- constitutional or statutory basis;
- controlling legal rule;
- precedent-specific limitation;
- legally required distinction;
- claim requirements and legal effects;
- special procedural consequence;
- mandatory doctrinal relationship.

The Legal Knowledge Payload is intended to answer:

> What must I know because the legal system specifically says so?

SKALE should attempt to compress this layer by storing shared rules once and representing cases or doctrines as parameters / deltas where possible.

However, arbitrary legal distinctions may remain irreducible.

### 1.3 Legal Output Vocabulary

The canonical legal labels and compact answer-language forms required to express an already-understood idea efficiently and recognizably in an examination answer.

Examples in constitutional-law style problems may include labels such as:

- `表現の自由`
- `内容規制`
- `法令違憲`
- `適用違憲`
- `明確性`

The key distinction is:

```text
semantic understanding != output label
```

A learner may understand:

```text
"the government is restricting it because of what the message says"
```

before learning that the standard legal label is:

```text
内容規制
```

SKALE should therefore avoid requiring specialized vocabulary as the primary representation of the underlying thought when ordinary semantic language is easier to learn and execute.

The preferred mapping is:

```text
ordinary semantic concept
→ canonical legal label
→ concise answer-language form
```

The vocabulary layer is not a substitute for legal knowledge. Knowing the word `内容規制` without knowing when and why it matters is not sufficient.

### 1.4 Residuals

Information that resists safe compression into the first three layers.

Examples:

- genuinely exceptional precedent rules;
- arbitrary statutory distinctions;
- one-off procedural rules;
- fixed numerical thresholds or deadlines;
- special formulations whose wording itself matters;
- rare exceptions that cannot yet be generated from a broader concept.

Residuals are permitted but must be visible.

A growing residual set is evidence against aggressive compression unless later refactoring can absorb multiple residuals into one reusable concept.

---

## 2. Essay minimal-system hypothesis

The strong essay hypothesis is:

> A learner may be able to reach passing-level unseen essay performance primarily by internalizing a compact Reasoning Core and a bounded Legal Knowledge / Vocabulary payload, with only a limited residual set.

In practical terms, the target is not:

```text
memorize hundreds of independent model arguments
```

but something closer to:

```text
small reusable reasoning program
+ compact subject-specific legal payload
+ compact output vocabulary
+ explicit exceptions
```

The project should test whether this architecture can generate scorable answers, not merely whether it looks elegant on paper.

---

## 3. Why vocabulary is measured separately

Specialized legal language may create the illusion of a much larger knowledge space than actually exists.

Three different burdens can otherwise be conflated:

1. understanding the underlying idea;
2. knowing the legal rule attached to that idea;
3. knowing the conventional legal name used to express it.

These should be measured separately.

If the learner already understands the semantic concept, learning its legal label may be closer to a vocabulary-mapping task than to learning an entirely new reasoning structure.

This matters because a large-looking body of legal prose may compress into a comparatively small set of concepts plus labels.

---

## 4. Year-by-year novelty accounting

Every training-year extraction should record how much genuinely new material the year adds to the existing model.

For each year, record at minimum:

```text
new_reasoning_operations
new_legal_payload_units
new_output_vocabulary
new_residuals
```

Also maintain cumulative counts.

Example structure:

```text
Year | New reasoning ops | New legal payload | New vocabulary | New residuals
-----|-------------------|-------------------|----------------|--------------
2008 | baseline          | baseline          | baseline       | baseline
2009 | +?                | +?                | +?             | +?
2010 | +?                | +?                | +?             | +?
```

Do not treat synonyms or stylistic reformulations as new units.

A new unit should be semantically or legally distinct enough that the existing system would fail to generate a materially adequate answer without it.

---

## 5. Saturation hypothesis

A central empirical question is whether the required essay-information space begins to saturate as more years are observed.

A strong compression signal would look like:

```text
new material per year ↓ over time
```

For example, if additional years repeatedly reuse the same Reasoning Core while adding fewer and fewer new legal payload units and output labels, then the effective essay model may be bounded and substantially smaller than conventional study materials suggest.

A weak or failed compression signal would look like:

```text
new reasoning operations remain high
and/or
new legal payload grows roughly linearly with each year
```

If every year requires many unrelated new rules that cannot be merged without loss, the strong SKALE compression hypothesis should be revised downward.

The desired result is not a predetermined low count. The shape of the novelty curve is itself experimental evidence.

---

## 6. Reuse and novelty metrics

Useful diagnostics include:

### Novelty count

How many genuinely new units appear in each layer for the current year?

### Cumulative model size

How many units exist after processing the current year?

### Reuse ratio

What proportion of the year's required analytical work was already representable by the previous model version?

### Residual ratio

What proportion of newly required information could not be safely represented by the current reusable structure?

### Vocabulary saturation

How quickly does the cumulative set of required canonical output labels stop growing?

These metrics are diagnostics rather than a single synthetic score.

Do not invent arbitrary weights to combine incomparable quantities merely to produce one number.

---

## 7. Compression admission rule

When deciding whether two apparently separate items can be merged, ask:

1. Can one shared representation regenerate the legally relevant difference between them?
2. Does the merged representation preserve answer quality on known problems?
3. Can a learner activate the shared representation quickly enough under exam conditions?

If yes, store the common structure once and keep only the necessary differences.

If no, preserve the distinction rather than forcing compression.

The goal is **loss-aware compression**, not the smallest possible document.

---

## 8. Relation to the existing SKALE pipeline

The existing shared pipeline remains:

```text
Raw Fact
→ Mediating Legal Reason
→ Legal Representation
→ Reasoning Procedure
→ Answer Rendering
→ Human Runtime
```

The four-layer decomposition describes what information the learner must possess to execute that pipeline.

A rough correspondence is:

```text
Reasoning Core
  → routing, representation selection, reasoning procedure, reusable answer construction

Legal Knowledge Payload
  → normative core, controlling doctrine, legal requirements / effects / boundaries

Legal Output Vocabulary
  → canonical labels and compact answer-language rendering

Residuals
  → non-compressible or not-yet-compressed legal exceptions
```

The `Mediating Legal Reason` layer remains especially important because it connects raw facts to legal significance and often doubles as the sentence that should appear in the answer.

---

## 9. Human deployment principle

The learner should not be required to think internally in specialized legal vocabulary where a simpler semantic representation is easier to understand and execute.

Preferred deployment pattern:

```text
plain-language trigger / concept
→ legal meaning
→ canonical output label when writing
```

Example:

```text
"the rule itself is the problem"
→ challenge to validity of the rule itself
→ 法令違憲
```

The formal term is still learned. It is simply treated as an output label attached to a understood concept rather than as the entire concept itself.

---

## 10. Scope: essay first

This architecture is currently aimed primarily at essay examinations.

Short-answer examinations may contain a much larger irreducible factual / doctrinal memory component. SKALE may still help there, but success in essay compression does not imply that short-answer knowledge can be reduced to the same degree.

The first experiment should therefore evaluate the essay architecture on constitutional law before making claims about the whole examination.

---

## 11. Immediate implication for training-year extraction

Starting with the next year-level extraction, each observation artifact should distinguish:

```text
A. reusable reasoning operations
B. legal knowledge payload
C. required output vocabulary
D. residual / apparently non-compressible items
```

The 2008 extraction should eventually be backfilled into the same schema so that 2009 can be measured as a true delta rather than another isolated list.

Do not perform cross-year compression before both years have first been extracted independently.

---

## 12. Success signal

The strongest practical signal would be the simultaneous appearance of both trends:

```text
reuse of the same reasoning operations ↑
new legal payload / vocabulary per year ↓
```

If this occurs while unseen-answer performance remains at or above target, the project has evidence that the apparent complexity of essay preparation contains substantial redundancy.

If it does not occur, preserve the negative result and revise the strong compression hypothesis rather than hiding complexity inside vague model labels.
