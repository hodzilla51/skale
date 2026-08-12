# SKALE Design

## 1. Problem statement

Japanese legal examinations require large amounts of doctrine, precedent knowledge, issue recognition, fact evaluation, answer construction, and timed legal reasoning.

Conventional study may store and rehearse many of these as partially separate units: individual precedents, model arguments, issue-specific rules, examples, and answer patterns.

SKALE tests whether a substantial portion of that work can be represented and learned more efficiently.

The central question is:

> What is the smallest practical human-executable reasoning system that reaches the required exam performance in the least total learning time?

SKALE is therefore not compression for its own sake. It is an end-to-end learning-system optimization problem.

---

## 2. End-to-end objective

Earlier versions of SKALE emphasized model size. That is insufficient.

A tiny model that takes hundreds of hours to construct is a bad study method.

The primary practical objective is:

```text
minimize:
  T_total = T_build + T_internalize + T_practice

subject to:
  sealed_holdout_performance >= target_performance
  exam_runtime <= allowed_time
```

Where:

- `T_build` = time spent reading sources, extracting structure, organizing models, managing evaluation, and revising artifacts;
- `T_internalize` = time required to deploy the model into the learner;
- `T_practice` = time required to make execution reliable under exam conditions.

Model size, residual count, representation complexity, and retrieval burden are useful only insofar as they affect total time and final performance.

### BuildCost rule

Build time must be logged from the first MVP.

If SKALE improves performance but requires more construction time than the study time it saves, the current implementation fails economically.

If the model is useful but build time dominates, a separate hypothesis becomes testable: whether AI-assisted extraction and organization can reduce `T_build` enough to make SKALE worthwhile.

---

## 3. What SKALE assumes — and what it does not

SKALE assumes that successful legal reasoning uses reusable internal structure. A person who can solve a genuinely unseen problem cannot rely only on exact recall of previously seen questions.

This does not imply that the internal structure is already small, clean, factorized, or consciously accessible.

A successful examinee may rely on a large implicit system containing precedent fragments, doctrinal language, analogies, procedural patterns, repeated practice, and learned intuitions.

SKALE therefore asks:

1. how much of that system is compressible;
2. which representation form fits each subject or problem class;
3. whether the representation can preserve exam-relevant reasoning;
4. whether it can be built and internalized faster than conventional study;
5. whether it can be executed reliably under actual time constraints.

---

## 4. Teacher-signal hierarchy

The examination does not grade precedent recall as an end in itself. It grades the answer produced under the exam's legal and evaluative expectations.

SKALE therefore does not use precedent as the sole or primary teacher signal.

### 4.1 Prior / baseline — textbooks and existing doctrine

Existing legal scholarship and exam-oriented doctrinal structure provide the initial model.

Examples include established requirement-effect structures, balancing frameworks, procedural sequences, and interpretive doctrines.

SKALE should not waste time rediscovering mature legal structures from zero unless evidence shows that the existing representation is inadequate for the exam.

### 4.2 Question-specific target — official question intent

Official explanations of what a question was designed to test provide direct evidence of the intended analytical path.

Use these materials to identify:

- required issues;
- expected legal relationships;
- intended contrasts;
- expected sequence of analysis;
- facts deliberately inserted to trigger evaluation.

### 4.3 Error / discriminative signal — official grading commentary

Official grading commentary is highly valuable but incomplete.

It is not a full teacher label. It is systematically biased toward:

- common omissions;
- shallow treatment;
- formalistic application;
- errors that separated stronger from weaker answers.

What nearly everyone handled correctly may receive little or no discussion.

Therefore:

> doctrinal sources provide the floor; grading commentary provides the error gradient.

Do not construct the entire model from grading commentary alone.

### 4.4 Legal authority — statutes and precedents

Statutes and precedents remain essential.

Their role is to provide:

- positive-law constraints;
- controlling formulations;
- boundary conditions;
- counterexamples;
- legal justification for the model.

They verify and constrain the exam-oriented representation rather than serving as the only source from which the representation must be discovered.

### 4.5 Problems and answers — observations and tests

Past problems are used for training, runtime practice, validation, and sealed evaluation according to their assigned status.

---

## 5. Evaluation protocol comes before model construction

Unseen exam material is a finite resource.

Before substantial model development, assign material to roles.

At minimum:

```text
training
validation
sealed_holdout
runtime_reusable
```

### Training

May be inspected freely and used to build or revise models.

### Validation

May be consumed to select among competing model revisions. Once viewed, it is no longer genuinely unseen and exposure must be recorded.

### Sealed holdout

Reserved for model generalization tests.

Do not inspect its questions, official explanations, grading commentary, AI analyses, or derivative materials during model construction.

A holdout is contaminated if the learner or model builder has materially encountered its content, even indirectly through AI-assisted work.

### Runtime-reusable

Already exposed problems used to test the human execution layer.

These are valuable because human runtime failures can be detected without fresh questions.

Examples:

- model fails to activate;
- activation takes too long;
- correct structure is recalled but the answer remains thin;
- relevant facts are not converted into legal evaluation;
- execution exceeds the time limit;
- learner knows the answer but cannot reproduce the reasoning path closed-book.

