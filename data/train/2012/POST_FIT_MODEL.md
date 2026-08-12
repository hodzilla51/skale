# 2012 Constitutional Law — Post-Fit Model

Status: **TRAIN fit complete / candidate model entering 2013**

This file records the learner-facing model after incorporating 2012 TRAIN evidence. It is not itself a 2013 freeze.

## 1. Model size

```text
Reasoning Core units:            9
Legal Knowledge Payload units:  31
Legal Output Vocabulary items:  36
Residual candidates:            10
Validated merges:                0
```

## 2. Reasoning Core

```text
RC-01  identify actor / right-holder
RC-02a partition challenged measures / claims
RC-02b route each challenge to rule / scheme vs application / disposition
RC-03  characterize actual protected interest / legal relationship / burden
RC-04  select and justify the appropriate analytical framework or backend
RC-05  convert fact -> mediating legal reason
RC-06  test the selected justification / requirements / effects concretely
RC-07  filter, suppress, and prioritize candidate branches
RC-08  strongest opposing position + independent conclusion
```

2012 required no addition, behavioral edit, split, or merge. The year strongly exercised RC-02a, RC-04, RC-05, RC-06, and RC-07.

## 3. Legal Knowledge Payload

### P-01 to P-25 — inherited through 2011

```text
P-01  Article 21 expression / information receipt
P-02  third-party-right invocation
P-03  rule-level vs application-level constitutional review
P-04  content-based speech regulation
P-05  minors / harmful-expression context
P-06  constitutional clarity
P-07  limits on delegation
P-08  Article 23 academic / research freedom
P-09  university autonomy
P-10  Article 13 informational privacy / self-information control family
P-11  paternalistic restriction
P-12  informed consent / explanation-duty autonomy
P-13  partial-society / judicial-review doctrine
P-14  public-actor constitutional routing
P-15  Article 25 through an implementing statute
P-16  equality of local treatment / local autonomy
P-17  constitutional significance of voting rights
P-18  restriction on voting-right exercise
P-19  legislative omission
P-20  State Redress illegality for legislative omission
P-21  revocation action against an existing administrative cessation order
P-22  minimal corporate constitutional-right capacity
P-23  business freedom as an available but secondary claimant theory
P-24  factual information provision / free flow of information under Article 21
P-25  portrait and private-life exposure beyond direct identification
```

### P-26 — Resident litigation route for executed local expenditure

For an already executed local-government financial act challenged by a resident as unlawful, use the resident-litigation route under Local Autonomy Act Article 242-2(1)(4), with required preliminary procedure treated as satisfied where the problem says so.

### P-27 — Church-state constitutional provision routing

For public money given to a religious body:

```text
primary entry: Article 89 first sentence
related:       Article 20(1) second sentence — privilege prohibition
related:       Article 20(3) — state religious activity
```

Do not replace this structure with Article 89 second sentence or an individual-right claim merely because religious facts are present.

### P-28 — Functional classification of `religious organization or association`

Article 89 classification is substantive / functional. Formal Religious Corporations Act incorporation is not decisive. Evaluate religious purpose, organization, activities, and institutional character.

### P-29 — Separation principle: neutrality without literal zero contact

Church-state separation protects religious freedom and state neutrality against the dangers of close state-religion identification. It does not mechanically prohibit every practical connection between government and religion; some contact may be unavoidable in social and cultural reality.

### P-30 — Purpose-effect / reasonable-limit framework

Evaluate the purpose's religious significance and whether the effect supports, promotes, suppresses, or interferes with religion in light of the surrounding circumstances and whether the relationship exceeds a socially reasonable limit.

The framework must be reasoned and fact-sensitive, not merely named.

### P-31 — Article 89 first-sentence prohibition: absolute vs relative interpretation

The wording of Article 89 raises a specific question whether public support for religious organizations is absolutely forbidden or whether the prohibition should be understood in relation to the broader Article 20 separation framework and precedent-based reasonable-limit analysis.

A learner must adopt and explain a coherent provision relationship before applying the facts.

## 4. Legal Output Vocabulary

```text
V-01  表現の自由
V-02  知る自由 / 知る権利
V-03  内容規制
V-04  法令違憲
V-05  適用違憲 / 処分違憲
V-06  明確性
V-07  委任
V-08  第三者の権利
V-09  審査基準
V-10  学問の自由
V-11  大学の自治
V-12  プライバシー権
V-13  自己情報コントロール権
V-14  パターナリズム
V-15  インフォームド・コンセント
V-16  説明義務
V-17  部分社会の法理
V-18  生存権
V-19  平等原則
V-20  選挙権 / 投票権
V-21  立法不作為
V-22  国家賠償請求
V-23  国民主権
V-24  間接民主制
V-25  取消訴訟
V-26  営業の自由 / 職業の自由
V-27  情報提供の自由
V-28  肖像権
V-29  立法事実
V-30  住民訴訟
V-31  政教分離原則
V-32  信教の自由
V-33  宗教上の組織若しくは団体
V-34  特権付与
V-35  宗教的活動
V-36  目的効果基準
```

## 5. Residual set

```text
R-01  Gifu youth-protection ordinance precedent / Ito supplementary opinion
R-02  third-party-owned-property confiscation precedent
R-03  blood-transfusion-refusal precedent
R-04  Toyama University precedent
R-05  Supreme Court Grand Bench 1958-10-15 local-treatment precedent
R-06  Supreme Court Grand Bench 2005-09-14 overseas-voting-rights precedent
R-07  Minoo memorial / loyal-dead monument precedent
R-08  Tsu Jichinsai precedent
R-09  Ehime Tamagushiryo precedent
R-10  Sorachibuto Shrine precedent
```

The 2012 church-state anchors remain separate because their comparative factual positions are exam-relevant even after abstract doctrine is stored in P-28 through P-31.

## 6. Mutation and novelty history

```text
RC
2008 baseline: 8
2009: +0 additions / 2 edits / 1 split -> 9
2010: +0 additions / 0 edits / 0 splits -> 9  [TRAIN fit only]
2011: +0 additions / 1 edit  / 0 splits -> 9  [TRAIN fit only]
2012: +0 additions / 0 edits / 0 splits -> 9  [TRAIN fit only]

Payload
2008 baseline: 7
2009: +7; novelty 77.8%
2010: +6; novelty 85.7%
2011: +5; novelty 45.5%
2012: +6; novelty 100.0%
current: 31

Vocabulary
2008 baseline: 9
2009: +8; novelty 61.5%
2010: +7; novelty 70.0%
2011: +5; novelty 45.5%
2012: +7; novelty 100.0%
current: 36

Residual
2008 baseline: 2
2009: +2
2010: +2
2011: +0
2012: +4
current: 10
```

## 7. Domain-coverage interpretation

The year sequence now gives the first useful contrast between chronological novelty and doctrinal-region novelty:

```text
2011
  expression / information / privacy revisit
  -> Payload novelty 45.5%

2012
  first church-state / public-finance observation
  -> Payload novelty 100.0%
```

Therefore a monotonic `year number -> lower novelty` expectation is not appropriate.

The stronger diagnostic is:

```text
within an already observed doctrinal region,
how much of the required Payload / Vocabulary is reused when that region returns?
```

2012 expands total coverage but does not contradict the 2011 local-reuse observation.

## 8. State entering 2013

Candidate model after 2012 TRAIN fit:

```text
RC:          9 units
Payload:    31 units
Vocabulary: 36 items
Residual:   10 anchors
Merges:      0
```

No 2013 problem content has been incorporated by this artifact. A separate Phase A freeze is required before any 2013 prospective access.
