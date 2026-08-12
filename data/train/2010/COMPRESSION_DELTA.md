# 2010 Constitutional Law — Compression Delta

Status: **TRAIN delta measured / not prospective generalization evidence**

Compared against the frozen pre-2010 model in `FROZEN_MODEL.md`.

Because the prospective test was contaminated before prediction commit, this file measures post-exposure TRAIN compatibility and model growth only.

## 1. Delta summary

```text
REASONING CORE
  pre-2010 units:                9
  unchanged units usable:        9 / 9
  standalone additions:          0
  behavioral edits:              0
  splits:                        0
  merges:                        0
  post-2010 units:               9

LEGAL KNOWLEDGE PAYLOAD
  reused units required:         1
  new units:                     6
  payload novelty rate:          6 / 7 = 85.7%
  cumulative payload units:      20

LEGAL OUTPUT VOCABULARY
  reused labels required:        3
  new labels:                    7
  vocabulary novelty rate:       7 / 10 = 70.0%
  cumulative unique labels:      24

RESIDUALS
  new precedent anchors:         2
  cumulative residuals:          6
```

The Reasoning Core result is encouraging as a TRAIN compatibility observation, but it must not be described as a successful frozen-model prediction because teacher signals were exposed before Phase B.

The legal-specific result is currently unfavorable to early saturation: both Payload and Vocabulary novelty remain high.

## 2. Reasoning Core compatibility

### RC-01 — actor / right-holder — UNCHANGED

X is the direct holder of the relevant subsistence and voting interests.

### RC-02a — partition challenged measures / claims — UNCHANGED

The model partitions:

```text
public-assistance denial
voting exclusion
```

and, within the voting branch, distinguishes substantive constitutional invalidity from the separate damages / State Redress question.

This is exactly the type of claim partitioning introduced by the 2009 split.

### RC-02b — route each challenge to correct level — UNCHANGED

The operation successfully distinguishes:

```text
public assistance:
  interpretation / application of existing statute

voting:
  scheme-level legislative omission
```

A scheme-level omission still falls within the existing rule / scheme side of the routing output. No new output type is necessary.

### RC-03 — characterize actual legal relationship — UNCHANGED

It identifies Article 25 subsistence protection implemented through an existing statute and the effective exercise of voting rights as distinct legal relationships.

### RC-04 — select and justify analytical framework — UNCHANGED

The frozen wording deliberately says `analytical framework`, not `scrutiny tier`.

Accordingly, the welfare branch can select constitutional-purpose-guided statutory interpretation rather than a generic constitutional scrutiny test, while the voting branch can select the controlling voting-right precedent framework.

No edit is needed merely because the selected backend is interpretive rather than a scrutiny standard.

### RC-05 — fact -> mediating legal reason — UNCHANGED

The seven-year petition, health consequences, different municipal practice, one-district fact, and City's motives all require this operation directly.

### RC-06 — test justification concretely — UNCHANGED

The operation can evaluate statutory purpose, local-autonomy reasons, equality concerns, electoral fairness, practical alternatives, notice, and persistence.

### RC-07 — filter / suppress non-fitting branches — UNCHANGED

2010 strongly exercises the suppressor already added in 2009. It must suppress, among other things:

- facial invalidity of the Public Assistance Act;
- generic legislative discretion in the welfare branch;
- long abstract Article 25 legal-character theory;
- automatic use of purpose-means scrutiny where statutory interpretation is the proper operation;
- the idea that law-level and application-level attacks must always both be written.

No new suppressor mechanism is required.

### RC-08 — opponent + independent conclusion — UNCHANGED

The official materials again require a responsive opposing rationale and independent conclusion, while discouraging mechanical three-position standard shopping.

## 3. RC mutation result

```text
2010 TRAIN compatibility:
  additions: 0
  edits:     0
  splits:    0
  merges:    0
```

This is the first year in which the post-2009 9-unit RC needs no post-hoc mutation.

However, because 2010 was contaminated before prediction, it is evidence of **fit / representational compatibility**, not clean prospective predictive power.

The next untouched year must test whether the same result survives preregistration.

## 4. Legal Knowledge Payload delta

### Reused — 1 definite unit

#### RP-01 — rule-level vs application-level constitutional review

Pre-2010 `P-03` is required to avoid treating the public-assistance statute as facially unconstitutional and to locate the voting defect at scheme / omission level.

Public-actor routing is background-compatible but is not counted as a required learner-facing Payload unit for novelty-rate purposes because public status is not a disputed doctrinal issue in this problem.

