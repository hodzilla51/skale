# SKALE Model Template

Use one copy of this template for each issue/domain model. Keep the canonical model explicit; keep the deploy representation aggressively small.

## Metadata

```text
id:
subject:
domain:
archetype:
version:
status: draft | validating | stable | deprecated
created:
updated:
build_time_minutes:
```

## 1. Teacher Signals / Prior

```text
Doctrinal prior / textbook structure:

Official question intent used:

Official grading commentary used:

Statutes / precedents / authorities:

Important caveat about missing teacher signal:
```

Remember: grading commentary is usually an error / discriminative signal, not a complete description of everything a competent answer must contain.

## 2. Trigger / Router

```text
Trigger facts / issue patterns:

Selected reasoning backend:

Neighboring models:

Routing distinctions:
```

## 3. Normative Core

```text
Statutory / doctrinal basis:

Claim / right / legal relationship:

Controlling rule:

Protected interest / legal purpose:

Required analytical sequence:
```

## 4. Mediating Legal Reasons

Store why classes of facts matter, not a brittle dictionary from fact to outcome.

```text
M1:
  legal meaning:
  example raw facts:
  downstream effect:
  answer-language form:
  limits / counterexamples:

M2:
  legal meaning:
  example raw facts:
  downstream effect:
  answer-language form:
  limits / counterexamples:
```

Preferred form:

```text
Raw Fact
→ Mediating Legal Reason
→ Legal Representation
```

## 5. Legal Representation Backend

Use the structure appropriate to the subject/problem.

### Balancing / factor form

```text
F1:
  meaning:
  direction:
  interactions:
  limits:
```

### Requirement-effect form

```text
Requirement R1:
  meaning:
  satisfaction conditions:
  consequence if satisfied:
  consequence if not satisfied:
```

### Procedural-state form

```text
State S1:
  available operation:
  prerequisites:
  transition / consequence:
```

### Rule / interpretation conflict form

```text
Candidate rule / construction A:
Candidate rule / construction B:
Selection criteria:
Consequence:
```

Delete unused backend sections in a concrete model.

## 6. Decision Procedure

```text
1.
2.
3.
4.
5.
```

The procedure must specify how the representation is actually executed, not merely list concepts.

## 7. Answer Rendering

Convert internal reasoning into scorable text.

```text
fact citation
→ mediating legal reason
→ legal significance
→ relation to rule / requirement / factor
→ counterargument if needed
→ conclusion
```

Example output pattern:

```text
本件では【事実】である。
これは【媒介概念・法的評価】を意味するため、【要件・因子・規範】を【肯定/否定】する方向に働く。
```

## 8. Residuals

```text
R1:
  content:
  why it resists compression:
  source:
  related residuals:
```

When several residuals cluster, test whether a missing mediating concept, distinction, state, or scope rule can absorb them.

## 9. Admission Check

Before adding a new representation element:

```text
Does it materially change the conclusion, analytical path, or answer content across multiple known cases/problems? YES / NO

Can the learner recognize and activate it from the problem within practical exam time? YES / NO
```

Promote it to the main model only if both are YES.

## 10. Provenance

```text
Training materials:

Validation materials already consumed:

Important counterexamples:

Known failures:

AI assistance used:

Build time added in this version:

What changed from previous version:
```

## 11. Model Generalization Test

Use genuinely sealed material only when testing external-model generalization.

```text
Model version tested:
Sealed set identifier:
Contamination check:
Conditions:
Result:
Required-issue coverage:
Fact-evaluation coverage:
Failures:
Diagnosis:
```

## 12. Deploy Representation

The smallest form intended to be internalized.

```text
<one line / tiny graph / short trigger sequence>
```

## 13. Human Runtime Test

This may and usually should use previously exposed problems.

```text
Problem:
Exposure status:
Closed book: YES / NO
Time limit:
Activation latency:
Structure recalled:
Fact → reason conversion:
Answer completeness:
Total execution time:
Runtime failure type:
```

A model is not considered deployed merely because the learner can recite it.

## 14. End-to-End Cost

```text
T_build:
T_internalize:
T_practice:
T_total:

Observed performance change:
Was the gain worth the construction cost?
```

## 15. Compression / Refactoring Notes

```text
What independent material did this model replace?
What remains irreducible?
Which residuals appear to share one missing concept?
Could an existing element be deleted without changing answers?
Is the deploy representation still too large or slow?
Is a different reasoning backend more natural for this problem?
```
