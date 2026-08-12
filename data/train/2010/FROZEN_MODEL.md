# 2010 Constitutional Law — Phase A Frozen Model

Status: **frozen before 2010 problem inspection**

Dataset role: `TRAIN` prospective test

This artifact freezes the learner-facing SKALE model that will be tested on the 2010 constitutional-law problem.

During this Phase A step, the 2010 problem, official question intent, grading commentary, examiner commentary, model answers, and derived analyses are not intentionally inspected. The next permitted step is **problem-only prediction** under the protocol in `COMPRESSION_ARCHITECTURE.md`.

This snapshot is the model version under test. Any revision made after seeing the 2010 problem is not part of frozen-model performance for 2010.

---

## 1. Frozen source artifacts

The frozen model is reconstructed from these pre-2010 artifacts:

```text
data/train/2008/COMPRESSION_BASELINE.md
  blob sha: c90105d558aac925c68bfb5934f7e3a4e2f5956f

data/train/2009/COMPRESSION_DELTA.md
  blob sha: db79d569e4f057548bbd51c4c390d8a98dcbfc16

data/train/2009/RC_REAUDIT.md
  blob sha: bd7a182bea0bc4c8e0a8128d13a759c0b2949184

COMPRESSION_ARCHITECTURE.md
  frozen protocol version: post-commit 749e3baadeca84bbea5d0e50304b1b9d65f33120
```

For Reasoning Core count and mutation history, `RC_REAUDIT.md` supersedes the older RC-count interpretation in `COMPRESSION_DELTA.md`.

---

## 2. Frozen model size

```text
Reasoning Core units:            9
Legal Knowledge Payload units:  14
Legal Output Vocabulary items:  17
Residual candidates:             4
Deploy representation:           none separately defined yet
```

Mutation history entering the 2010 test:

```text
2008 baseline RC units: 8
2009 additions:         0
2009 behavioral edits: 2
2009 splits:            1
2009 merges:            0
post-2009 RC units:     9
```

The 2010 result must report RC additions, behavioral edits, splits, and merges separately. Stable unit count alone is not evidence of convergence.

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

### RC-04 — Select and justify the analytical framework
Choose the framework only after characterization and explain why the framework fits the type / intensity of burden and the competing interest. Do not rely on a test label alone.

### RC-05 — Convert fact to mediating legal reason
For each important fact, state why it matters legally and what part of the analysis it changes.

### RC-06 — Test justification concretely
Evaluate the relevant justification variables such as purpose, fit / effectiveness, burden, breadth, necessity, alternatives, competing rights, institutional reasons, requirements, or effects as the selected backend requires.

### RC-07 — Filter / suppress non-fitting branches
After a doctrine is triggered, check doctrinal fit and any explicit factual suppressors before spending answer space on it.

### RC-08 — Opponent + independent conclusion
Construct the strongest responsive opposing position, compare the competing reasons, and render an independently reasoned conclusion.

Frozen execution skeleton:

```text
RC-01
→ RC-02a
→ RC-02b
→ RC-03
→ RC-04
→ RC-05 / RC-06 iteratively during application
→ RC-07 whenever candidate branches appear
→ RC-08
```

This is a default skeleton, not a claim that every problem must visibly serialize every operation exactly once. A 2010 ordering miss will be counted if teacher signals show that the frozen structure materially prevents the expected analysis.

---

## 4. Frozen Legal Knowledge Payload — 14 units

### P-01 — Article 21 expression / information receipt
Constitutional protection may extend to expression and to audience information-receipt interests, which may belong to different actors.

### P-02 — Third-party-right invocation
A claimant cannot automatically rely on a constitutional right belonging to another person; additional legal justification may be required.

### P-03 — Rule-level vs application-level constitutional review
The target and reasoning differ depending on whether the rule / scheme itself or its concrete application / disposition is challenged.

### P-04 — Content-based speech regulation
A restriction triggered by communicative content is legally different from one directed only at the medium or method, and this affects constitutional review.

### P-05 — Minors / harmful expression context
Protection of minors and treatment of harmful expression may modify ordinary speech analysis, but the modification requires legal justification rather than a magic-word exception.

