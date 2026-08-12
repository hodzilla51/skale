# 2008 Constitutional Law — Year Extraction

Status: **year-level observation complete / not yet generalized across years**

Dataset role: `TRAIN`

This file records what the 2008 constitutional-law essay appears to require **within this year only**. It is not yet a cross-year SKALE model.

## 1. Source hierarchy

Source of record:

- Ministry of Justice — 2008 public-law essay problem
- Ministry of Justice — 2008 official question intent
- Ministry of Justice — 2008 grading commentary

Official source pages are listed in `README.md`.

For machine-readable inspection, the archived copy of the official Ministry of Justice grading document and the official examiner-hearing document preserved by Kagoshima University were also used. They reproduce Ministry of Justice / Judicial Examination Committee documents. No prep-school model answer was used as authority for the extraction below.

## 2. Task shape observed in 2008

The constitutional component uses a fictional statute requiring filtering software intended principally to protect minors from harmful Internet content. A operates a website concerning matters such as war / peace and capital punishment, including disturbing imagery. The site is filtered, and A later provides a program that bypasses the filtering effect for A's site. A is prosecuted under the fictional statute.

The examinee is required to:

1. construct constitutional arguments from A's defense perspective;
2. anticipate the prosecution's opposing position;
3. state and justify the examinee's own view.

The examiner materials make clear that merely listing every conceivable constitutional issue is not the objective. The expected performance is to identify the important issues, analyze the concrete facts, give reasoned legal evaluation, and reach a persuasive conclusion.

## 3. Examiner-required analytical operations

### O1 — Identify whose right is actually burdened

Do not collapse A's freedom of expression and the audience's freedom to receive information into one undifferentiated claim.

If A relies on rights held by viewers / third parties, the answer must address why A may invoke those third-party rights.

Observed authority signal:

- third-party-owned-property confiscation precedent (第三者所有物没収事件判決)

### O2 — Separate law-level attack from application-level attack

The examiner materials repeatedly distinguish:

- `法令違憲` — defects in the statute / regulatory scheme itself;
- `適用違憲（処分違憲）` — defects arising from how the scheme operates against A in the concrete case.

Individual facts about A must not be used casually as reasons that the statute itself is unconstitutional.

### O3 — Correctly classify the restriction before selecting the test

The regulation focuses on the content / harmfulness of expression. The fact that the medium is the Internet does not make it merely a regulation of a method of communication.

The answer must therefore classify the restriction before selecting and applying a constitutional review framework.

### O4 — Select and justify the review framework

The examiner materials reject mechanical recitation of a review standard.

The answer should explain:

- why a particular level / form of review is appropriate;
- whether the ordinary framework should be modified because minors and harmful expression are involved;
- what purpose the government must show;
- what relationship between purpose and means is required.

Merely naming a strict / intermediate / rational standard is insufficient.

### O5 — Evaluate purpose and means concretely

After choosing a framework, the answer must still evaluate the facts.

Relevant operations include:

- evaluate the importance / legitimacy of protecting minors;
- evaluate the evidentiary or legislative basis for the asserted harm;
- examine whether the filtering scheme is sufficiently tailored;
- examine effectiveness;
- examine whether burdens are broader than necessary;
- examine burdens imposed on adults as well as minors.

### O6 — Analyze breadth of the filtering mechanism

A major year-specific feature is that the mechanism can block an entire website because it contains harmful pages.

The examiner materials treat this as an obvious point requiring analysis.

### O7 — Analyze clarity and delegated rulemaking

The answer should consider:

- the clarity of the definition of harmful information;
- the relationship between freedom of expression and Article 31-style clarity concerns;
- whether subordinate rules can cure insufficient clarity;
- whether essential / important matters were impermissibly delegated.

### O8 — Treat child protection as a reason-bearing variable, not a magic word

The fact that the statute protects persons under 18 may justify a different degree of constitutional protection or a modified review framework, but the answer must explain why and how.

A generic freedom-of-expression paragraph is not enough.

### O9 — Evaluate burdens on adult recipients

Adults may not be absolutely prohibited from access, but procedural burden is still legally relevant.

The analysis should ask whether that burden is constitutionally significant and how it relates to the audience's freedom to receive information.

### O10 — Use A-specific facts in the application-level analysis

The examiner materials specifically identify facts such as:

- A warned viewers before disturbing images appeared;
- A's materials concerned socially important subjects;
- A's bypass program targeted access to A's own site rather than generally destroying filtering;

as facts that should be legally evaluated rather than ignored or copied mechanically.

### O11 — Distinguish useful arguments from reflexive issue spotting

Many examinees reflexively raised censorship (`検閲`). The examiner hearing says the conventional censorship concept does not straightforwardly fit the case.

The broader operation is:

> Do not raise an issue merely because the surface vocabulary activates it. Ask whether the existing legal concept actually fits the facts and whether pursuing it helps resolve the case.

### O12 — Render adversarial reasoning, then an independent conclusion

The second part is not satisfied by saying "the prosecution disagrees" and then repeating the defense.

The answer must:

- articulate a meaningful opposing rationale;
- compare the competing positions;
- give an independently reasoned conclusion.

The examiner materials expressly allow a conclusion different from both sides and from precedent, provided the reasoning is persuasive.