Do not waste sealed holdout material merely to test retrieval or fluency.

---

## 6. Two separate performance systems

### 6.1 Model Generalization Performance

Question:

> Does the external SKALE representation correctly structure genuinely unseen legal problems?

This consumes sealed evaluation material.

Possible measures:

- issue coverage;
- required analytical-step coverage;
- quality of legal application;
- fact-evaluation coverage;
- agreement with official question intent and grading criteria;
- stable performance across unseen variants.

### 6.2 Human Runtime Performance

Question:

> Can the learner activate, execute, and render the model under exam conditions?

This can be measured repeatedly on exposed material.

Possible measures:

- activation latency;
- closed-book retrieval success;
- analytical-sequence recall;
- fact-to-legal-evaluation conversion;
- answer completeness;
- execution time;
- delayed retention.

A strong external model with weak runtime performance is not a successful study method.

---

## 7. Shared intermediate pipeline

SKALE should not assume that every subject is best represented as a factor graph.

The shared architecture is instead:

```text
Raw Fact
   ↓
Mediating Legal Reason
   ↓
Legal Representation
   ↓
Reasoning Procedure
   ↓
Answer Rendering
   ↓
Human Runtime
```

The key shared idea is the `Mediating Legal Reason` layer.

### 7.1 Why the mediating layer matters

Do not store brittle mappings such as:

```text
telephoto lens → intrusion high
```

Prefer:

```text
telephoto lens
→ bypasses the subject's practical ability to control exposure
→ increases legal intrusiveness
```

The middle representation is portable to unseen facts such as drones, infrared sensing, remote reconstruction, or another technical mechanism.

It is also efficient because the mediating reason is often exactly the legal evaluation sentence that should appear in the answer.

Thus:

> inference intermediate representation ≈ answerable legal evaluation.

This layer should therefore be treated as a primary compression target.

---

## 8. Subject / archetype backend selection

Different fields may compress into different forms.

Before building a detailed issue model, select the most natural reasoning backend.

Possible initial archetypes include:

### A. Balancing / proportionality / factor backend

Likely useful where multiple legally relevant considerations shift the result directionally.

Typical examples may include constitutional-rights analysis and privacy-like problems.

### B. Requirement-effect backend

Useful where the core task is:

```text
legal claim
→ requirements
→ satisfaction / non-satisfaction
→ legal effect
```

Likely important in civil law and other rule-dense areas.

### C. Procedural-state backend

Useful where reasoning depends on:

```text
current procedural state
→ available procedural operation
→ prerequisites
→ consequence
```

Likely important in procedural law and parts of company law.

### D. Rule / interpretation conflict backend

Useful where competing constructions, rules, or normative bases must be compared and selected.

These categories are initial priors, not sacred taxonomy.

Use established doctrinal structures first. Merge, split, or revise archetypes only when actual exam evidence shows that the initial form is inadequate.

---

## 9. Canonical model

A SKALE model is an external, inspectable artifact. It must not exist only in the learner's head.

A model contains the following components.

### 9.1 Trigger / Router

Defines what observations activate the issue or archetype.

Questions:

- What signals this legal problem?
- Which backend is appropriate?
- Which neighboring doctrines compete?
- What facts distinguish them?

### 9.2 Normative Core

Preserves legal structure that cannot safely be generated from vague intuition.

Possible contents:

- statutory basis;
- claim / right / procedural basis;
- controlling doctrine;
- protected interest or legal purpose;
- required analytical sequence;
- controlling precedent formulation.

### 9.3 Mediating Reasons

Stores reusable legal meanings that convert raw facts into legally operative representations.

For each reason, record where useful:

- underlying legal concern;
- examples of raw facts that instantiate it;
- what it affects downstream;
- answer-language form;
- limits / counterexamples.

The goal is not to memorize every factual indicator. The goal is to learn why classes of facts matter.

### 9.4 Legal Representation Backend

The representation depends on the selected archetype.

It may contain:

- balancing factors and relations;
- legal requirements and effects;
- procedural states and transitions;
- competing rules / interpretations;
- another compact structure justified by the subject.

### 9.5 Decision Procedure

Specifies the order in which the representation is executed.

A representation without an execution procedure is incomplete.

### 9.6 Answer Rendering

Defines how internal reasoning becomes scorable text.

The model should support:

```text
fact citation
→ mediating legal reason
→ legal significance
→ relation to rule / requirement / factor
→ conclusion or counterargument
```

The exam grades the rendered answer, not a hidden internal model.

### 9.7 Residuals

Contains information that currently resists safe compression.

Examples:

- genuinely exceptional precedents;
- numerical thresholds;
- deadlines;
- arbitrary statutory distinctions;
- fixed formulations;
- one-off procedural rules.

Residuals are allowed, but they must not become a dumping ground.

### 9.8 Provenance

Record where practical:

- doctrinal prior;
- official question intent used;
- grading commentary used;
- statutes / precedents;
- training problems;
- counterexamples;
- model revisions;
- known failures;
- AI assistance;
- build time.

