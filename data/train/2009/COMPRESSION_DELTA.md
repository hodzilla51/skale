# 2009 Constitutional Law — Compression Delta

Status: **first cross-year delta measured / provisional**

Dataset role: `TRAIN`

Compared artifacts:

- `data/train/2008/COMPRESSION_BASELINE.md`
- `data/train/2009/EXTRACTION.md`

This is the first cross-year compression measurement. The 2009 extraction was produced independently before this comparison.

The goal is to measure whether 2009 requires genuinely new learner-facing units, not whether its examiner observations use different wording from 2008.

## 1. Counting discipline

A 2009 observation is counted as `reused` when the 2008 model already contains an operation or payload unit capable of generating materially adequate handling of that observation.

A difference in examples, protected interests, or surface wording is not by itself a new reasoning operation.

A 2008 unit may be **refined** when 2009 reveals a broader or sharper formulation that does not require a separate human-runtime operation. Refinements are recorded explicitly so that compression is not achieved by hiding complexity inside vague labels.

Vocabulary synonyms are normalized. For example, `知る自由` and `知る権利` do not automatically count as separate vocabulary units when they function as the same canonical output concept.

## 2. Delta summary

```text
REASONING CORE
  reused baseline operations:        8 / 8
  new standalone operations:         0
  refinements to existing ops:       3
  cumulative operation units:        8

LEGAL KNOWLEDGE PAYLOAD
  reused units required by 2009:     2
  new units:                         7
  cumulative payload units:         14

LEGAL OUTPUT VOCABULARY
  reused labels required by 2009:    5
  new labels:                        8
  cumulative unique labels:         17

RESIDUALS
  new confirmed candidates:          2
  cumulative confirmed candidates:   4
  possible reused precedent anchor:  1 (not counted until source-level identity is confirmed)
```

At the operation-unit level, the 2009 reasoning task required **no new standalone Reasoning Core operation** beyond the eight-unit 2008 baseline. This is an encouraging first reuse signal, but two years are far too little to claim saturation.

The legal-specific layers behave differently: 2009 introduces substantial new doctrinal payload and vocabulary.

## 3. Reasoning Core mapping

### RC-01 — Identify the legal actor / right-holder — REUSED

2009 repeatedly requires separating X, C, and C's family members and determining whose constitutional interest is involved.

Maps primarily from 2009 O2, O9, O11, and O12.

No new operation is needed; the actors and rights are new, but the operation is the same.

### RC-02 — Route the constitutional question to the correct level — REUSED + REFINED

2009 O3 again requires separating rule-level and application/disposition-level review.

2009 O1 additionally shows that routing should begin one step earlier when a problem contains multiple challenged measures.

Refined form:

```text
partition challenged measures / claims
→ route each to rule-level or application-level analysis
```

This is recorded as a refinement rather than a ninth operation because both tasks are instances of the same routing stage and can be executed as one human step.

### RC-03 — Classify the restriction or legal relationship first — REUSED + REFINED

2009 O4 and O8 strongly reuse this operation.

The year sharpens the rule: classification is not limited to identifying a type of regulation. It also includes identifying the **specific form of the protected interest and constitutional relationship** before importing a framework.

Refined form:

```text
what exactly is the freedom / interest here?
what relationship is the government regulating?
what feature actually causes the burden?
→ only then select doctrine / framework
```

This refinement handles the difference between ordinary Article 21 information receipt and access to one's own information under an Article 13 theory.

### RC-04 — Select and justify the analytical framework — REUSED

2009 O7 is almost a direct stress test of RC-04.

The grading signals again reject canned tier selection and require a framework justified from the concrete conflict.

### RC-05 — Convert facts into mediating legal reasons — REUSED

2009 repeatedly requires turning facts about clinical risk, consent, information sensitivity, institutional responsibility, and disclosure into legal reasons.

No new operation is required.

### RC-06 — Test the justification concretely — REUSED

2009 O5, O6, O7, O10, O11, and O13 all require concrete evaluation of competing reasons such as autonomy, safety, paternalism, privacy, institutional responsibility, and consent.

These are new legal inputs but not a new reasoning procedure.

### RC-07 — Filter out non-fitting issues — REUSED + REFINED

2009 O14 and O16 strongly reuse this operation.

The year reveals a particularly useful subtype: **issue suppressors**.

Refined form:

```text
trigger candidate doctrine
→ check fit
→ check whether the problem expressly supplies a fact that deactivates or deprioritizes the branch
→ pursue only if still useful
```

The statement that prescribed procedures were carefully followed is an example of a fact that should suppress reflexive procedural-due-process analysis.

### RC-08 — Render the opposing position and an independent conclusion — REUSED

2009 O15 reuses this directly and adds an efficiency lesson: the strongest opposing view can be integrated into the examinee's own analysis instead of mechanically writing the same essay three times.

## 4. Reasoning result

Normalized 2009 reasoning can therefore still be executed by the same eight-operation skeleton:

```text
RC-01 actor / right-holder
RC-02 partition and route challenge
RC-03 classify actual legal relationship
RC-04 choose and justify framework
RC-05 fact -> mediating legal reason
RC-06 test justification concretely
RC-07 suppress non-fitting branches
RC-08 opponent + independent conclusion
```

