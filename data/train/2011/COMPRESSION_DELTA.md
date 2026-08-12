# 2011 Constitutional Law — Compression Delta

Status: **TRAIN delta measured / not prospective generalization evidence**

Compared against the pre-2011 frozen model in `FROZEN_MODEL.md`.

Because teacher signals were exposed before a Phase B prediction commit, 2011 cannot be used as clean prospective evidence. This file measures post-exposure model fit and growth only.

## 1. Delta summary

```text
REASONING CORE
  pre-2011 units:                9
  unchanged units:               8 / 9
  standalone additions:          0
  behavioral edits:              1
  splits:                        0
  merges:                        0
  post-2011 units:               9

LEGAL KNOWLEDGE PAYLOAD
  reused units required:         6
  new units:                     5
  payload novelty rate:          5 / 11 = 45.5%
  cumulative payload units:      25

LEGAL OUTPUT VOCABULARY
  reused labels required:        6
  new labels:                    5
  vocabulary novelty rate:       5 / 11 = 45.5%
  cumulative unique labels:      29

RESIDUALS
  new confirmed anchors:         0
  cumulative confirmed:          6
```

The drop in Payload novelty is the first potentially interesting domain-recurrence signal. It is not enough to claim global saturation: 2011 revisits the already observed expression / information / privacy region, so higher reuse is expected if the existing units are meaningful.

## 2. Reasoning Core audit

### RC-01 — actor / right-holder — UNCHANGED

X is a corporate claimant; affected residents hold privacy / portrait interests; users are third parties. Existing actor separation is sufficient.

### RC-02a — partition challenged measures / claims — UNCHANGED

The model can partition:

```text
litigation route
law-level constitutional claims
clarity branch
concrete cessation-order / disposition claim
```

No new intermediate representation is required.

### RC-02b — route each challenge — UNCHANGED

The existing rule / scheme versus application / disposition routing handles the required distinction.

### RC-03 — characterize actual legal relationship — UNCHANGED

The operation can characterize X's activity as factual / visual information provision and distinguish that from business activity and users' third-party interests. The new legal content needed to recognize information provision under Article 21 is Payload, not a new reasoning operation.

### RC-04 — select and justify framework — UNCHANGED

The 2011 materials strongly validate the existing wording. The answer may discuss scrutiny or purpose-means review, but must derive the framework from the actual protected activity and conflict rather than from a memorized category.

### RC-05 — fact -> mediating legal reason — UNCHANGED

This operation is heavily exercised by the public-road / Internet-publication distinction, masking, camera height, private-life images, user utility, and secondary use.

### RC-06 — test justification concretely — UNCHANGED

The operation already permits direct analysis of competing rights, burden, effectiveness, alternatives, and concrete effects rather than only a generic scrutiny tier.

### RC-07 — behavioral edit

#### Pre-2011 form

```text
RC-07 — Filter / suppress non-fitting branches
After a doctrine is triggered, check doctrinal fit and explicit factual suppressors before spending answer space on it.
```

#### 2011-required sharpening

2011 shows that a branch can be legally available and still deserve suppression or deprioritization because another claimant-side theory is materially stronger and more responsive to the actual dispute.

Example:

```text
business freedom:
  legally available
  but strategically weaker than a properly constructed expression / information-provision claim
```

The input remains candidate doctrinal branches. The output remains pursue / suppress / deprioritize. There is no new intermediate representation and no second independently executable stage.

Classification: **BEHAVIORAL EDIT**.

#### Revised form

```text
RC-07 — Filter, suppress, and prioritize candidate branches
For each candidate branch, check doctrinal fit, factual suppressors, task relevance,
and relative legal / strategic strength before allocating answer space.
```

This remains one human-executable routing step.

### RC-08 — opponent + independent conclusion — UNCHANGED

The existing operation already requires a responsive opposing position and an independent conclusion. 2011's warning against disconnected plaintiff / defendant / own-view mini-essays is fully representable.

## 3. RC mutation result

```text
2011 TRAIN fit:
  additions: 0
  edits:     1
  splits:    0
  merges:    0
  net units: 9
```

The RC count remains 9, but the model is not declared converged because one internal routing criterion changed.

## 4. Legal Knowledge Payload reuse — 6 units

### RP-01 — P-01 Article 21 expression / information provision family

The year centrally reuses Article 21 protection, while requiring a new subtype for factual information provision recorded below.

### RP-02 — P-02 third-party-right invocation

X should not build its principal claim around users' generic information interests. The existing third-party-right discipline is directly useful.

### RP-03 — P-03 rule-level vs application-level constitutional review

This distinction is central again.

2011 sharpens the learner-facing cue:

```text
law-level review -> legislative / general facts
application-level review -> concrete images / concrete order / claimant facts
```

This is retained as the same payload unit because it is the same legal distinction with more explicit evidentiary routing, not a second independent rule.

