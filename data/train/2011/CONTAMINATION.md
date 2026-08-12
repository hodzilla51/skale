# 2011 Constitutional Law — Prospective Test Contamination Log

Status: **Phase B prospective test invalidated before prediction commit**

Dataset role: `TRAIN`

The 2011 Phase A frozen model remains a valid pre-problem snapshot. However, the intended Phase B problem-only prediction cannot be treated as prospective evidence.

## What happened

The protocol required:

```text
open 2011 problem text only
→ execute frozen model
→ commit prediction
→ only then inspect official question intent / grading commentary
```

The official Ministry of Justice page confirming the 2011 public-law essay problem was located without exposing substantive teacher signals.

Because the official page could not be directly opened in the retrieval environment, a BEXA page titled as the 2011 public-law Question 1 problem page was used to access the problem text.

The search-result preview exposed problem text only. However, opening the page itself returned a single page containing, in sequence:

```text
problem text
→ official question intent transcription
→ grading commentary transcription
```

The retrieval response therefore materially exposed teacher signals before any Phase B prediction artifact was committed.

## Consequence

The 2011 prospective test is invalid for frozen-model generalization measurement.

Do **not** create a post-hoc `PREDICTION.md` and describe it as problem-only or preregistered.

Do **not** use 2011 to claim success or failure of the Phase B/C prediction protocol.

The Phase A snapshot remains historically valid because it was committed before any 2011 problem or teacher-signal inspection:

```text
data/train/2011/FROZEN_MODEL.md
commit: 7565e1144bc68bd5b0514046a4b8fe51a569b44e
```

## Dataset effect

2011 remains in the `TRAIN` split.

It may still be used for:

- normal year-level extraction;
- teacher-signal-guided fitting;
- Reasoning Core mutation analysis;
- Legal Knowledge Payload / Vocabulary / Residual accounting;
- future model construction.

It may not be counted as a clean prospective frozen-model test.

## Information-integrity rule

No attempt should be made to reconstruct what the frozen model "would have predicted" before teacher-signal exposure. Such a reconstruction would be contaminated by hindsight and would not satisfy the preregistered falsifiability requirement.

## Stronger retrieval rule for the next prospective year

For 2012 and later prospective tests, do **not** open any BEXA year page before the Phase B prediction commit, even if the search-result preview appears to show only the problem.

The target problem must first be obtained from an artifact whose contents are known to terminate at the problem text, preferably:

```text
1. direct official problem-only PDF
2. university/archive mirror of that exact problem-only PDF
3. locally supplied problem-only file whose boundaries can be verified before substantive reading
```

A webpage that combines problem text with commentary is categorically ineligible for Phase B access.
