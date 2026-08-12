# SKALE

**Shihou Kasu-compression Algorithm for Legal Education**  
対司法試験カス圧縮アルゴリズム

SKALE is an experimental method for compressing the knowledge and reasoning required for Japanese legal examinations into a smaller, human-executable model while preserving performance on unseen problems.

The project starts from a simple observation:

> People who pass legal examinations are still humans operating under severe limits on working memory and execution time.

If they can solve unseen legal problems, some reusable internal representation must exist. SKALE asks whether that representation can be made explicit, compressed, validated, and then implemented in a human learner more efficiently than conventional study.

## Core hypothesis

The target is **not** merely to summarize precedents.

SKALE seeks the smallest practical representation that preserves legal-exam performance:

```text
Authorities / Cases / Problems
          ↓
     SKALE model
          ↓
 Human deployment form
          ↓
         Brain
          ↓
    Unseen problems
```

A successful model should reduce memorization and execution cost without sacrificing generalization.

Conceptually:

```text
minimize(memory cost + execution cost + irreducible exceptions)
subject to: unseen-problem performance >= target performance
```

## Two kinds of compression

### Knowledge compression

Compress overlapping precedents, doctrines, arguments, and recurring fact patterns into reusable structures.

### Execution compression

Compile those structures into a representation that a human can recall and execute quickly under exam conditions.

The final goal is therefore not a large legal knowledge base. It is a **human-executable legal reasoning program**.

## Model structure

A canonical SKALE model contains:

- **Trigger / Router** — what facts or issue patterns activate the model
- **Normative Core** — statutes, doctrine, and precedent-based legal framework that must be preserved
- **Factor Graph** — outcome-relevant factors, their direction, interactions, and relative importance
- **Decision Procedure** — the order in which the model processes a problem
- **Residuals** — rules, exceptions, numbers, or precedent-specific information that cannot be safely generated from the model
- **Provenance / Validation** — which authorities and problems produced the model and how it performed on unseen material
- **Deploy Representation** — the smallest version intended to be internalized by the learner

See [DESIGN.md](./DESIGN.md).

## Experimental loop

```text
Solve problem
↓
Freeze pre-answer log
↓
Check authority / correct answer
↓
Extract or revise structure
↓
Minimize model
↓
Validate on unseen cases
↓
Test on unseen exam problems
↓
Diagnose failure
↓
Revise model
```

When a model fails, SKALE should first test whether the problem is a missing factor, incorrect weighting, interaction, routing error, or domain condition. New exceptions are added only when the failure cannot be explained more generally.

## Study logs

Answer logs may stay deliberately lightweight. Example:

```text
1 6 一般常識から考えて何となく
2 1 正直分からんがなんとなく
```

The important rule is that the pre-answer record is frozen before checking the answer. Later evaluation can be appended separately.

## What would count as success?

SKALE does not require a dramatic claim such as "replace all conventional legal study."

Any of the following would be meaningful:

- materially less memorization for the same unseen-problem performance
- better transfer to unfamiliar fact patterns
- fewer execution failures under time pressure
- faster formation of the kind of implicit judgment normally acquired only after large amounts of practice
- a stable post-learning representation that survives forgetting better than isolated precedent memorization

The strongest version of the hypothesis is that a surprisingly large portion of legal-exam competence is compressible into a low-dimensional model. The weaker — and still valuable — version is that SKALE acts as a final compiler that makes an otherwise conventional learner substantially more reliable.

## Status

Early experimental design. No claim of effectiveness yet.
