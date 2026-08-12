# SKALE Model Template

Use one copy of this template for each model/domain. Keep the canonical model explicit; keep the deploy representation aggressively small.

## Metadata

```text
id:
domain:
version:
status: draft | validating | stable | deprecated
created:
updated:
```

## 1. Trigger / Router

What should make this model activate?

```text
Trigger facts / issue patterns:

Neighboring models:

Routing distinctions:
```

## 2. Normative Core

What legal structure must be preserved rather than guessed from correlations?

```text
Statutory basis:

Controlling rule / doctrine:

Protected interest / legal purpose:

Required analytical sequence:
```

## 3. Factor Graph

Record only factors that materially improve explanation or unseen-problem performance.

```text
F1:
  meaning:
  factual indicators:
  direction:
  interactions:
  limits:

F2:
  meaning:
  factual indicators:
  direction:
  interactions:
  limits:
```

## 4. Decision Procedure

```text
1.
2.
3.
4.
5.
```

## 5. Residuals

Information that currently resists safe generation from the model.

```text
R1:
  content:
  why residual:
  source:
```

## 6. Provenance

```text
Training authorities / cases:

Training questions:

Important counterexamples:

What changed from previous version:
```

## 7. Validation

```text
Model version tested:
Test set:
Exposure status: unseen | previously exposed
Conditions:
Result:
Failures:
Diagnosis:
```

## 8. Deploy Representation

The smallest form intended to be internalized.

```text
<one line / tiny graph / short trigger sequence>
```

## 9. Human Deployment Check

A model is not considered deployed merely because the learner can recite it.

Test without viewing the canonical model:

```text
Can the learner recognize when to activate it?
Can the learner recall the controlling factors?
Can facts be mapped to factors quickly?
Can competing directions be evaluated?
Can the learner generate a legally structured answer?
Can this still be done after a delay?
```

## 10. Compression Notes

```text
What independent items did this model replace?
What remains irreducible?
Could two factors be merged without performance loss?
Could an exception instead reveal a missing factor or interaction?
Is the deploy representation still too large or slow?
```
