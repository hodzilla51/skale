# 2012 Constitutional Law — Phase A Frozen Model

Status: **frozen before 2012 problem inspection**

Dataset role: `TRAIN` prospective test

This artifact freezes the learner-facing SKALE model entering the 2012 constitutional-law test.

During this Phase A step, the 2012 problem, official question intent, grading commentary, examiner commentary, model answers, and derived analyses are not intentionally inspected.

The next permitted action is Phase B: obtain an isolated copy of the **2012 problem text only**, execute this frozen model, and commit a falsifiable prediction before any teacher signal is opened.

Because 2010 and 2011 prospective tests were contaminated by pages bundling problem text with teacher signals, Phase B retrieval for 2012 must not open BEXA year/problem pages or any page whose content boundary is not known in advance. Only a verified problem-only artifact is eligible.

---

## 1. Frozen source artifacts

```text
data/train/2011/POST_FIT_MODEL.md
  blob sha: c82178d35fe3f82ec706c7a16d3c3d2744f76482

COMPRESSION_ARCHITECTURE.md
  blob sha: b12d3123cad14e064ca7654dc4f5dbb941cdd971
```

The 2010 and 2011 contamination logs remain part of the experiment history. Neither year provides clean prospective generalization evidence, but both remain valid TRAIN fit data incorporated into the frozen model below.

---

## 2. Frozen model size

```text
Reasoning Core units:            9
Legal Knowledge Payload units:  25
Legal Output Vocabulary items:  29
Residual candidates:             6
Deploy representation:           none separately defined yet
Validated merges:                0
```

Mutation history entering 2012:

```text
2008 baseline RC units: 8
2009: +0 additions / 2 edits / 1 split -> 9
2010: +0 additions / 0 edits / 0 splits -> 9  [TRAIN fit only]
2011: +0 additions / 1 edit  / 0 splits -> 9  [TRAIN fit only]
```

A stable RC count is not enough to claim convergence. The 2012 result must separately report additions, behavioral edits, splits, and merges.

---

## 3. Frozen Reasoning Core — 9 executable units

### RC-01 — Identify actor / right-holder
Identify the legally relevant actor, claimant, right-holder, and protected interest. Keep different persons' rights distinct.

### RC-02a — Partition challenged measures / claims
Separate distinct governmental actions, sanctions, claims, or legal disputes that require separate analysis.

### RC-02b — Route each challenge to the correct level
For each partitioned challenge, distinguish a defect in the rule / scheme itself from a defect in its concrete application / disposition.

### RC-03 — Characterize the actual legal relationship
Before selecting doctrine, identify the specific protected interest, the constitutional relationship, and the feature producing the burden.

### RC-04 — Select and justify the analytical framework / backend
Choose the framework only after characterization and explain why it fits the protected interest, burden, competing interest, and legal task. The backend may be constitutional scrutiny, statutory interpretation, requirements/effects analysis, or another legally appropriate procedure.

### RC-05 — Convert fact to mediating legal reason
For each important fact, state why it matters legally and what part of the analysis it changes.

### RC-06 — Test the selected justification / requirements / effects concretely
Evaluate the legally relevant variables such as purpose, fit, effectiveness, burden, breadth, necessity, alternatives, competing rights, institutional reasons, requirements, effects, or procedural state as the selected backend requires.

### RC-07 — Filter, suppress, and prioritize candidate branches
For each candidate branch:

```text
check doctrinal fit
check explicit factual suppressors
check task relevance
compare relative legal / strategic strength
allocate answer space accordingly
```

### RC-08 — Strongest opposing position + independent conclusion
Construct the strongest responsive opposing position, compare the competing reasons, and render an independently reasoned conclusion.

Frozen default execution skeleton:

```text
RC-01
→ RC-02a
→ RC-02b
→ RC-03
→ RC-04
→ RC-05 / RC-06 iteratively during application
→ RC-07 whenever candidate branches compete
→ RC-08
```

This is a default execution structure, not a requirement that every answer visibly serialize every operation exactly once.

---

## 4. Frozen Legal Knowledge Payload — 25 units

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
P-23  business / occupational freedom as an available claimant theory
P-24  factual information provision / free flow of information under Article 21
P-25  portrait and private-life exposure beyond direct identification
```

Frozen clarifications carried with the relevant units:

### P-03

```text
law-level review
  -> evaluate the rule / scheme with legislative or general facts

application-level review
  -> evaluate the concrete act / order with case-specific facts
```

### P-06

Clarity analysis must be tied to the actual operative statutory phrase and, where relevant, the burden on expressive activity. Do not reflexively convert every vague-looking phrase into a generic Article 31 paragraph.

### P-10

The informational-privacy family currently includes both control of / access to one's own sensitive information and protection against unwanted public exposure of private-life information. This remains one frozen unit entering 2012; a later year may force a split if materially different executable rules are required.

No payload merges are performed before the 2012 test.

---

## 5. Frozen Legal Output Vocabulary — 29 items

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

These are output labels, not keyword-scoring assumptions. Phase B must predict which existing labels are actually required by the 2012 problem before teacher signals are opened.

---

## 6. Frozen Residual set — 6 candidates

```text
R-01  Gifu youth-protection ordinance precedent / Ito supplementary opinion
R-02  third-party-owned-property confiscation precedent
R-03  blood-transfusion-refusal precedent
R-04  Toyama University precedent
R-05  Supreme Court Grand Bench 1958-10-15 local-treatment precedent
R-06  Supreme Court Grand Bench 2005-09-14 overseas-voting-rights precedent
```

No residual is absorbed or merged before the 2012 test.

---

## 7. Frozen novelty history

```text
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

The 2011 novelty decline is retained only as a possible domain-recurrence signal, not as proof of global saturation.

---

## 8. Merge freeze

No merge is available merely because the 2012 problem makes two existing units look related.

The preregistered merge rule remains in force: recurrence across at least three independent years, at least two materially different surface fact patterns, the same mediating reason / inference route, no known material counterexample, and successful compression-admission tests.

Gross historical additions are never rewritten after a later merge.

---

## 9. Phase B retrieval gate

The next permitted action is:

```text
obtain a verified 2012 problem-only artifact
→ confirm the artifact terminates at the problem text
→ inspect the problem
→ execute this frozen model
→ commit 2012 problem-only prediction
→ only then inspect official teacher signals
```

Before the prediction commit, categorically forbidden sources include:

```text
BEXA year/problem pages
pages containing 出題趣旨 or 採点実感
model-answer pages
commentary / analysis pages
search-result payloads that expose teacher-signal text
```

The Phase B prediction must include at minimum:

```text
predicted_rc_path
predicted_major_issues
predicted_required_payload
predicted_required_vocabulary
predicted_unnecessary_or_suppressed_branches
predicted_answer_skeleton
explicit_failure_conditions
```

No target-year teacher signal may be used to improve that prediction before commit.

---

## 10. What the 2012 test can falsify

The frozen model is exposed to failure if later scoring shows, among other things:

- a required cognitive operation absent from the 9-unit RC;
- an existing RC that requires behavioral edit or split;
- a major issue omitted in the Phase B prediction;
- a materially wrong analytical order;
- a required Legal Knowledge Payload unit unavailable to the frozen model;
- a required Payload unit available in the frozen model but not activated / predicted;
- a predicted branch that teacher signals materially reject or deprioritize;
- a required output-vocabulary gap;
- failure of RC-05 / RC-06 to convert important facts into the legally expected evaluation.

Any revision made after problem inspection is post-test fitting and may not be retroactively attributed to this frozen model.
