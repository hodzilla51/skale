# SKALE

**Shihou Kasu-compression Algorithm for Legal Education**  
対司法試験カス圧縮アルゴリズム

SKALE is an experimental method for constructing the smallest **human-executable legal reasoning system** that can preserve the performance required by Japanese legal examinations.

The project starts from a simple observation:

> People who pass legal examinations are still humans operating under severe limits on working memory and execution time.

If they can solve unseen legal problems, some reusable internal representation must exist. SKALE asks whether that representation can be made explicit, validated, compressed, and deployed into a human learner **faster than conventional study**.

## Core hypothesis

The target is not merely to summarize precedents, maximize compression ratio, or build an elegant legal model.

The end-to-end target is:

```text
minimize:
  total time to target exam performance

where:
  total time
  = build time
  + internalization time
  + practice time

subject to:
  sealed-holdout performance >= target
  human execution fits exam-time constraints
```

A smaller model is useful only if it reduces the total cost of reaching reliable passing performance.

## Teacher signals

SKALE does not treat precedent alone as the teacher.

```text
Legal textbooks / doctrine
        ↓ initial prior / baseline
Official question intent
        ↓ question-specific target
Official grading commentary
        ↓ error / discriminative signal
Statutes and precedents
        ↓ legal authority / boundary conditions
Past exam problems
        ↓ training / validation / sealed evaluation
```

Official grading commentary is not a complete answer key. It tends to emphasize omissions, weaknesses, and discriminative failures rather than everything examinees already do correctly. The baseline therefore comes from ordinary legal doctrine; examiner materials are used to correct and sharpen it.

## Architecture

SKALE uses a shared intermediate pipeline while allowing different subjects to use different reasoning backends.

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

The middle representation is not assumed to be a factor graph everywhere.

Examples:

- constitutional law: balancing / proportionality / factor structures
- civil law: requirements → satisfaction / non-satisfaction → legal effect
- civil procedure / company law: procedural state, available operation, consequence
- interpretive conflicts: competing rules / constructions and selection criteria

Existing doctrinal structures are used as initial hypotheses rather than rediscovered from zero.

## The semantic bridge

SKALE should not memorize brittle mappings such as:

```text
telephoto lens → intrusion high
```

It should preserve the mediating legal reason:

```text
telephoto lens
→ bypasses the subject's practical ability to control exposure
→ increases legal intrusiveness
```

The same bridge can generalize to a drone, infrared camera, synthetic reconstruction, or another unseen fact pattern.

This middle layer is especially valuable because it is also the sentence that can appear in the answer as legal evaluation. The reasoning representation and the answer output are therefore partially the same artifact.

## Evaluation budget

Unseen problems are a finite resource.

SKALE separates two kinds of evaluation:

**Model Generalization** uses sealed material and tests whether the external model handles genuinely unseen problems.

**Human Runtime** may reuse already-exposed problems and tests whether the learner can activate, execute, and render the model under closed-book and time-limited conditions.

Do not spend sealed holdout material merely to test retrieval speed or answer-writing fluency.

See [EVALUATION.md](./EVALUATION.md).

## Model admission rule

Do not optimize an arbitrary weighted sum of factor counts, exception counts, and memory estimates.

A candidate factor / representation element enters the model only when both are true:

1. adding it materially changes the analysis or answer across multiple known cases/problems;
2. the learner can recognize and activate it from the problem within practical exam time.

Otherwise it remains a residual.

If residuals begin to cluster, attempt to replace several of them with one better mediating concept or representation rule.

## Two kinds of compression

**Knowledge compression** reduces redundant legal material into reusable structures.

**Execution compression** compiles those structures into something a human can retrieve and execute quickly.

The external model and the deployed human runtime are measured separately. A model can be analytically excellent and still fail as a study method if it is too expensive to build, learn, retrieve, or write out.

## MVP strategy

Do not expand to all subjects first.

The first experiment is one subject: **constitutional law**.

Build the smallest useful SKALE version, log the time spent constructing it, deploy it, and test whether answer performance improves enough to justify that construction cost.

If performance does not improve, the result may indicate that SKALE targeted the wrong bottleneck rather than that the design is internally inconsistent.

If the model works but build time dominates, the next hypothesis is whether AI-assisted construction can reduce build cost without contaminating evaluation.

## Study logs

Answer logs may remain deliberately lightweight. Example:

```text
1 6 一般常識から考えて何となく
2 1 正直分からんがなんとなく
```

The important rule is that the pre-answer record is frozen before checking the answer. Later evaluation is appended separately.

## Status

Early experimental design. No claim of effectiveness yet.

See [DESIGN.md](./DESIGN.md) and [MODEL_TEMPLATE.md](./MODEL_TEMPLATE.md).
