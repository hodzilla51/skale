# 2011 Constitutional Law — Phase A Frozen Model

Status: **frozen before 2011 problem inspection**

Dataset role: `TRAIN` prospective test

This artifact freezes the learner-facing SKALE model entering the 2011 constitutional-law test.

During this Phase A step, the 2011 problem, official question intent, grading commentary, examiner commentary, model answers, and derived analyses are not intentionally inspected.

The next permitted action is Phase B: obtain an isolated copy of the **2011 problem text only**, execute this frozen model, and commit a falsifiable prediction before any teacher signal is opened.

---

## 1. Frozen source artifacts

```text
data/train/2010/POST_FIT_MODEL.md
  blob sha: f83c4c1bb74d76f3d79a588794bd701ae0fb49e0

COMPRESSION_ARCHITECTURE.md
  blob sha: b12d3123cad14e064ca7654dc4f5dbb941cdd971
```

The 2010 contamination log remains part of the experiment history; 2010 did not provide prospective generalization evidence. The model below nevertheless incorporates 2010 as TRAIN fit, as recorded in `POST_FIT_MODEL.md`.

---

## 2. Frozen model size

```text
Reasoning Core units:            9
Legal Knowledge Payload units:  20
Legal Output Vocabulary items:  24
Residual candidates:             6
Deploy representation:           none separately defined yet
Validated merges:                0
```

---

## 3. Frozen Reasoning Core — 9 executable units

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

Frozen default skeleton:

```text
RC-01
→ RC-02a
→ RC-02b
→ RC-03
→ RC-04
→ RC-05 / RC-06 iteratively
→ RC-07 whenever candidate branches appear
→ RC-08
```

2011 must separately report:

```text
rc_additions
rc_behavioral_edits
rc_splits
rc_merges
```

Stable unit count alone is not convergence evidence.

---

## 4. Frozen Legal Knowledge Payload — 20 units

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
P-15  Article 25 through an implementing statute
P-16  equality of local treatment / local autonomy
P-17  constitutional significance of voting rights
P-18  restriction on voting-right exercise
P-19  legislative omission
P-20  State Redress illegality for legislative omission
```

No additional doctrine, textbook knowledge, or target-year intuition is silently added to the frozen Payload.

---

## 5. Frozen Legal Output Vocabulary — 24 items

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

Vocabulary is a canonical output-label layer, not a keyword-scoring assumption.

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

No Residual is absorbed before the 2011 test.

---

## 7. Historical state entering 2011

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

No saturation claim is frozen into the model. The 2011 result may support or weaken the hypothesis.

---

## 8. 2011 Phase B gate

Before any 2011 teacher signal is exposed, Phase B must commit a prediction artifact containing at minimum:

```text
predicted_rc_path
predicted_major_issues
predicted_required_payload
predicted_required_vocabulary
predicted_unnecessary_or_suppressed_branches
predicted_answer_skeleton
explicit_failure_conditions
```

Permitted Phase B input:

```text
2011 official problem text only
```

Forbidden until the prediction commit exists:

```text
official question intent
grading commentary
examiner commentary
model answers
commentaries or analyses derived from teacher signals
search-result payloads that bundle any of the above
```

Because the 2010 test was contaminated by a bundled search result, the 2011 problem must be obtained from an isolated problem-only artifact whose contents are verified not to include teacher signals before substantive reading.

---

## 9. Freeze integrity

This file is the 2011 model version under test.

After the 2011 problem is opened:

- do not edit this file to accommodate the problem;
- do not silently add Payload or Vocabulary before prediction;
- do not reinterpret a missing RC operation as if it had always existed;
- do not use teacher signals to improve the Phase B prediction;
- preserve misses as evidence.

Any post-teacher-signal change belongs to 2011 TRAIN fitting and must earn generalization evidence on a later untouched year.