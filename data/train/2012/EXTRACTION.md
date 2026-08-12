# 2012 Constitutional Law — Extraction

Status: **TRAIN extraction / teacher signals opened**

This extraction is based on the 2012 public-law Question 1 problem plus the published question-intent and grading-commentary transcriptions recorded in `README.md`.

## A. Reusable reasoning observations

### O-01 — Separate litigation route from constitutional merits

The problem first asks what suit the lawyer should bring, then what constitutional argument should be made in that suit.

Runtime shape:

```text
identify procedural vehicle
→ then analyze constitutional illegality inside that vehicle
```

This is representable by RC-02a / RC-04 and does not require a new RC operation.

### O-02 — Partition the three aid targets

The aid is expressly itemized for:

```text
land / cemetery
main hall
priest residence
```

The constitutional character of each target differs. Treating the entire 75 million yen as one undifferentiated payment loses important facts.

This is a direct reuse of RC-02a.

### O-03 — Start from the legally correct constitutional provision

The existence of religion-related facts does not justify dumping every church-state provision into the answer. The public-money grant to a religious body makes Article 89 first sentence the primary entry point.

Article 20(1) second sentence and Article 20(3) matter through their relationship to that primary route.

### O-04 — Do not substitute an individual-right claim for a structural claim

D's own freedom of religion is not the central issue. The problem is the constitutionality of governmental financial support to a religious body.

A resident-suit vehicle permits the structural public-finance question to be litigated without turning the case into a personal coercion-of-belief claim.

### O-05 — Classify the recipient before testing the payment

Before debating the permissible degree of state-religion contact, determine whether A Temple is a `宗教上の組織若しくは団体` under Article 89.

The problem deliberately does not tell the examinee whether the temple or denomination is incorporated under the Religious Corporations Act. Formal incorporation status is therefore not the decisive test.

### O-06 — Build the framework from the structure and purpose of church-state separation

A bare invocation of the purpose-effect test is insufficient. The examinee must explain why strict separation is constitutionally important and why complete separation may be impossible in social reality.

This reasoning supplies the justification for the chosen framework.

### O-07 — Use precedent as a family of comparative boundary cases

The relevant precedents are not merely names to cite. They provide contrasts about:

```text
religious body or not
secular / customary contact or religious support
small ceremonial payment vs material institutional support
reasonable contact vs excessive relationship
```

The framework should be justified from this line rather than recited as an isolated slogan.

### O-08 — Convert each fact into a reason for or against religious significance

Examples:

```text
A Temple is the village's only temple
→ supports broad social significance

about 200 / 300 households are parishioners
→ indicates deep religious institutional presence, not merely a neutral civic hall

non-parishioners attend seasonal events and counseling
→ supports secular / community-use character

main hall contains Kannon and hosts worship
→ strong religious use

main hall also hosts resident counseling
→ mixed-use character

priest residence is a residence
→ secular analogy to ordinary housing

resident is the priest who manages the temple
→ support still sustains the religious institution
```

This is a heavy reuse of RC-05 and RC-06.

### O-09 — `Public character` and `religious character` are not opposites

The mayor's assertion that the temple is a public/community institution cannot simply be accepted as a legal fact.

A facility can be socially useful and religious at the same time. Public usefulness therefore does not itself erase the church-state problem.

### O-10 — Use the cemetery facts to test the claimed public character

A Temple advertises that sect does not matter, but burial is accepted only if the applicant agrees to C-sect rites. D refused that condition and could not use the cemetery.

This fact weakens the claim that the cemetery is a religion-neutral facility open to all residents.

### O-11 — Compare religious and secular reasons in both directions

Do not list facts and then announce a result. For each aid target, place the strongest secular/public justification against the strongest religious-support concern.

Runtime shape:

```text
fact supporting secular/public purpose
vs
fact supporting religious purpose/effect
→ reasoned weight
→ item-specific conclusion
```

This is representable by RC-06 and RC-08.

### O-12 — Plaintiff advocacy must remain realistic

The plaintiff's lawyer should choose the strongest realistically defensible framework and fact evaluation, not an extreme rule created so that the defendant or final view can easily defeat it.

This directly reuses the post-2011 RC-07 priority criterion.

### O-13 — Defendant response must also be realistic

Weak responses such as `the temple is not religious`, `construction is never religious`, or `the grant is not public money` should be suppressed when the facts make them implausible.

The strongest defense instead emphasizes secular disaster recovery, community function, mixed use, limited subsidy proportions, and practical limits of complete separation.

### O-14 — Precise statutory citation can itself be required Payload

The grading commentary specifically expects Local Autonomy Act Article 242-2(1)(4), not merely the label `resident litigation`.

This is a useful counterexample to the idea that all required statutory detail can be regenerated from general reasoning.

## B. Legal-specific knowledge candidates

The year introduces a largely new doctrinal shelf relative to the pre-2012 model:

```text
resident litigation route for executed local expenditure
Article 89 / Article 20 provision relationship
religious-organization classification
constitutional rationale for church-state separation
purpose-effect / reasonable-limit framework
Article 89 absolute-vs-relative prohibition question
```

## C. Vocabulary candidates

```text
住民訴訟
政教分離原則
信教の自由
宗教上の組織若しくは団体
特権付与
宗教的活動
目的効果基準
```

## D. Precedent-anchor candidates

```text
Minoo memorial / loyal-dead monument case
Tsu Jichinsai case
Ehime Tamagushiryo case
Sorachibuto Shrine case
```

These are candidates for Residual treatment because the examiner signals expect comparative understanding of their specific boundary positions, not merely one abstract church-state rule.
