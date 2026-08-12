# SKALE Dataset Split — Constitutional Law MVP

This file freezes the first experimental split for the constitutional-law MVP.

The purpose is to protect genuinely unseen material before model construction begins.

## Scope

- Exam: Japanese Judicial Examination (司法試験本試験)
- Subject: Constitutional Law / public-law constitutional component
- Primary official materials per year: question, official question intent, official grading commentary where available
- Split direction: chronological, oldest to newest

## Frozen split

```text
TRAIN
2008–2017

VALIDATION
2018–2021

SEALED HOLDOUT
2022–2025
```

## Rules

### TRAIN — 2008–2017

May be freely collected, read, analyzed, quoted internally, summarized, and reused for model construction.

This corpus is used to build SKALE Constitutional Model v0.

### VALIDATION — 2018–2021

Must not be used during initial v0 construction.

Open one year at a time only after the current model version and evaluation criteria have been frozen.

After a validation year is opened, it becomes exposed material and may be used for subsequent model revision and runtime practice.

### SEALED HOLDOUT — 2022–2025

Must not be opened or analyzed during model construction or ordinary validation.

Do not retrieve or inspect:

- the exam problem;
- official question intent;
- grading commentary specific to the year;
- detailed model answers or reproduction answers;
- AI summaries that reveal the problem structure, decisive issues, or expected answer.

These years are reserved for high-value model-generalization tests.

A holdout year becomes consumed once materially exposed and must never again be described as genuinely unseen.

## Runtime testing

Human Runtime testing should preferentially use already exposed TRAIN or VALIDATION problems.

Fresh SEALED HOLDOUT material is not required to test:

- model activation latency;
- closed-book recall;
- fact → mediating reason conversion;
- answer rendering;
- time-limit execution;
- delayed retention.

## Contamination log

If any validation or holdout material is accidentally exposed, record it here immediately rather than silently retaining its status.

```text
Date | Year | Previous status | Exposure | New status | Notes
-----|------|-----------------|----------|------------|------
```

## 2026

The 2026 examination is outside this first frozen split. Its role will be decided later; do not use it for model construction until explicitly assigned.

## Freeze rule

This split must not be changed merely because later results are inconvenient.

A revision is permitted only for a documented methodological reason (for example, missing official source material or a major legal-regime incompatibility), and the revision must be committed before the affected material is inspected.