This does **not** mean the 2009 problem is easy or contains no new legal knowledge. It means its new difficulty enters mainly through the legal-specific inputs fed into the reasoning procedure rather than through a new top-level reasoning algorithm.

## 5. Legal Knowledge Payload delta

### Reused — 2 definite units

#### Reuse P-01 — Third-party-right invocation

2008 `KP-02` is required again because X may rely on constitutional interests belonging to C or C's family.

#### Reuse P-02 — Rule-level vs application-level constitutional review

2008 `KP-03` is required again for the university rules and the concrete stop / suspension decisions.

The 2008 Article 21 information-receipt payload also acts as an important **contrast** in 2009, but it is not counted as a definite reused payload unit here because the central positive theory for one's own genetic information is different.

### New — 7 units

#### NP-01 — Article 23 academic / research freedom

The learner needs the constitutional protection of academic research and its application to an individual researcher.

#### NP-02 — University autonomy as an institutional guarantee

The learner needs the relationship between university autonomy and academic freedom, including the possibility that institutional autonomy can support restrictions on an individual researcher's activity.

#### NP-03 — Article 13 informational privacy / self-information control

The learner needs a constitutional account of access to and control of one's own sensitive information that is distinct from an ordinary Article 21 sender-recipient model.

#### NP-04 — Paternalistic restriction as a constitutional justification problem

The learner needs to recognize and evaluate a restriction imposed for the competent adult's supposed own protection rather than treating that justification as automatically sufficient.

#### NP-05 — Informed consent / explanation-duty autonomy doctrine

The learner needs the legal significance of informed consent, explanation, and autonomous medical decision-making, including the limits of relying on consent under severe information asymmetry.

#### NP-06 — Partial-society / judicial-review doctrine

The learner needs the doctrine associated with internal institutional decisions and the requirement to examine whether that framework actually applies rather than treating it as an automatic jurisdictional bar.

#### NP-07 — Public-actor constitutional routing

The learner needs the basic distinction that action by a public prefectural university is constitutionally reviewed as public action rather than automatically routed into private-party-effect analysis.

### Payload result

```text
2008 cumulative: 7
2009 new:        +7
--------------------
current total:    14
```

This is the first evidence that the Legal Knowledge Payload may grow much faster than the Reasoning Core.

## 6. Legal Output Vocabulary delta

### Reused — 5 labels

- `知る自由 / 知る権利` — normalized as the existing information-receipt label where used as the Article 21 comparator;
- `法令違憲`;
- `適用違憲`;
- `第三者の権利`;
- `審査基準`.

### New — 8 labels

- `学問の自由`;
- `大学の自治`;
- `プライバシー権`;
- `自己情報コントロール権`;
- `パターナリズム`;
- `インフォームド・コンセント`;
- `説明義務`;
- `部分社会の法理`.

These are canonical output labels, not claims that a grader performs keyword matching. A semantically correct answer may sometimes use different wording.

### Vocabulary result

```text
2008 cumulative: 9
2009 new:        +8
--------------------
current total:    17
```

The first-year vocabulary delta is therefore substantial. The saturation hypothesis remains completely open.

## 7. Residual delta

### New confirmed candidates — 2

#### NR-01 — Blood-transfusion-refusal precedent anchor

Retain the precedent-specific anchor provisionally for explanation duty / personal autonomy until later years show whether the general payload is enough for deploy memory.

#### NR-02 — Toyama University precedent anchor

Retain the precedent-specific anchor provisionally for the partial-society / judicial-review framework.

### Possible reuse — not yet counted

2009 again requires a precedent framework for third-party constitutional claims. This may reuse the 2008 third-party-right precedent anchor, but the current extraction does not establish source-level identity strongly enough to count the precedent residual itself as reused.

The general doctrine is already counted as reused payload.

## 8. Important model-structure refinement not counted as a new operation

2009 shows that a legal concept should not be stored with a permanently fixed directional sign.

Example:

```text
bad representation:
  university autonomy -> strengthens academic freedom

better representation:
  university autonomy
  -> protects institutional self-government for academic purposes
  -> may support or oppose the individual researcher's position depending on the conflict
```

This supports relational / reason-based storage rather than brittle label-to-conclusion mappings.

## 9. First empirical signal

The first cross-year result is mixed in a useful way:

```text
Reasoning Core:
  extremely high reuse so far
  0 new standalone units
  3 explicit refinements

Legal Knowledge Payload:
  substantial growth
  +7 units

Output Vocabulary:
  substantial growth
  +8 labels

Residuals:
  modest growth
  +2 precedent anchors
```

This is exactly why the four-layer decomposition matters. If all of this had been called simply "legal knowledge," the strongest signal would be invisible: **the problem changed dramatically, while the same top-level reasoning procedure still appears capable of running it.**

One year of delta evidence is not enough to infer a trend. 2010 is required before any claim about decreasing novelty is justified.

## 10. Current cumulative model size after 2009

```text
Reasoning Core operations:      8
Legal Knowledge Payload units: 14
Legal Output Vocabulary items: 17
Residual candidates:            4
```

These counts remain provisional and may later shrink through safe merges or increase through splits if future evidence shows that a unit was too broad.

## 11. Next experimental step

Do not infer saturation yet.

The next clean step is to collect the 2010 official source packet, then independently extract 2010 before calculating its delta against the cumulative 2008-2009 model.
