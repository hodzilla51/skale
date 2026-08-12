# 2012 Constitutional Law — Compression Delta

Status: **TRAIN delta measured / not prospective generalization evidence**

Compared against `FROZEN_MODEL.md`.

Because Phase B was contaminated before a prediction commit, 2012 is used only for post-exposure fit and growth measurement.

## 1. Delta summary

```text
REASONING CORE
  pre-2012 units:                9
  unchanged units:               9 / 9
  standalone additions:          0
  behavioral edits:              0
  splits:                        0
  merges:                        0
  post-2012 units:               9

LEGAL KNOWLEDGE PAYLOAD
  reused units required:         0
  new units:                     6
  payload novelty rate:          6 / 6 = 100.0%
  cumulative payload units:      31

LEGAL OUTPUT VOCABULARY
  reused labels required:        0
  new labels:                    7
  vocabulary novelty rate:       7 / 7 = 100.0%
  cumulative unique labels:      36

RESIDUALS
  new confirmed anchors:         4
  cumulative confirmed:         10
```

2012 is a deliberate counterpoint to 2011. The previous year revisited expression / information / privacy and showed substantial reuse. 2012 opens a church-state / public-finance shelf not represented in the frozen Payload, so very high novelty is expected under a domain-conditional saturation model.

## 2. Reasoning Core audit

### RC-01 — identify actor / right-holder — UNCHANGED

The model distinguishes resident D, B Village, A Temple, the denomination, parishioners, non-parishioner residents, and the priest. No new actor-identification operation is needed.

### RC-02a — partition challenged measures / claims — UNCHANGED

This operation is central. It partitions:

```text
litigation vehicle
constitutional merits
land / cemetery aid
main-hall aid
priest-residence aid
```

The three aid items must receive separate concrete analysis because their religious / secular character differs.

### RC-02b — route rule / scheme vs application / disposition — UNCHANGED

The year does not require a new routing stage. The constitutional problem concerns concrete public expenditure rather than facial invalidity of a statutory scheme. Existing routing is sufficient to avoid unnecessary rule-level analysis.

### RC-03 — characterize actual legal relationship — UNCHANGED

The relationship is governmental financial support to a religious institution, not merely an individual's religious-freedom dispute. Existing characterization is sufficient.

### RC-04 — select and justify framework — UNCHANGED

2012 heavily exercises this operation. The examiner signals reject a bare memorized `purpose-effect test`; the framework must be justified from the constitutional provisions, separation principle, and precedent line. That is exactly the existing RC-04 job.

### RC-05 — fact -> mediating legal reason — UNCHANGED

The problem requires converting mixed-use and community-use facts into reasons bearing on religious significance, secular purpose, and supportive effect. No new operation is needed.

### RC-06 — test justification concretely — UNCHANGED

The model can compare purpose, effect, degree of support, mixed use, practical limits of separation, and item-specific consequences under the selected church-state backend.

### RC-07 — filter / suppress / prioritize — UNCHANGED

2012 strongly validates the post-2011 form without changing it.

The learner must suppress or deprioritize:

```text
Article 89 second-sentence / public-control detour
D's personal religious-freedom claim as the main theory
implausible denial that A Temple is religious
implausible denial that the subsidy is public money
```

and prioritize Article 89 first sentence plus the related Article 20 structure.

The input and output remain candidate branches and answer-space allocation; no edit or split is required.

### RC-08 — opponent + independent conclusion — UNCHANGED

The task expressly requires plaintiff advocacy, realistic defendant response, and the examinee's own view. Existing RC-08 fully represents the operation.

## 3. RC mutation result

```text
2012 TRAIN fit:
  additions: 0
  edits:     0
  splits:    0
  merges:    0
  net units: 9
```

This is TRAIN compatibility, not prospective evidence.

## 4. Reused Legal Knowledge Payload — 0 definite units

No pre-2012 Payload unit is counted as definitely required substantive legal knowledge for the central 2012 solution.

The existing Reasoning Core is heavily reused, but the positive-law / doctrine-specific church-state rules are new to the current model.

Potentially adjacent units such as P-14 public-actor routing are not counted merely because B Village is a public actor. That fact does not supply the specific Article 89 / Article 20 doctrine needed to solve the problem.

This conservative counting avoids manufacturing reuse by using overly broad labels.

## 5. New Legal Knowledge Payload — 6 units

### P-26 — Resident litigation route for executed local expenditure

When a resident challenges an already executed local-government financial act as unlawful, the main litigation route in this problem is a resident action under Local Autonomy Act Article 242-2(1)(4), with the legally required preliminary procedure treated as satisfied by the problem statement.

The exact statutory route matters; generic `administrative litigation` is insufficient.

### P-27 — Church-state constitutional provision routing

For public money given to a religious body, Article 89 first sentence is the primary constitutional entry point. The analysis then relates that prohibition to Article 20(1) second sentence's ban on privileges for religious organizations and Article 20(3)'s ban on state religious activity.

