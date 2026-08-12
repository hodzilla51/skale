# 2011 Constitutional Law — Post-Fit Model

Status: **TRAIN fit complete / candidate model entering 2012**

This file records the learner-facing model after incorporating 2011 TRAIN evidence. It is not itself a 2012 freeze. A separate Phase A artifact must be committed before any 2012 problem access.

## 1. Model size

```text
Reasoning Core units:            9
Legal Knowledge Payload units:  25
Legal Output Vocabulary items:  29
Residual candidates:             6
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

### RC-07 current form

```text
For each candidate branch:
  check doctrinal fit
  check explicit factual suppressors
  check task relevance
  compare relative legal / strategic strength
  allocate answer space accordingly
```

2011 caused one behavioral edit to RC-07 and no addition, split, or merge.

## 3. Legal Knowledge Payload

### P-01 to P-20 — inherited through 2010

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
```

### P-21 — Revocation action against an existing administrative cessation order

Challenge an already issued administrative cessation order through a revocation / cancellation action; constitutional claims are advanced within that challenge without turning the constitutional essay into a full administrative-law essay.

### P-22 — Minimal corporate constitutional-right capacity

A corporation may invoke constitutional rights whose nature permits corporate enjoyment. Use the rule only as much as needed to establish the claimant's capacity; do not automatically spend substantial answer space on it.

### P-23 — Business freedom as an available but secondary claimant theory

Commercial activity can implicate business / occupational freedom, but the learner must compare its fit and strategic strength against more specific constitutional theories available on the facts.

### P-24 — Factual information provision / free flow of information under Article 21

Article 21 protection can extend beyond personal opinions or political advocacy to provision and circulation of factual / visual information where the constitutional value of free information flow can be persuasively explained.

### P-25 — Portrait and private-life exposure beyond direct identification

Privacy-related constitutional harm can include public exposure of appearance, whereabouts, home life, family composition, or living patterns even when direct identifiers have been removed. Internet amplification is evaluated from concrete facts rather than stored as a categorical conclusion.

## 4. Payload clarifications retained without new unit count

### P-03 clarification

```text
law-level review
  -> evaluate the rule / scheme with legislative or general facts

application-level review
  -> evaluate the concrete act / order with case-specific facts
```

This remains one legal distinction.

### P-06 clarification

Clarity analysis must be tied to the actual operative statutory phrase and, where relevant, the burden on expressive activity. Do not reflexively convert every vague-looking phrase into a generic Article 31 paragraph.

### P-10 clarification

The informational-privacy family includes protection against unwanted public exposure of private-life information as well as control of / access to one's own sensitive information. Future evidence may force a split if these contexts require materially different executable legal rules.

## 5. Legal Output Vocabulary

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
```

## 6. Residual set

```text
R-01  Gifu youth-protection ordinance precedent / Ito supplementary opinion
R-02  third-party-owned-property confiscation precedent
R-03  blood-transfusion-refusal precedent
R-04  Toyama University precedent
R-05  Supreme Court Grand Bench 1958-10-15 local-treatment precedent
R-06  Supreme Court Grand Bench 2005-09-14 overseas-voting-rights precedent
```

2011 adds no confirmed Residual anchor.

## 7. Mutation and novelty history

```text
RC
2008 baseline: 8
2009: +0 additions / 2 edits / 1 split -> 9
2010: +0 additions / 0 edits / 0 splits -> 9  [TRAIN fit only]
2011: +0 additions / 1 edit  / 0 splits -> 9  [TRAIN fit only]

Payload
2008 baseline: 7
2009: +7; novelty 77.8%
2010: +6; novelty 85.7%
2011: +5; novelty 45.5%
current: 25

Vocabulary
2008 baseline: 9
2009: +8; novelty 61.5%
2010: +7; novelty 70.0%
2011: +5; novelty 45.5%
current: 29

Residual
2008 baseline: 2
2009: +2
2010: +2
2011: +0
current: 6
```

## 8. Domain-recurrence observation

2011 revisits the expression / information / privacy region already touched in 2008 and 2009.

The fall in Payload and Vocabulary novelty is therefore more informative than a simple year-number trend:

```text
new doctrinal region
  -> high novelty may be expected

revisited doctrinal region
  -> low novelty is evidence of local reuse / possible local saturation
```

2011 provides one positive observation of that pattern. It is not enough to estimate the total constitutional knowledge-pool size.

## 9. State entering 2012

The candidate model entering the next year is:

```text
RC:          9 units
Payload:    25 units
Vocabulary: 29 items
Residual:    6 anchors
```

The highest-value next evidence is still a clean prospective problem-only prediction. The 2012 Phase A freeze must be committed before any 2012 problem text or teacher signal is intentionally opened.
