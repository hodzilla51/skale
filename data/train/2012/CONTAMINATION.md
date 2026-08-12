# 2012 Constitutional Law — Prospective Test Contamination Log

Status: **Phase B prospective test invalidated before prediction commit**

Dataset role: `TRAIN`

The 2012 Phase A frozen model remains a valid pre-problem snapshot. However, the intended clean problem-only prediction cannot be treated as prospective evidence.

## What happened

The protocol required:

```text
open 2012 problem text only
→ execute frozen model
→ commit prediction
→ only then inspect teacher signals
```

For 2012, the official Ministry of Justice problem index was safely located first. A separate public index also exposed the exact official problem-only PDF URL:

```text
https://www.moj.go.jp/content/000098335.pdf
```

Direct retrieval of the official PDF returned a 403 error in the current environment. A Kanazawa University archive was also located whose index clearly separates `問題` links from `出題趣旨` and `採点実感` links, and its 2012 public-law problem link resolved to a problem-only PDF path. However, that PDF could not be fetched in the retrieval environment.

A subsequent search intended only to locate an accessible mirror of the exact problem PDF returned third-party search results whose previews materially exposed the target issue and, more importantly, quoted / summarized official teacher-signal material for the 2012 constitutional-law problem. The exposed material included the doctrinal topic and substantive guidance derived from the official question intent / grading commentary.

This occurred before any Phase B prediction artifact was committed.

## Consequence

The 2012 prospective test is invalid for clean frozen-model generalization measurement.

Do **not** create a post-hoc `PREDICTION.md` and describe it as problem-only or preregistered.

Do **not** use 2012 to claim success or failure of the Phase B/C prediction protocol.

The Phase A snapshot remains historically valid because it was committed before any 2012 substantive access:

```text
data/train/2012/FROZEN_MODEL.md
commit: 2eb88534356068199f231a502304e8f013821743
```

## Dataset effect

2012 remains in the `TRAIN` split.

It may still be used for:

- normal year-level extraction;
- teacher-signal-guided fitting;
- Reasoning Core mutation analysis;
- Legal Knowledge Payload / Vocabulary / Residual accounting;
- future model construction.

It may not be counted as a clean prospective frozen-model test.

## Retrieval lesson

The failure mode is now broader than bundled webpages. Search-engine result previews themselves can leak issue labels, model-answer reasoning, or official teacher-signal quotations.

For the next prospective year, Phase B must avoid substantive web search entirely after freeze. A problem-only artifact must be obtained through a deterministic URL / file route established without querying the target year's legal content, for example:

```text
1. exact official problem PDF URL obtained from a pre-verified index;
2. exact archive problem PDF path obtained from a pre-verified index;
3. user-supplied problem-only PDF;
4. a locally cached corpus prepared before the year-specific freeze.
```

If the exact file cannot be fetched through that route, abort Phase B rather than search the open web for mirrors.

## Stronger protocol change suggested

Before attempting the next prospective year, prepare a local `problem-only` corpus for future TRAIN years using only index metadata and file-boundary verification, while deliberately withholding the problem contents from the model until each year's Phase B begins.

This separates retrieval engineering from the actual prediction experiment and prevents search-result contamination from consuming further years.
