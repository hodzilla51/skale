# 2008 Constitutional Law — Compression Baseline

Status: **baseline classified / provisional until cross-year comparison**

Dataset role: `TRAIN`

Source observation artifact: `EXTRACTION.md`

This file reorganizes the 2008 extraction under the four-layer architecture in `COMPRESSION_ARCHITECTURE.md`. The purpose is to create a countable baseline for measuring later-year deltas, not to claim that the units below are already universal constitutional-law rules.

## 1. Counting rule

Count one unit only when removing it would plausibly prevent the model from generating a materially adequate 2008 answer. Do not count synonyms, stylistic variants, raw problem facts, or generic Japanese prose as separate units. Counts are provisional: later years may justify merging, splitting, or reclassifying units.

## 2. Baseline counts

```text
Reasoning Core operations:      8
Legal Knowledge Payload units:  7
Legal Output Vocabulary items:  9
Residual candidates:            2
```

These are baseline sizes, not a compression ratio. Reuse can only be measured from 2009 onward.

## 3. Reasoning Core — 8 operations

### RC-01 — Identify the legal actor / right-holder
Determine whose protected interest is affected and keep different persons' rights distinct.

### RC-02 — Route the constitutional question to the correct level
Separate a problem in the rule or scheme itself from a problem in its concrete application.

### RC-03 — Classify the restriction or legal relationship first
Determine what feature of the conduct or expression causes the government response before selecting the analytical test.

### RC-04 — Select and justify the analytical framework
Do not merely name a standard. Explain why it fits the type and intensity of burden and the competing interest.

### RC-05 — Convert facts into mediating legal reasons
For each important fact, explain why it matters legally and which part of the analysis it changes.

### RC-06 — Test the justification concretely
Evaluate purpose, fit or effectiveness, breadth, burden, necessity, alternatives, and effects on other affected persons where relevant.

### RC-07 — Filter out non-fitting issues
Do not raise a doctrine merely because a surface word resembles its trigger. Ask whether the doctrine actually fits and helps resolve the case.

### RC-08 — Render the opposing position and an independent conclusion
Give a meaningful counter-position, compare both sides, and state a reasoned conclusion.

## 4. Legal Knowledge Payload — 7 units

### KP-01 — Article 21 protection of expression and receipt of information
Expression and the audience's information interests may both receive constitutional protection and may belong to different actors.

### KP-02 — Use of a third party's right requires additional legal justification
A claimant cannot automatically rely on a constitutional right belonging to viewers or another person.

### KP-03 — Rule-level and application-level constitutional review are distinct
The legal target of the constitutional argument changes depending on whether the rule itself or its concrete use is challenged.

### KP-04 — Content-based speech regulation changes the review analysis
A restriction triggered by communicative content is legally different from one directed only at the medium or method.

### KP-05 — Protection of minors / harmful expression may modify ordinary speech analysis
The child-protection context may affect the review framework, but the modification must be legally explained rather than assumed.

### KP-06 — Constitutional clarity doctrine
The definition of regulated expression may itself create a constitutional clarity problem, with Article 31-style concerns appearing in the examiner materials.

### KP-07 — Delegation has legal limits
Subordinate rulemaking does not automatically cure an insufficient statutory structure, and important matters may require adequate legislative definition.

## 5. Legal Output Vocabulary — 9 items

| ID | Canonical label | Plain semantic cue |
|---|---|---|
| V-01 | `表現の自由` | protected communication of ideas or information |
| V-02 | `知る自由` | protected interest in receiving information |
| V-03 | `内容規制` | regulation changes because of what the expression says or shows |
| V-04 | `法令違憲` | the legal rule or scheme itself is constitutionally defective |
| V-05 | `適用違憲` | the concrete application is constitutionally defective |
| V-06 | `明確性` | the legal boundary is insufficiently clear |
| V-07 | `委任` | authority or detail is assigned to subordinate rulemaking |
| V-08 | `第三者の権利` | the asserted right belongs to someone other than the claimant |
| V-09 | `審査基準` | the form or level of constitutional review |

The vocabulary count does not imply keyword scoring. The deployment hypothesis is `ordinary semantic concept -> canonical legal label -> concise answer language`.

## 6. Residual candidates — 2

### RS-01 — Gifu youth-protection ordinance precedent / Ito supplementary-opinion anchor
The examiner materials specifically signal this precedent family in relation to minors and harmful expression. Its precedent-specific content is retained provisionally until later years show whether the broader payload is sufficient.

### RS-02 — Third-party-owned-property confiscation precedent anchor
The general doctrine is represented as `KP-02`, but the precedent-specific anchor is retained separately for now. Later evidence may show that it can be removed from deploy memory.

## 7. Raw facts are not memory units

The specific 2008 facts matter because they exercise `RC-05`; they are not items the learner should memorize for future questions. SKALE should retain reusable reasons for why classes of facts matter rather than storing each historical fact pattern.

Examples of 2008 semantic bridges include:

```text
broad blocking of protected material
-> protected expression is swept in with targeted expression
-> breadth / tailoring concern

warning before disturbing material
-> exposure can be reduced by a lighter mechanism
-> necessity / alternative-means concern

socially important subject matter
-> disturbing form does not eliminate public-discourse value
-> increases the weight of protected expression

extra procedure for adult access
-> lawful access is burdened even without an absolute prohibition
-> burden on the audience's information interest
```

## 8. Delta fields for 2009+

After each later year is extracted independently, compare it against the existing model and record:

```text
new_reasoning_operations
reused_reasoning_operations
new_legal_payload_units
reused_legal_payload_units
new_output_vocabulary
reused_output_vocabulary
new_residuals
```

Do not use this baseline to force the next year's extraction into the 2008 structure. Extract the next year independently first, then compute the delta.

## 9. Current interpretation

2008 separates into a relatively small reasoning layer and a bounded set of legal-specific payload and labels. That is encouraging but is not evidence of saturation. The first meaningful evidence about compression begins with the 2009 delta.
