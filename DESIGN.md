# SKALE Design

## 1. Problem statement

Japanese legal examinations require large amounts of doctrine, precedent knowledge, issue recognition, fact evaluation, and timed legal reasoning.

Conventional study often stores much of this information as separate units: individual precedents, model arguments, issue-specific rules, and repeated examples.

SKALE tests whether a substantial part of that information is redundant.

The central question is:

> What is the smallest human-executable model that preserves performance on unseen legal problems?

The project is therefore about **compression under a performance constraint**, not summarization for its own sake.

---

## 2. What SKALE assumes — and what it does not

SKALE assumes that successful legal reasoning uses reusable internal structure. A person who can solve a genuinely unseen problem cannot be relying only on exact recall of previously seen questions.

This does **not** imply that the internal structure is already small, clean, or consciously accessible.

A successful examinee may rely on a very large implicit model containing precedent fragments, analogies, doctrinal language, exceptions, repeated practice, and learned intuitions.

SKALE therefore does not ask whether a model exists. It asks:

1. how compressible that model is;
2. whether the compressed representation can remain legally adequate;
3. whether a learner can acquire it more efficiently;
4. whether it can be executed reliably under exam constraints.

---

## 3. Canonical model

A SKALE model is an external, inspectable artifact. It must not exist only in the learner's head.

The canonical model is divided into seven components.

### 3.1 Trigger / Router

Defines what observations should activate the model.

Questions:

- What fact pattern signals this issue?
- What competing models might also be activated?
- What facts distinguish neighboring doctrines?

A model that cannot be reliably retrieved during an exam has little practical value.

### 3.2 Normative Core

Preserves the legal framework that should not be collapsed into mere statistical association.

Possible contents:

- statutory basis;
- doctrinal requirement;
- controlling precedent rule;
- protected interest or legal purpose;
- required analytical sequence.

SKALE may compress this layer where safe, but it does not assume that positive law can always be regenerated from abstract factors.

### 3.3 Factor Graph

Represents outcome-relevant dimensions extracted across cases and problems.

Each factor should ideally record:

- meaning;
- observable factual indicators;
- direction of effect;
- relative importance where supportable;
- interactions with other factors;
- domain limitations.

The model should prefer a small reusable set of factors over one rule per precedent.

### 3.4 Decision Procedure

Specifies how the model is executed.

A factor list alone is insufficient. The learner must know the order in which the legal problem is processed.

Typical form:

```text
identify legal relationship
→ select normative rule
→ identify controlling factors
→ map facts to factors
→ evaluate competing directions
→ process exceptions / counterarguments
→ conclude
```

### 3.5 Residuals

Contains information that cannot currently be generated safely from the compressed structure.

Examples may include:

- genuinely exceptional precedents;
- numerical thresholds;
- procedural deadlines;
- arbitrary statutory distinctions;
- fixed doctrinal formulations;
- domain-specific rules that resist further compression.

Residuals are not a failure by themselves. SKALE explicitly allows irreducible memorization.

The relevant question is how large the residual set must become before compression ceases to be useful.

### 3.6 Provenance / Validation

Every important part of a model should be traceable to its evidence.

Record, where practical:

- source authorities;
- training cases;
- questions that caused revisions;
- counterexamples;
- model version;
- known failures;
- validation performance.

This makes the model debuggable rather than merely intuitive.

### 3.7 Deploy Representation

The canonical model may be too large to execute directly under exam conditions.

A separate deployment representation compresses it into the smallest form the learner actually needs to recall.

Example:

```text
撮影問題
→ 保護領域
→ 態様
→ 必要性
→ 代替手段
→ 公益
```

The deploy representation is not the source of truth. It is the compiled human runtime form of the canonical model.

---

## 4. Human implementation

The external model and the internalized human model are distinct artifacts.

```text
Canonical SKALE Model
        ↓
Human Compile
        ↓
Deploy Representation
        ↓
Repeated retrieval and application
        ↓
Implicit / automatic skill
```

The target end state is not necessarily conscious recitation of the model.

