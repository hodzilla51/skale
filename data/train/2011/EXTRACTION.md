# 2011 Constitutional Law — Year-Level Extraction

Status: **TRAIN extraction complete / teacher-signal guided**

Dataset role: `TRAIN`

Source packet: `README.md`

This extraction records the 2011 problem as a year-level observation before computing cross-year compression. Because the prospective test was contaminated, the extraction may use official question intent and grading commentary.

## 1. Problem structure

X company provides an Internet map / panoramic-image service. A statutory scheme regulates image collection and publication to protect individuals from privacy and related harms. After X declines to correct some images revealing private life, the responsible minister orders cessation of the service.

The answer must:

```text
identify the litigation route
→ construct X's constitutional claims
→ distinguish law-level and disposition-level arguments
→ anticipate the government's response
→ give an independent reasoned conclusion
```

## 2. Year-level reasoning observations

### O-2011-01 — The procedural route is part of the required output

The problem expressly asks what litigation X should file. The procedural route should be stated briefly; turning the constitutional essay into a long administrative-procedure essay is a mistake.

### O-2011-02 — Choose the strongest claimant-side constitutional theory

Several interests are superficially available: expression / information provision, business freedom, users' information interests, corporate-right questions, and others.

The task is not to list every plausible right. The examiner signals require choosing the theory that best characterizes X's activity and gives the strongest coherent constitutional claim.

### O-2011-03 — Expression can require construction beyond speech of opinion

The map service does not primarily communicate X's personal ideas or political opinions. A satisfactory theory must explain why factual / visual information provision can nevertheless fall within Article 21, for example through the constitutional value of a free flow of information.

This is not solved by merely attaching the label `表現の自由`.

### O-2011-04 — The concrete value of the information matters

The information has convenience and anti-fraud utility, but it is not strongly connected to political self-government, public-official scrutiny, or classic public-affairs reporting.

The constitutional weight of the activity therefore depends on what this information actually does rather than on a generic hierarchy of rights.

### O-2011-05 — The competing interest is concrete privacy / portrait harm

The opposing side is not an abstract government interest alone. The statute protects persons from exposure of identifying information, appearance, location, home life, and other private-life information.

The legal analysis must characterize the protected private interest with comparable specificity.

### O-2011-06 — Public visibility is not equivalent to Internet publication

A central factual bridge is:

```text
visible from a public road at a moment in time
!=
searchable / reproducible / scalable Internet publication
```

Internet publication changes the reach, persistence, aggregation, and ease of secondary use of the information. These are mediating legal reasons, not independent memorized doctrines.

### O-2011-07 — Distinguish facial / scheme analysis from disposition analysis

The answer must not use X's individual circumstances as if they were the legislative facts proving facial invalidity.

Conversely, disposition-level constitutional analysis must examine the concrete images and the actual cessation order, not merely repeat abstract objections to the statute.

### O-2011-08 — Clarity is a targeted issue, not a generic branch

A general attack on ordinary statutory phrases is weak. If clarity is raised, the real focus is whether the statutory concept of rights-infringing information gives adequate guidance as applied to images revealing a resident's private life.

The issue must also be connected to the expressive activity rather than treated as a rote Article 31 paragraph only.

### O-2011-09 — Compliance with some safeguards narrows the real dispute

X already masks direct identifying information and complies with the statutory camera-height limit. The remaining dispute therefore concerns images that reveal private life even without direct facial / name identification.

Those facts route the answer toward the actual residual conflict instead of reopening every statutory requirement.

### O-2011-10 — Several tempting branches are expressly suppressible

The examiner materials signal that a strong answer should not waste space on, among other things:

- procedural due process where the problem says the Administrative Procedure Act was followed;
- censorship merely because prior reporting / regulation exists;
- a user's generic `知る権利` as X's principal claim;
- a long corporate-right-capacity essay;
- generic clarity discussion detached from the concrete wording;
- a mechanical `expression -> strict scrutiny -> conclusion` template.

### O-2011-11 — A legally available claim may still be strategically weak

Business freedom is not doctrinally impossible. But as the principal claimant-side theory it is weaker than a properly constructed information-provision / expression theory in this dispute.

This is distinct from simple doctrinal fit: the learner must prioritize among fitting branches.

### O-2011-12 — Scrutiny labels do not replace the rights conflict

A framework may be stated, but the answer still has to compare the concrete expressive / informational value with the concrete privacy and portrait harms.

The examiner materials expressly criticize answers that infer the result from labels such as `内容規制`, `厳格審査`, or abstract purpose-means phrases without case-specific analysis.

### O-2011-13 — Facts must be converted into reasons on both sides

Examples:

```text
user convenience / anti-fraud use
→ genuine social value of information provision

home / balcony / interior visibility
→ exposure of private-life information beyond direct identification

Internet publication and secondary use
→ scale / persistence / harm-amplification concern

masking + lower camera height already implemented
→ dispute is narrower than a total rejection of privacy safeguards

full service cessation
→ severity of burden and possible overbreadth / proportionality concern
```

### O-2011-14 — Opponent and own view must actually engage

The government's response must answer X's best theory, and the examinee's own view must resolve that actual conflict. Three disconnected mini-essays are not adequate.

## 3. Candidate learner-facing legal inputs revealed by 2011

Without yet deciding reuse vs novelty, the year requires access to legal knowledge concerning:

- the litigation form for challenging an administrative cessation order;
- constitutional-right capacity of a corporate actor at least at a minimal level;
- expression protection for factual / informational provision beyond personal opinion;
- business freedom as an alternative but weaker claimant theory;
- constitutional protection of privacy / portrait / private-life exposure;
- facial versus disposition constitutional review;
- clarity / vagueness in an expression-related setting;
- content-related regulation without automatic tier selection.

Cross-year classification is deferred to `COMPRESSION_DELTA.md`.

## 4. Key 2011 semantic bridge

The year's most important reusable bridge is:

```text
raw fact:
  something can be seen from a public road

mediating legal reason:
  ordinary momentary visibility does not imply consent to searchable,
  persistent, globally distributable publication and secondary use

analysis effect:
  privacy harm can be materially greater on the Internet
  even if the underlying image was captured from a lawful public location
```

This strongly exercises the SKALE `fact -> mediating legal reason` design.

## 5. Interpretation before compression

2011 is another strong warning against treating constitutional essays as a lookup table from right-label to scrutiny tier.

The difficulty lies in:

```text
choosing / constructing the actual protected activity
+ identifying the real opposing interest
+ suppressing superficially available but weak branches
+ using concrete facts to compare them
```

Whether this requires new Reasoning Core structure or only new legal payload is decided in the delta audit.