### New — 6 units

#### NP-2010-01 — Article 25 through an existing implementing statute

Where legislation already concretizes subsistence protection, constitutional analysis may operate through interpretation and application of the concrete statutory provisions. The learner must connect Article 25 purpose to Public Assistance Act terms such as `居住地` and `現在地` rather than jump directly to abstract constitutional invalidity.

#### NP-2010-02 — equality of local treatment / local-autonomy interaction

Different treatment by local governments can raise equality concerns, but the analysis must account for local autonomy and the national statutory purpose; existing precedent allowing local differences cannot be transplanted without comparing the legal and factual context.

#### NP-2010-03 — constitutional significance of the right to vote

The voting right and its effective exercise have distinct constitutional weight grounded in popular sovereignty and representative democracy, not merely in analogy to freedom of expression.

#### NP-2010-04 — heightened rule for restriction on voting-right exercise

Under the 2005 overseas-voting-rights precedent, a restriction requires an unavoidable reason; the analysis asks whether permitting exercise while preserving electoral fairness is practically impossible or extremely difficult.

#### NP-2010-05 — legislative omission as a constitutional defect

A right may be effectively denied because legislation fails to create a necessary exercise mechanism. Removing an existing provision is not always the correct remedy or analytical target.

#### NP-2010-06 — State Redress illegality for legislative omission is distinct

The substantive constitutionality of a legislative omission and whether the omission is illegal for State Redress damages are separate legal questions with separate criteria. Notice, duration, and the legislature's opportunity to respond can matter to the latter.

### Payload novelty

```text
2009: 7 new / (7 new + 2 reused) = 77.8%
2010: 6 new / (6 new + 1 reused) = 85.7%
```

The rate did **not** decline in 2010. On this two-delta series, there is no evidence yet that Legal Knowledge Payload is saturating.

This result should be preserved even though it is unfavorable to the strong compression hypothesis.

## 5. Legal Output Vocabulary delta

### Reused — 3

- `法令違憲`
- `適用違憲`
- `審査基準`

### New — 7

- `生存権`
- `平等原則`
- `選挙権 / 投票権` [normalized family]
- `立法不作為`
- `国家賠償請求`
- `国民主権`
- `間接民主制`

Do not count optional or discouraged terms merely because they appear in examiner commentary. In particular, `比例原則`, `プログラム規定説`, and generic `立法裁量` are not added as required 2010 output labels.

### Vocabulary novelty

```text
2009: 8 new / (8 new + 5 reused) = 61.5%
2010: 7 new / (7 new + 3 reused) = 70.0%
```

Vocabulary novelty also does not decline in 2010.

## 6. Residual delta

### NR-2010-01 — 1958 local-treatment precedent anchor

Retain the Supreme Court Grand Bench 1958-10-15 Tokyo prostitution-control ordinance precedent as a specific anchor for differing local treatment and the need to compare its context with the current statutory scheme.

### NR-2010-02 — 2005 overseas-voting-rights precedent anchor

Retain the Supreme Court Grand Bench 2005-09-14 overseas-voting-rights precedent as a specific anchor because the examiner materials rely on it both for the restriction standard and for legislative-omission / State Redress analysis.

One precedent anchor may support multiple Payload propositions without duplicating the Residual count.

## 7. Merge discipline

No merge is performed.

In particular, `legislative omission` and `State Redress illegality for legislative omission` are **not** merged merely because the same precedent discusses both. The examiner materials explicitly require the two questions to be distinguished, which is affirmative evidence against a one-unit representation unless a later representation can regenerate the distinction losslessly.

Gross additions remain:

```text
2008 payload baseline: 7
2009 gross additions:  +7
2010 gross additions:  +6
current gross/net:      20   [no validated merges]
```

## 8. Current cumulative sizes after 2010

```text
Reasoning Core:          9
Legal Knowledge Payload: 20
Output Vocabulary:       24
Residual candidates:      6
```

Do not add these across layers into a single synthetic complexity score.

## 9. Experimental interpretation

After 2010 the evidence is split:

```text
Reasoning procedure:
  stable on TRAIN fit in 2010

Legal-specific knowledge:
  still showing high novelty

Vocabulary:
  still showing high novelty
```

The project therefore has a plausible stable reasoning skeleton, but no evidence yet that the larger memorization burden is bounded tightly enough to produce the desired radical compression.

2011 should be used as the next clean prospective test if its problem can be isolated without teacher-signal leakage.