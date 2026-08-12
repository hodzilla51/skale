# 2010 Constitutional Law — Prospective Test Contamination Log

Status: **Phase B prospective test invalidated before prediction commit**

Dataset role: `TRAIN`

The 2010 Phase A frozen model remains a valid pre-problem snapshot. However, the intended Phase B problem-only prediction cannot be treated as prospective evidence.

## What happened

The protocol required:

```text
open 2010 problem text only
→ execute frozen model
→ commit prediction
→ only then inspect official question intent / grading commentary
```

The official Ministry of Justice 2010 problem index was located, but direct opening from the retrieval environment returned an access error. A subsequent search for an isolated copy of the 2010 public-law Question 1 returned a BEXA result whose search payload contained not only the problem text but also substantial sections labeled as official question intent and grading commentary.

Those teacher signals were therefore materially exposed before any Phase B prediction artifact was committed.

## Consequence

The 2010 prospective test is invalid for frozen-model generalization measurement.

Do **not** create a post-hoc `PREDICTION.md` and describe it as problem-only or preregistered.

Do **not** use 2010 to claim success or failure of the Phase B/C prediction protocol.

The Phase A snapshot remains historically useful because it was committed before the contamination occurred:

```text
data/train/2010/FROZEN_MODEL.md
commit: fe0c7b7a7fe76394de984aaab7a5bc241503730e
```

## Dataset effect

2010 remains in the `TRAIN` split. The contamination does not consume validation or sealed-holdout material.

2010 may still be used normally for:

- year-level extraction;
- teacher-signal-guided fitting;
- Legal Payload / Vocabulary / Residual accounting;
- post-hoc RC mutation analysis;
- future model construction.

It may **not** be counted as a clean prospective frozen-model test.

## Information integrity rule

No attempt should be made to reconstruct what the model "would have predicted" before exposure. Once teacher signals have been seen, such reconstruction is not falsifiable enough for the intended experiment.

This negative procedural result is preserved rather than repaired retroactively.

## Retrieval lesson for the next prospective year

For the next untouched prospective year, the problem text must be obtained through a source that is demonstrably isolated from teacher signals before the model reads it.

Preferred order:

```text
1. direct official problem PDF / isolated official problem file
2. university/archive mirror of the problem PDF only
3. a locally downloaded isolated problem artifact verified not to contain commentary
```

Avoid search-result or transcription pages that bundle the problem together with question intent, grading commentary, model answers, or explanations.
