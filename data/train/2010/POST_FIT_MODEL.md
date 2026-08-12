# 2010 Constitutional Law — Post-Fit Model

Status: **TRAIN fit complete / candidate model entering 2011**

This file records the learner-facing model after incorporating 2010 TRAIN evidence. It is not itself a 2011 freeze; a separate Phase A artifact must be committed before opening the 2011 problem.

## 1. Model size

```text
Reasoning Core units:            9
Legal Knowledge Payload units:  20
Legal Output Vocabulary items:  24
Residual candidates:             6
```

No validated merges have occurred.

## 2. Reasoning Core

```text
RC-01  identify actor / right-holder
RC-02a partition challenged measures / claims
RC-02b route each challenge to rule / scheme vs application / disposition
RC-03  characterize actual protected interest / legal relationship / burden
RC-04  select and justify the appropriate analytical framework or backend
RC-05  convert fact -> mediating legal reason
RC-06  test the selected justification / requirements / effects concretely
RC-07  filter and suppress non-fitting branches
RC-08  strongest opposing position + independent conclusion
```

2010 TRAIN analysis required no RC addition, edit, split, or merge.

## 3. Legal Knowledge Payload

### P-01 to P-14 — inherited pre-2010 units

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
P-10  Article 13 informational privacy / self-information control
P-11  paternalistic restriction
P-12  informed consent / explanation-duty autonomy
P-13  partial-society / judicial-review doctrine
P-14  public-actor constitutional routing
```

### P-15 — Article 25 through an implementing statute

Where legislation already concretizes subsistence protection, interpret and apply the concrete statutory scheme in light of Article 25 purpose rather than skipping directly to abstract constitutional invalidity.

### P-16 — equality of local treatment / local autonomy

Different local treatment may raise equality concerns, but the analysis must account for local autonomy, statutory structure, and factual / legal differences from precedent.

### P-17 — constitutional significance of voting rights

The right to vote and its effective exercise have distinct constitutional importance grounded in popular sovereignty and representative democracy.

### P-18 — restriction on voting-right exercise

A restriction on voting-right exercise requires an unavoidable reason under the controlling precedent, including concrete examination of whether exercise with electoral fairness is practically impossible or extremely difficult.

### P-19 — legislative omission

A constitutional defect may consist of failure to create a mechanism necessary for effective exercise of a protected right.

### P-20 — State Redress illegality for legislative omission

Substantive unconstitutionality of legislative omission and illegality for damages are separate questions; notice, persistence, and opportunity to legislate may matter to the latter.

## 4. Legal Output Vocabulary

```text
V-01  表現の自由
V-02  知る自由 / 知る権利
V-03  内容規制
V-04  法令違憲
V-05  適用違憲
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
```

## 5. Residual set

```text
R-01  Gifu youth-protection ordinance precedent / Ito supplementary opinion
R-02  third-party-owned-property confiscation precedent
R-03  blood-transfusion-refusal precedent
R-04  Toyama University precedent
R-05  Supreme Court Grand Bench 1958-10-15 local-treatment precedent
R-06  Supreme Court Grand Bench 2005-09-14 overseas-voting-rights precedent
```

## 6. Mutation and novelty history

```text
RC
2008 baseline: 8
2009: +0 additions / 2 edits / 1 split -> 9
2010: +0 additions / 0 edits / 0 splits -> 9  [TRAIN fit only]

Payload
2008 baseline: 7
2009: +7; novelty 77.8%
2010: +6; novelty 85.7%
current: 20

Vocabulary
2008 baseline: 9
2009: +8; novelty 61.5%
2010: +7; novelty 70.0%
current: 24

Residual
2008 baseline: 2
2009: +2
2010: +2
current: 6
```

## 7. State of the hypothesis

The Reasoning Core is currently compact and 2010 can be represented without post-hoc mutation of the 9-unit form. That is not prospective evidence because 2010 was contaminated.

The stronger compression hypothesis is not yet supported on the legal-specific layers: Payload and Vocabulary novelty remain high and did not decline from 2009 to 2010.

The next high-value evidence is a clean prospective year using this model lineage, with problem-only prediction committed before teacher signals are exposed.