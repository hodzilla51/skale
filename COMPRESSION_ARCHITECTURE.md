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

---

## 13. Reasoning Core mutation accounting

A stable Reasoning Core cannot be inferred from unit count alone.

An eight-operation model that is rewritten every year has not converged merely because the number `8` remains unchanged.

Track at minimum, per year and cumulatively:

```text
rc_unit_count
rc_additions
rc_behavioral_edits
rc_splits
rc_merges
```

A claim such as `RC +0` is incomplete unless the edit / split / merge counts for that year are disclosed with it.

### 13.1 No change

Classify an operation as unchanged only when its practical input type, output type, activation boundary, and executable step remain materially the same.

Different problem facts or different legal payloads do not by themselves constitute an RC change.

### 13.2 Behavioral edit

Classify a change as a `behavioral edit` only when all of the following remain materially the same:

- the operation's input type;
- the operation's output type;
- its position as one human-executable cognitive step.

An edit may change or sharpen internal decision criteria, trigger conditions, suppressors, or routing rules inside that same step.

### 13.3 Split

Classify a change as a `split` when a previously single operation must now expose two or more independently meaningful executable stages.

Strong split signals include:

- the input or output type changes;
- a new intermediate representation must be produced;
- one new stage can activate independently of the other;
- one stage must produce an output that a second stage consumes;
- the learner must reliably perform two distinct cognitive actions rather than one sharpened judgment.

Example shape:

```text
old:
  route challenge to rule-level or application-level review

new candidate:
  partition multiple challenged measures
  → then route each measure to rule-level or application-level review
```

This must not automatically be called an edit merely to preserve unit count.

### 13.4 Addition

Classify a change as an `addition` when the new executable operation cannot be represented as an edit or split of an existing operation without changing the existing operation beyond recognition.

### 13.5 Merge

Classify a change as a `merge` only when two or more previously distinct executable operations can be replaced by one human-executable operation without loss of answer quality, activation reliability, or runtime performance.

### 13.6 Conservative tie-break rule

If a change is genuinely ambiguous between `edit` and `split`, classify it as `split` until evidence justifies the narrower edit classification.

This rule deliberately biases against artificially stable RC counts.

### 13.7 Convergence signal

Reasoning convergence requires more than stable unit count.

A stronger signal is:

```text
rc additions ↓
rc edits ↓
rc splits ↓
while frozen-model prediction performance remains adequate
```

A stable count with persistent mutation is evidence that the representation is still moving.

---

## 14. Prospective test protocol and preregistration

Beginning with 2010, SKALE should separate model fitting from teacher-signal testing as much as the historical dataset allows.

### Phase A — Freeze before opening the problem

Before inspecting the target year's problem, commit the current versions of:

- Reasoning Core;
- Legal Knowledge Payload;
- Legal Output Vocabulary;
- Residual set;
- deploy representation if one exists.

The commit is the model version under test.

Do not edit that version after seeing the target problem and still describe the resulting performance as frozen-model generalization.

### Phase B — Problem-only prediction

Open the problem text but do not inspect the official question intent, grading commentary, examiner commentary, model answers, or analyses derived from them.

Before opening teacher signals, commit a prediction artifact containing at minimum:

```text
predicted_rc_path
predicted_major_issues
predicted_required_payload
predicted_unnecessary_or_suppressed_branches
predicted_answer_skeleton
explicit_failure_conditions
```

The purpose is to create a falsifiable prediction, not a flexible note that can later be interpreted as approximately correct.

### 14.1 Explicit failure conditions

The Phase B artifact must state in advance what observations would count as a miss.

Examples:

```text
- If official intent treats X as a major required issue and the prediction omitted X, count a major-issue false negative.
- If the official analytical sequence requires B before A and the frozen model materially depends on A before B, count an ordering miss.
- If a legal payload unit is necessary to generate the expected analysis and was not predicted / available, count a payload false negative.
- If the prediction marks a branch as necessary but official signals show it is materially irrelevant or affirmatively discouraged, count a branch / payload false positive where appropriate.
- If correct handling requires a new reasoning operation or a split not available in the frozen RC, count an RC miss.
```

Failure conditions should be concrete enough that Phase C cannot rescue a prediction merely by saying it was "basically similar."

### Phase C — Open teacher signals and score

Only after Phase B is committed may the official question intent and grading commentary be opened.

Record mismatches under explicit categories such as:

```text
major_issue_false_negative
major_issue_false_positive
ordering_miss
payload_false_negative
payload_false_positive
vocabulary_gap
rc_miss
fact_evaluation_miss
```

