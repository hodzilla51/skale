# SKALE Evaluation Protocol

Evaluation is a design input, not an afterthought.

The project has two scarce resources:

1. the learner's study time;
2. genuinely unseen exam material.

Both must be budgeted deliberately.

## 1. Dataset roles

Assign problem sets before substantive model development.

```text
TRAIN
  free to inspect and reuse for construction

VALIDATION
  consumed when choosing among model revisions

SEALED HOLDOUT
  reserved for external-model generalization

RUNTIME REUSABLE
  already-exposed problems used for human execution practice/tests
```

A problem changes status once exposed. Record that change rather than pretending it remains unseen.

## 2. What contaminates a sealed holdout?

Treat a holdout as contaminated when the learner or model-construction process has materially encountered:

- the problem itself;
- its official explanation;
- grading commentary specific to it;
- a detailed solution or reproduction answer;
- AI analysis that reveals its structure or answer;
- derivative notes containing its decisive facts or issues.

Incidental awareness that a particular year exists is not contamination.

## 3. Model Generalization Test

Purpose:

> Determine whether the external SKALE model transfers to genuinely unseen material.

Use sealed material sparingly.

Before opening a sealed problem, freeze:

```text
model version
available deploy representation
allowed materials
expected time limit
rubric / evaluation criteria
```

After the attempt, record:

```text
required issues recovered
analytical steps recovered
raw facts cited
facts converted into legal evaluation
normative errors
reasoning errors
answer-rendering errors
elapsed time
```

Only after freezing the attempt should official examiner material or solutions be opened.

## 4. Human Runtime Test

Purpose:

> Determine whether the learner can actually execute a model under exam conditions.

Fresh material is usually unnecessary.

Prefer exposed problems for repeated runtime checks.

Useful tests include:

- closed-book activation within a fixed number of seconds;
- reproducing the reasoning skeleton from facts;
- converting facts into mediating legal reasons;
- completing an answer within the real time limit;
- repeating after delay;
- executing despite already knowing the eventual conclusion.

Knowing the correct answer does not invalidate a runtime test. If the learner knows the answer but cannot reconstruct the analytical path quickly, that is evidence of a deployment defect.

## 5. Evaluation dimensions

Do not reduce every pilot result to a single fake-precision score.

Track a small number of interpretable dimensions:

```text
Issue coverage
Analytical-step coverage
Fact citation coverage
Fact → legal-evaluation conversion rate
Normative accuracy
Answer completeness
Activation latency
Total execution time
```

When external grading is available, add it without discarding the structural diagnostics above.

## 6. Baseline comparison

The key comparison is not "before model" versus "after model" in the abstract.

Ask:

> Was the time spent building and learning SKALE more valuable than spending the same time on ordinary study and problem practice?

Record:

```text
T_build
T_internalize
T_practice
T_total
performance before
performance after
```

The first MVP need not prove causality perfectly. It must be strong enough to determine whether further investment is rational.

## 7. Constitution MVP

The first subject is constitutional law.

Do not build all subjects in advance.

Suggested sequence:

```text
1. Reserve sealed material.
2. Establish a baseline on non-sealed problems.
3. Read only enough doctrinal material and official examiner material to build a minimal model.
4. Log all build time.
5. Create canonical + deploy representations.
6. Train runtime using exposed problems.
7. Measure runtime failure modes.
8. Run one sealed generalization test.
9. Compare gain against T_total.
10. Decide: expand, redesign, or stop.
```

## 8. MVP continuation criteria

Continue investment when there is credible evidence that SKALE does at least one of the following at reasonable build cost:

- improves required-issue recovery;
- improves fact-to-legal-evaluation conversion;
- reduces execution failures;
- improves answer completeness under time pressure;
- improves unseen-problem performance;
- reduces the practice time needed to reach the same performance.

If the model is strong but construction dominates the economics, test an AI-assisted build process next.

If the model is elegant but answer performance barely changes, investigate whether the targeted reasoning layer was actually the learner's bottleneck.

## 9. First principle

> Spend fresh questions only on questions that genuinely require fresh questions.
