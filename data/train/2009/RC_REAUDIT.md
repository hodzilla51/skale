# 2009 Constitutional Law — Reasoning Core Re-audit

Status: **RC mutation re-audited under preregistered mutation rules**

Dataset role: `TRAIN`

This file re-audits the three 2009 Reasoning Core changes that were originally described as `refinements` in `COMPRESSION_DELTA.md`.

The re-audit applies the mutation-accounting rules later fixed in `COMPRESSION_ARCHITECTURE.md`:

- behavioral edit only if input type, output type, and one-step human execution remain materially the same;
- split when a previously single operation must expose two independently meaningful stages, especially when one stage produces an intermediate representation consumed by another;
- ambiguous edit-vs-split cases are classified conservatively as split.

This file **supersedes the RC-count interpretation in the original 2009 compression delta**. It does not change the 2009 Legal Knowledge Payload, Vocabulary, or Residual counts.

---

## 1. Re-audit result

```text
2008 baseline RC units:          8
2009 RC additions:              0
2009 behavioral edits:          2
2009 splits:                    1
2009 merges:                    0
net RC units after 2009:        9
```

The original exploratory statement `RC +0 / 3 refinements / 8 cumulative units` is therefore not retained as the mutation-accounting result.

A more accurate summary is:

```text
2009:
  unchanged baseline ops: 5
  behavioral edits:       2
  splits:                  1
  standalone additions:   0
  resulting RC units:      9
```

All eight 2008 operations were useful in some form, but only five remained unchanged under the stricter definition.

---

## 2. RC-02 re-audit — SPLIT

### 2008 form

```text
RC-02 — Route the constitutional question to the correct level

input:
  a constitutional challenge

operation:
  distinguish a defect in the rule / scheme from a defect in concrete application

output:
  rule-level route or application-level route
```

### 2009-required form

2009 first requires the examinee to distinguish multiple challenged measures arising from different conduct, rules, and constitutional interests, and only then route each measure to rule-level or application-level analysis.

```text
mixed problem containing multiple challenged measures
→ partition measures / claims
→ route each partition to rule-level or application-level analysis
```

### Classification

**SPLIT**

Reason:

The first stage produces a new intermediate representation — a set of separately identified measures / claims — which the second stage consumes. The learner can also fail the first stage while still knowing the rule-vs-application distinction. These are therefore two independently meaningful cognitive actions under the preregistered rule.

The previous decision to treat both as one broader routing operation was too permissive.

### Post-split form

```text
RC-02a — Partition challenged measures / claims
Identify distinct governmental actions, sanctions, claims, or legal disputes that require separate analysis.

RC-02b — Route each challenge to the correct level
For each partitioned challenge, distinguish rule / scheme invalidity from concrete application / disposition invalidity.
```

Net effect of the split:

```text
1 old unit → 2 executable units
net RC unit count: +1
```

---

## 3. RC-03 re-audit — BEHAVIORAL EDIT

### 2008 form

```text
RC-03 — Classify the restriction or legal relationship first
Determine what feature of the conduct or expression causes the government response before selecting the analytical test.
```

### 2009 refinement

2009 requires a broader characterization before importing doctrine:

```text
what exactly is the protected freedom / interest?
what constitutional relationship is present?
what feature causes the burden?
→ only then select doctrine / framework
```

### Classification

**BEHAVIORAL EDIT**

Reason:

The practical input remains the already-partitioned constitutional dispute. The practical output remains a legal characterization used to select the next analytical framework. No additional intermediate representation must be separately produced and consumed by another stage.

The change expands the internal classification criteria from primarily `type of restriction` to `specific protected interest + constitutional relationship + burden type`, but remains one executable characterization step.

This is therefore an edit, not a split.

### Revised form

```text
RC-03 — Characterize the actual legal relationship before selecting doctrine
Identify the specific protected interest, the constitutional relationship, and the feature producing the burden before selecting the framework.
```

---

## 4. RC-07 re-audit — BEHAVIORAL EDIT

### 2008 form

```text
RC-07 — Filter out non-fitting issues
Do not raise a doctrine merely because a surface word resembles its trigger. Check whether the doctrine actually fits and helps resolve the case.
```

### 2009 refinement

2009 reveals explicit `issue suppressors`:

```text
trigger candidate doctrine
→ check doctrinal fit
→ check whether supplied facts expressly deactivate or deprioritize the branch
→ pursue only if still useful
```

### Classification

**BEHAVIORAL EDIT**

Reason:

The input remains a candidate doctrinal branch. The output remains a pursue / suppress / deprioritize routing decision. The new material adds an internal criterion — explicit problem facts that deactivate a branch — without creating a second independently necessary cognitive stage.

### Revised form

```text
RC-07 — Filter and suppress non-fitting branches
After a doctrine is triggered, check doctrinal fit and any explicit factual suppressors before spending answer space on it.
```

---

## 5. Unchanged operations

The following 2008 operations remain materially unchanged after the 2009 observation:

```text
RC-01 — identify actor / right-holder
RC-04 — select and justify analytical framework
RC-05 — convert facts into mediating legal reasons
RC-06 — test justification concretely
RC-08 — render opposing position and independent conclusion
```

They receive new legal inputs in 2009, but their input/output type and human-executable step do not materially change.

---

## 6. Post-2009 RC version

The conservative post-2009 Reasoning Core is therefore:

```text
RC-01  identify actor / right-holder
RC-02a partition challenged measures / claims
RC-02b route each challenge to rule-level or application-level analysis
RC-03  characterize actual legal relationship
RC-04  select and justify analytical framework
RC-05  fact -> mediating legal reason
RC-06  test justification concretely
RC-07  filter / suppress non-fitting branches
RC-08  opponent + independent conclusion
```

Total: **9 executable RC units**.

This 9-unit form is the candidate RC to freeze before the 2010 prospective test unless another pre-2010 audit identifies a rule-defined defect.

---

## 7. Interpretation

The 2009 result remains encouraging, but it is weaker than the original `RC +0` headline suggested.

The correct signal is:

```text
no standalone new top-level operation
BUT
one existing operation had to split
AND
two existing operations required behavioral edits
```

This is exactly why RC mutation accounting was added. A stable-looking unit count would have hidden meaningful model movement.

The future convergence question is now sharper:

```text
Do additions, edits, and splits fall toward zero on prospectively tested years?
```

Only later frozen-model tests should answer that question.