A model revision performed after Phase C is a fit to that year. It may improve the model, but the revised model must earn new generalization evidence on a later untouched year.

---

## 15. Payload and vocabulary novelty rates

Absolute cumulative size is not enough to show saturation.

For each year, measure the proportion of that year's required units that were genuinely new to the pre-year frozen model.

### Payload novelty rate

```text
payload_novelty_rate
= new_payload_units
  / (new_payload_units + reused_payload_units_required_this_year)
```

### Vocabulary novelty rate

```text
vocabulary_novelty_rate
= new_vocabulary_items
  / (new_vocabulary_items + reused_vocabulary_items_required_this_year)
```

These denominators count units actually required by the target year, not every unit accumulated historically.

Track both yearly novelty rate and cumulative model size.

A linearly growing payload with persistently high novelty is evidence against the strong compression hypothesis even if the Reasoning Core appears stable.

If novelty remains high after several years, first consider whether the domain is genuinely information-heavy. Only then consider whether unit granularity is too fine. Do not merge units merely because the curve is disappointing.

---

## 16. Merge freeze and evidence rule

Payload, vocabulary, residual, or RC units must not be merged opportunistically in response to model growth.

A merge candidate remains separate until the following minimum evidence exists:

1. the candidate shared inference path has appeared in at least **three independent training years**;
2. it has appeared across at least **two materially different fact patterns**;
3. the proposed common representation uses the same mediating legal reason or executable inference path rather than merely a broad thematic similarity;
4. no unresolved counterexample requires the units to remain distinct;
5. the merged representation preserves answer quality and does not make human activation materially slower or less reliable.

Until these conditions are satisfied, count the units separately even if a common parent concept appears plausible.

### 16.1 Merge-candidate record

Every merge candidate must record:

```text
candidate_units
proposed_parent_or_shared_representation
why_they_might_be_the_same
shared_mediating_reason_or_inference_path
known_differences
supporting_years
supporting_fact_patterns
counterexamples_or_open_questions
```

The field `why_they_might_be_the_same` is mandatory. Later review should be able to distinguish a genuine common inference path from an earlier temptation to group concepts because they sounded related.

### 16.2 Parent concept does not imply merge

Two units may share a broad parent concept and still require separate learner-facing payloads.

For example, several doctrines may relate to personal autonomy while controlling different objects, relationships, or legal questions. The existence of the parent `autonomy` is not itself evidence that the child units can be executed as one rule.

The merge test is functional, not thematic.

### 16.3 Gross additions must never be rewritten

When a validated merge later reduces the current model size, preserve historical growth.

Track separately:

```text
gross_additions_to_date
validated_merges_to_date
current_net_model_size
```

A later merge must not retroactively erase the fact that earlier years introduced separately necessary units at the time.

---

## 17. Anti-hindsight reporting dashboard

For every year from 2010 onward, report at minimum:

```text
REASONING
  frozen RC unit count
  RC additions
  RC behavioral edits
  RC splits
  RC merges
  prediction misses by category

LEGAL PAYLOAD
  reused required units
  new units
  yearly novelty rate
  cumulative gross additions
  validated merges
  current net size

VOCABULARY
  reused required labels
  new labels
  yearly novelty rate
  cumulative gross additions
  validated merges
  current net size

RESIDUALS
  new
  reused
  absorbed by validated representation

GENERALIZATION
  frozen-model result before teacher signals
```

Do not collapse these into a single weighted compression score unless a defensible common scale is later developed.

The experiment should make it easy to see an unfavorable pattern.

Examples of unfavorable but valuable results include:

- stable RC count but persistent edits / splits;
- good issue prediction but continually high payload novelty;
- declining novelty only because post-hoc merges are being performed;
- compact external model that is too abstract to activate under exam time;
- good fit after teacher signals but weak pre-signal prediction.

---

## 18. Transitional rule for the 2009 delta

The 2009 compression delta was measured before the mutation taxonomy and preregistration protocol in Sections 13–17 were fixed.

Therefore:

- its reported `RC +0` is **exploratory evidence**, not preregistered generalization evidence;
- its three reported RC refinements must be re-audited under the new `edit / split / addition` rules before being used in a convergence series;
- the original 2009 record must remain preserved even if reclassification changes the metrics;
- the first prospective historical-year test under the new protocol should begin with 2010.

This prevents later rules from being silently applied only when they improve the appearance of compression.