## 4. Raw Fact → Mediating Legal Reason → Legal Representation candidates

These are **2008 observations**, not yet reusable cross-year rules.

| Raw fact | Mediating legal reason | Legal representation / operation |
|---|---|---|
| A whole site can be blocked because some pages are classified harmful | Protected material may become inaccessible together with the targeted material | breadth / tailoring of the law-level scheme |
| Regulation turns on gruesome / harmful content | Government action is triggered by communicative content rather than merely the transmission channel | content-based expression restriction |
| The primary protected class is under 18 | Minors may justify stronger protection, but the justification must explain any relaxation of ordinary speech protection | review-standard modification / competing interest |
| Adults can obtain access only after following a procedure | The scheme does not absolutely prohibit adult access, but it creates friction on lawful receipt of information | burden on adult `知る自由` / tailoring |
| A places a warning before disturbing material | Voluntary exposure can be reduced without blocking all access, weakening the necessity of the concrete restriction against A | application-level tailoring / less burdensome response |
| A's material concerns peace / war / capital punishment | Disturbing imagery may still carry substantial public-discourse value | weight of protected expression |
| A's bypass program enables access to A's own site | Punishing a narrowly targeted workaround may burden more speech than needed to protect the filtering system generally | proportionality / overbreadth at application level |
| A invokes viewers' ability to receive the information | The right-holder is not automatically A; relying on another person's right requires an additional justification | third-party-right invocation |
| A-specific warning / purpose is used to attack the statute as such | A fact about one application does not necessarily show that the legal rule is invalid in all / general applications | facial-vs-as-applied routing error |

## 5. Strong grading-failure signals

The 2008 grading commentary is unusually explicit about failure modes.

### F1 — Memorized doctrine dump

A recurring weak pattern was to reproduce stock freedom-of-expression doctrine without adapting it to the concrete problem.

### F2 — Formalistic `当てはめ`

The examiners reject the idea that one can memorize an abstract rule and mechanically insert facts into it. They describe the required process as flexible concretization of legal theory in light of the individuality of the case.

### F3 — Failure to evaluate supplied facts / materials

Copying a fact or source is not enough. The answer must state what legal meaning the fact has and why.

### F4 — Confusion between law-level and application-level review

A-specific facts were frequently misused as reasons for law-level invalidity.

### F5 — Failure to identify the relevant right-holder

Many answers mixed A's expression interest with the recipients' freedom to know without addressing third-party-right invocation.

### F6 — Medium/content category error

Some answers treated Internet regulation as a method / channel regulation even though the scheme classified material by content.

### F7 — Review-standard label without reasoning

The examiners criticize answers that name a standard without explaining why it applies or how the facts affect purpose, fit, effectiveness, necessity, etc.

### F8 — Reflexive issue accumulation

The examiner hearing expressly says that collecting every possible issue is not rewarded. Important issues should be selected and developed deeply enough to solve the case.

### F9 — Opposing positions stated abstractly

Writing "rights are not absolute" for the prosecution, without a concrete reasoned counter-analysis, is insufficient.

### F10 — Conclusion without legal reasoning chain

The examiner hearing identifies failure of legal syllogistic structure: issue / rule / reason for rule / fact evaluation / effect / conclusion.

## 6. Authorities / doctrinal anchors explicitly signaled by examiner materials

- Constitution Article 21 / freedom of expression and receiving information
- Constitution Article 31 in relation to clarity
- 岐阜県青少年保護育成条例事件判決, including attention to the Ito supplementary opinion's framework
- 第三者所有物没収事件判決 for third-party-right invocation
- distinction between `法令違憲` and `適用違憲（処分違憲）`
- doctrine concerning clarity / vagueness and delegation
- review frameworks for content-based restrictions on expression

This list records signals visible in the examiner materials. It is not yet a complete doctrinal backfill.

## 7. Candidate year-level procedure

The following is a compact description of the **2008-required process**, not yet a constitutional parent model:

```text
Identify claimant / right-holder
→ separate statute-level and application-level attacks
→ classify the restriction
→ identify the protected and opposing interests
→ choose and justify the review framework
→ translate concrete facts into legal reasons
→ test purpose / fit / breadth / burden / alternatives
→ address third-party-right and procedural issues where relevant
→ articulate the opposing case
→ give an independently reasoned conclusion
```

## 8. Particularly important SKALE observation from 2008

The strongest repeated examiner signal is not a particular constitutional formula.

It is the transformation:

```text
Raw fact
→ why that fact matters legally
→ what part of the constitutional analysis it changes
→ answer sentence
```

The examiners repeatedly criticize answers that either omit facts or merely copy them. This strongly supports preserving a `Mediating Legal Reason` layer in SKALE rather than a simple fact-to-factor lookup table.

## 9. What is deliberately NOT done yet

- no comparison with 2009 or later years;
- no claim that the procedure above is universal to constitutional law;
- no parent-model merge;
- no frequency weighting across years;
- no deploy representation for the learner;
- no doctrinal backfill beyond what examiner materials visibly signal;
- no validation against 2018+ material.

## 10. Next step if approved

Collect the official 2009 packet only.

Do not yet merge 2008 into a cross-year model. The intended sequence is to produce one independent observation artifact per training year, then normalize vocabulary and synthesize only after the ten training years have been extracted.