### 9.9 Deploy Representation

The canonical model may be too large to execute directly.

Compile it into the smallest human runtime form that still activates the necessary reasoning.

The deploy representation is not the source of truth. It is the human-executable form.

---

## 10. Admission and refactoring rules

Avoid fake precision from weighted complexity formulas that cannot be measured on a common scale.

Use operational rules instead.

### 10.1 Representation-element admission

A candidate factor, requirement distinction, procedural state, or other model element is promoted into the canonical model only if both are true:

1. adding it materially changes the conclusion, analytical path, or answer content across multiple known cases/problems;
2. the learner can recognize and activate it from the problem within practical exam time.

If either condition fails, keep it out of the main representation and treat it as residual, explanatory note, or unnecessary detail.

### 10.2 Residual refactoring

When residuals accumulate, do not simply add more exceptions.

Ask whether several residuals share a missing mediating concept, distinction, backend state, interaction, or scope condition.

Prefer one reusable representation element that absorbs multiple residuals when it passes the admission rule.

---

## 11. Human implementation

The external model and the learner's internal execution system are distinct artifacts.

```text
Canonical SKALE Model
        ↓
Human Compile
        ↓
Deploy Representation
        ↓
Repeated closed-book retrieval and application
        ↓
Fast implicit / automatic skill
```

The final state need not be conscious recitation.

Repeated execution may turn the explicit model into intuition. This is acceptable as long as the external artifact remains inspectable and the learner can still produce the required answer.

---

## 12. Failure diagnosis

When performance is poor, first identify which layer failed.

Possible failure classes:

- teacher-signal error;
- wrong doctrinal prior;
- backend-selection error;
- router failure;
- normative-core error;
- missing mediating reason;
- incorrect legal representation;
- missing interaction / state / distinction;
- answer-rendering failure;
- genuine residual;
- human retrieval failure;
- slow activation;
- execution failure after correct retrieval;
- thin fact evaluation;
- reading error;
- time-management error;
- build cost too high relative to gain.

A failure does not automatically justify a more complex model.

---

## 13. Data discipline

### Pre-answer logs

The learner's answer and reasoning before checking the solution must be preserved unchanged.

Lightweight logs are acceptable:

```text
1 6 一般常識から考えて何となく
2 1 正直分からんがなんとなく
```

Post-answer evaluation is appended separately.

### Exposure history

Record whether a problem is genuinely unseen, previously viewed, practiced repeatedly, or indirectly contaminated.

### Holdout budget

Treat genuinely unseen problems as an evaluation budget.

Do not repeatedly spend fresh material on things that can be tested with exposed problems.

### Legal-version awareness

Older problems may depend on superseded law. Historical questions must not automatically be treated as current-law ground truth.

---

## 14. AI usage

AI may assist with:

- extraction of official examiner signals;
- comparison across years;
- candidate mediating-reason discovery;
- model simplification;
- counterexample generation;
- residual clustering;
- drafting structured artifacts;
- source navigation;
- runtime grading assistance.

AI output is not itself legal authority.

AI can also materially reduce `T_build`, which may be one of the most important practical uses of AI in SKALE.

However, AI exposure to sealed questions can contaminate a holdout. AI usage must therefore be logged whenever evaluation integrity matters.

---

## 15. MVP before expansion

Do not deploy SKALE across all subjects before measuring whether it pays for itself.

The first MVP is **constitutional law only**.

The MVP should measure:

- baseline answer performance;
- SKALE build time;
- internalization time;
- runtime practice time;
- activation speed;
- required-issue coverage;
- fact citation and legal-evaluation coverage;
- answer quality under a fixed rubric;
- sealed-holdout performance;
- delayed runtime performance where useful.

The key question is not merely:

> Did the model become elegant?

It is:

> Did the time spent building and learning SKALE move the learner toward passing performance faster than the alternative use of that time?

If not, identify whether the bottleneck was legal knowledge, issue recognition, answer rendering, runtime speed, or something SKALE did not target.

---

## 16. Strong and weak hypotheses

### Strong hypothesis

A surprisingly large portion of the reasoning needed for the examinations can be represented compactly enough to reduce total time to passing performance dramatically while maintaining or improving unseen-problem performance.

### Weak hypothesis

Even if conventional foundational study remains necessary, explicit modeling and deployment can act as a final compiler that reduces execution errors, improves transfer, and makes passing performance more stable.

Failure of the strong hypothesis does not imply failure of the weak one.

---

## 17. Design principles

> Do not memorize every observation as an independent unit when a smaller representation can regenerate what the exam rewards.

> Do not rediscover mature legal doctrine from scratch when a strong prior already exists.

> Do not optimize model elegance while ignoring the time required to build and deploy it.

> Do not consume genuinely unseen questions to measure failures that exposed questions can already reveal.

> Preserve the reason why a fact matters, not merely a dictionary from fact to conclusion.

> The target artifact is not a theory of law. It is a legally adequate, scorable, human-executable reasoning system for the examination.