Do not substitute Article 89 second sentence or an individual religious-freedom claim merely because religion is present in the facts.

### P-28 — Functional classification of `religious organization or association`

Whether the recipient is a `宗教上の組織若しくは団体` for Article 89 is a substantive / functional constitutional classification. Formal incorporation under the Religious Corporations Act is not the decisive criterion.

The classification should be made from the entity's religious purposes, organization, activities, and institutional character.

### P-29 — Separation principle: neutrality without literal zero contact

The constitutional separation of state and religion is grounded in protection of religious freedom and governmental religious neutrality, including the historical danger of close state-religion identification. At the same time, the doctrine does not mechanically treat every contact between government and religion as unconstitutional; social and cultural reality may make some contact unavoidable.

This rationale is needed to justify the analytical framework rather than merely naming a test.

### P-30 — Purpose-effect / reasonable-limit framework

For state conduct connected with religion, the controlling precedent line evaluates whether the purpose has religious significance and whether the effect promotes, supports, suppresses, or interferes with religion, in light of the relevant circumstances and whether the relationship exceeds a socially reasonable limit.

The test is not a two-word incantation; the learner must connect the framework to concrete facts and precedent comparisons.

### P-31 — Article 89 first-sentence prohibition and the absolute-vs-relative question

The literal wording of Article 89 first sentence creates a distinct question whether public support for a religious organization is absolutely prohibited or whether the prohibition is interpreted in relation to the broader Article 20 separation framework and precedent-based reasonable-limit analysis.

A scorable answer must adopt a coherent position, explain the relationship among the provisions, and apply it consistently. The issue cannot be generated safely from generic proportionality reasoning alone.

## 6. Payload novelty history

```text
2009: 7 new / (7 + 2 reused) = 77.8%
2010: 6 new / (6 + 1 reused) = 85.7%
2011: 5 new / (5 + 6 reused) = 45.5%
2012: 6 new / (6 + 0 reused) = 100.0%
```

Interpretation:

```text
2011: revisit of a previously observed doctrinal region -> reuse rises
2012: first observation of church-state / public-finance region -> novelty spikes
```

This pattern argues against reading the yearly novelty curve as a simple monotonic sequence. Domain coverage is now an essential diagnostic.

## 7. New Legal Output Vocabulary — 7

No pre-2012 label is counted as definitely required for the core solution. New canonical labels are:

```text
V-30  住民訴訟
V-31  政教分離原則
V-32  信教の自由
V-33  宗教上の組織若しくは団体
V-34  特権付与
V-35  宗教的活動
V-36  目的効果基準
```

`信教の自由` is included as the canonical value whose protection helps explain the separation principle; it should not be confused with making D's own individual religious-freedom claim the center of the case.

Vocabulary novelty:

```text
2009: 8 / (8 + 5) = 61.5%
2010: 7 / (7 + 3) = 70.0%
2011: 5 / (5 + 6) = 45.5%
2012: 7 / (7 + 0) = 100.0%
```

## 8. Residual delta — 4 new precedent anchors

### R-07 — Minoo memorial / loyal-dead monument precedent

Retain as a boundary anchor for an organization not classified as a constitutional `religious organization or association` despite religion-adjacent memorial activity.

### R-08 — Tsu Jichinsai precedent

Retain as the core purpose-effect / reasonable-limit anchor involving a ceremony with religious form but substantial secular / customary context.

### R-09 — Ehime Tamagushiryo precedent

Retain as the public-funds-to-specific-religious-ceremony violation anchor and for the relationship among Article 20 and Article 89 analysis.

### R-10 — Sorachibuto Shrine precedent

Retain as the materially supportive state-religion relationship anchor involving public property / benefit and as a comparator for substantive classification of a religious group.

These anchors are not merged into one residual because their value lies in distinct comparative boundary positions. The abstract common structure is already stored in P-28 through P-31.

## 9. Merge discipline

No validated merge is performed.

The 2012 church-state Payload has only one observed year in the current dataset. Broad thematic similarity among church-state rules is not enough to merge them. The recurrence and admission tests are not met.

## 10. Current cumulative sizes after 2012

```text
Reasoning Core:          9
Legal Knowledge Payload: 31
Output Vocabulary:       36
Residual candidates:     10
Validated merges:         0
```

## 11. Experimental interpretation

2012 produces a strong layer-separation result:

```text
Reasoning Core:
  0 additions
  0 edits
  0 splits
  0 merges

Legal-specific layers:
  completely new doctrinal shelf
  Payload novelty = 100%
  Vocabulary novelty = 100%
  Residual +4
```

This is neither a success nor failure of the strong compression hypothesis by itself.

It shows that the reusable reasoning program can remain stable while subject-matter coverage expands sharply. The key future question is whether a later church-state recurrence reuses P-26 to P-31 at a rate resembling the 2011 expression / privacy recurrence.