### RP-04 — P-04 content-based speech regulation

Content-related classification is relevant as a candidate analytical route, but the year expressly rejects automatic `content regulation -> strict scrutiny -> result` reasoning.

### RP-05 — P-06 constitutional clarity

Clarity is reused, but only in a targeted way tied to the disputed statutory phrase and expressive activity. Generic vagueness discussion is not enough.

### RP-06 — P-10 informational privacy / self-information control family

The existing Article 13 privacy family is reused as the basis for the opposing informational / private-life interest. 2011 clarifies that the family also includes protection against public exposure of private-life information, not merely access to one's own records.

If later years show materially different rules for access, control, disclosure, and portrait interests, this unit may require a future split. No split is justified yet.

## 5. New Legal Knowledge Payload — 5 units

### NP-2011-01 — Revocation action against an existing administrative cessation order

Where X has already received a ministerial cessation order, the basic litigation route is an action seeking revocation / cancellation of that disposition. The constitutional claims are advanced within that challenge; the essay need not become a full administrative-law treatise.

### NP-2011-02 — Minimal corporate constitutional-right capacity

A corporation may invoke constitutional rights whose nature permits corporate enjoyment. In this problem the learner must at least be able to treat X as capable of asserting an expression-related interest without spending a long paragraph on corporate-right theory.

### NP-2011-03 — Business freedom as an available but secondary claimant theory

Commercial provision of the service implicates business / occupational freedom, but that theory does not capture the central constitutional conflict as strongly as a properly constructed information-provision theory. It may remain secondary or become relevant to economic loss / damages analysis.

### NP-2011-04 — Factual information provision / free flow of information under Article 21

Article 21 protection is not confined to a speaker's personal opinions or political advocacy. Provision and circulation of factual / visual information can receive constitutional protection where a persuasive theory of free information flow is supplied.

This is the major new positive-law / doctrine-specific input of 2011.

### NP-2011-05 — Portrait and private-life exposure beyond direct identification

Constitutionally relevant privacy harm can arise from publication of a person's appearance, whereabouts, home, family life, or living patterns even when direct identifying information such as a face or name is masked. The legal interest is therefore broader than simple name / face identification.

The Internet-specific amplification of that harm is generated through facts and RC-05 / RC-06 rather than stored as a separate doctrine.

## 6. Payload novelty history

```text
2009: 7 new / (7 + 2 reused) = 77.8%
2010: 6 new / (6 + 1 reused) = 85.7%
2011: 5 new / (5 + 6 reused) = 45.5%
```

Interpretation:

2011 is the first return to a previously observed expression / information / privacy knowledge region. The resulting novelty decline is compatible with local saturation, but one revisit is not sufficient evidence that the whole constitutional Payload pool is approaching saturation.

The useful future test is whether later revisits to the same region continue to show low novelty.

## 7. Legal Output Vocabulary reuse — 6

- `表現の自由`
- `法令違憲`
- `適用違憲 / 処分違憲` [normalized family]
- `明確性`
- `審査基準`
- `プライバシー権`

## 8. New Legal Output Vocabulary — 5

- `取消訴訟`
- `営業の自由 / 職業の自由` [normalized family]
- `情報提供の自由`
- `肖像権`
- `立法事実`

Vocabulary novelty:

```text
2009: 8 / (8 + 5) = 61.5%
2010: 7 / (7 + 3) = 70.0%
2011: 5 / (5 + 6) = 45.5%
```

Again, this is a local recurrence signal, not proof of global vocabulary saturation.

## 9. Residual result

No new precedent anchor is confirmed as a necessary standalone Residual.

The official materials expect awareness of important / basic precedents but do not make a single named precedent anchor indispensable enough in the current extraction to justify a new Residual count.

Do not invent a precedent residual merely because a familiar case could be cited.

## 10. Merge discipline

No validated merge is performed.

2011 is only the third year overall, but merge eligibility also requires recurrence of the same mediating reason across at least three independent years and at least two materially different surface fact patterns. No candidate newly satisfies the full preregistered admission rule here.

Gross historical additions remain immutable.

## 11. Current cumulative sizes after 2011

```text
Reasoning Core:          9
Legal Knowledge Payload: 25
Output Vocabulary:       29
Residual candidates:      6
```

## 12. Experimental interpretation

2011 gives a mixed but more informative signal than 2010:

```text
Reasoning Core:
  still compact
  but RC-07 required one behavioral edit

Payload:
  novelty fell sharply on a return to an already observed doctrinal region

Vocabulary:
  novelty also fell on the same recurrence

Residuals:
  no growth this year
```

The key question is now domain-conditional rather than merely chronological:

```text
When a doctrinal region is revisited,
does the frozen model mostly reuse existing Payload / Vocabulary?
```

2011 provides the first positive observation for that narrower hypothesis, but not enough repetitions to establish a trend.