### P-06 — Constitutional clarity
A regulation may create a constitutional problem if its legally operative boundary is insufficiently clear; the 2008 materials connect this with Article 31-style concerns.

### P-07 — Limits on delegation
Subordinate rulemaking does not automatically cure an insufficient statutory structure, and important matters may require adequate legislative definition.

### P-08 — Article 23 academic / research freedom
Academic research may receive constitutional protection, including protection of an individual researcher's activity.

### P-09 — University autonomy
University autonomy functions as an institutional guarantee connected to academic freedom and may, depending on the conflict, support institutional control rather than always point in the individual's favor.

### P-10 — Article 13 informational privacy / self-information control
Access to and control of one's own sensitive information may require an Article 13 autonomy / informational-privacy analysis distinct from an ordinary Article 21 sender-recipient model.

### P-11 — Paternalistic restriction
A restriction imposed for a competent adult's supposed own protection presents a distinct constitutional justification problem and is not automatically valid or invalid.

### P-12 — Informed consent / explanation-duty autonomy
Consent, explanation, and autonomous medical decision-making have legal significance; the weight of consent may depend on information quality and asymmetry.

### P-13 — Partial-society / judicial-review doctrine
Internal institutional decisions may trigger a partial-society / judicial-review framework, but doctrinal fit must be examined rather than assumed.

### P-14 — Public-actor constitutional routing
Action by a public institution is routed as public action for constitutional review rather than automatically treated as a private-party constitutional-effect problem.

No payload merges are performed before the 2010 test. Candidate higher-order relations do not reduce this gross 14-unit count.

---

## 5. Frozen Legal Output Vocabulary — 17 items

```text
V-01  表現の自由
V-02  知る自由 / 知る権利   [normalized family]
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
```

These are canonical output labels, not keyword-scoring assumptions. Phase B must predict which of these are required by the 2010 problem before teacher signals are opened.

---

## 6. Frozen Residual set — 4 candidates

### R-01 — Gifu youth-protection ordinance precedent / Ito supplementary-opinion anchor
Precedent-specific anchor retained provisionally for minors / harmful-expression analysis.

### R-02 — Third-party-owned-property confiscation precedent anchor
Precedent-specific anchor retained provisionally for third-party-right invocation.

### R-03 — Blood-transfusion-refusal precedent anchor
Precedent-specific anchor retained provisionally for explanation duty / personal autonomy.

### R-04 — Toyama University precedent anchor
Precedent-specific anchor retained provisionally for the partial-society / judicial-review framework.

No residual is absorbed or merged before the 2010 test.

---

## 7. Merge freeze

No Payload / Vocabulary / Residual merge is allowed merely because the 2010 problem makes two items look similar.

A merge remains unavailable until the preregistered conditions are met, including repeated appearance across at least three independent years, at least two materially different fact patterns, the same mediating reason / inference route, and no observed counterexample.

Any merge candidate discovered later must record **why the items were thought to share one representation**. Parent-category similarity alone is insufficient.

Gross historical additions remain immutable even if a later validated merge reduces current net model size.

---

## 8. Phase B gate

The next permitted experimental action is:

```text
open 2010 problem text only
→ execute this frozen model
→ commit 2010 problem-only prediction
→ only then open official teacher signals
```

The Phase B prediction must include:

```text
predicted_rc_path
predicted_major_issues
predicted_required_payload
predicted_required_vocabulary
predicted_unnecessary_or_suppressed_branches
predicted_answer_skeleton
explicit_failure_conditions
```

No teacher-signal material should be used to improve that prediction before it is committed.

---

## 9. What the 2010 test can falsify

The frozen model is exposed to failure if the problem / official signals later show, among other things:

- a required cognitive operation absent from the 9-unit RC;
- an existing RC that requires behavioral edit or split;
- a major issue omitted in the Phase B prediction;
- a materially wrong analytical order;
- a required Legal Payload unit not available / predicted;
- a predicted required branch that official signals materially reject or deprioritize;
- a required output vocabulary gap;
- failure of the frozen fact-to-mediating-reason procedure to generate the expected legal evaluation.

A miss is evidence. It must not be hidden by editing the frozen model and retroactively describing the edited version as the model that made the prediction.