Repeated use may convert an explicit structure into fast intuition. This is acceptable and desirable as long as the external model remains available for inspection and debugging.

The role of the explicit model is therefore partly analogous to an intermediate representation in a compiler: it allows the learner's intuitive model to be inspected, corrected, simplified, and redeployed.

---

## 5. Objective function

SKALE is not optimized for maximum compression alone.

A useful conceptual objective is:

```text
minimize:
  memory_cost
+ execution_cost
+ residual_cost
+ model_complexity

subject to:
  unseen_problem_performance >= target
```

Possible practical metrics include:

- unseen-question accuracy;
- essay issue coverage;
- quality of rule application;
- response time;
- factor count;
- exception count;
- amount of deploy material;
- delayed retention;
- study hours required to reach target performance.

The important comparison is always performance relative to model cost.

---

## 6. Two compression stages

### 6.1 Knowledge Compression

Compresses legal material itself.

```text
precedents + doctrine + problems
→ common structure + residuals
```

### 6.2 Execution Compression

Compresses the canonical model into something a human can retrieve and run quickly.

```text
canonical model
→ deploy representation
→ automatic application
```

A model may succeed at knowledge compression while failing at execution compression. These should be measured separately.

---

## 7. Three levels of evaluation

### Level A — Structural compression

Can many precedents or rules be represented by substantially fewer factors, relations, and residuals?

### Level B — Predictive / analytical generalization

Can the external model explain or correctly analyze unseen cases and exam problems?

### Level C — Human transfer

After learning the deploy representation, can the learner solve unseen problems under realistic exam constraints without consulting the canonical model?

Level C is required to support strong claims about study efficiency.

---

## 8. Failure diagnosis

When an unseen problem is missed, do not immediately create an exception.

First test whether the failure came from:

- router failure — wrong model activated or relevant model not activated;
- normative-core error — wrong legal rule or scope;
- missing factor;
- incorrect factor definition;
- incorrect weighting or direction;
- missing interaction;
- domain-condition failure;
- genuine residual / exception;
- retrieval failure in the learner;
- execution error despite correct retrieval;
- simple reading or time-management error.

Only genuine residuals should increase the exception set.

---

## 9. Data discipline

### Pre-answer logs

The learner's answer and reasoning before checking the solution must be preserved unchanged.

Lightweight logs are acceptable. For example:

```text
1 6 一般常識から考えて何となく
2 1 正直分からんがなんとなく
```

Post-answer evaluation is appended separately.

### Exposure

A problem need not be treated as permanently unusable after one exposure, but exposure history should be distinguishable from genuinely unseen material when evaluating generalization.

### Holdout

Some material should remain unseen for stronger tests. Holdout status should be declared before the model is tested on it.

### Legal-version awareness

Older questions may depend on superseded law. Historical questions must not automatically be treated as current-law ground truth.

---

## 10. AI usage

AI may assist with:

- candidate factor extraction;
- comparison across cases;
- counterexample generation;
- model simplification;
- error diagnosis;
- finding possible interactions;
- grading assistance;
- source navigation.

AI output is not itself legal authority.

Where the experiment is intended to measure the learner or SKALE rather than the AI, use of AI must be logged so that test contamination is visible.

The project should avoid quietly becoming a test of whether an AI model can solve the judicial examination.

---

## 11. Strong and weak hypotheses

### Strong hypothesis

A surprisingly large portion of the knowledge and reasoning needed for the examinations can be compressed enough to reduce conventional study dramatically while maintaining or improving unseen-problem performance.

### Weak hypothesis

Even if conventional foundational study remains necessary, explicit compression and validation can act as a final compiler that reduces execution errors, improves transfer, and makes borderline passing performance substantially more stable.

Failure of the strong hypothesis does not imply failure of the weak one.

---

## 12. Design principle

The core principle is:

> Do not memorize every observation as an independent unit when a smaller structure can explain and regenerate what matters.

But also:

> Do not compress information merely because it can be made shorter. Compress only while preserving the legal performance the examination actually rewards.
