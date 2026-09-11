# ContextualJudgeBench (CJB) Results

**Release**: 2026-09-09 · **Model**: `turingcorp/decider-junior-v1` (Decider Junior)
**Dataset**: ContextualJudgeBench (Salesforce) — the full official set of 2,000 pairs across all 8
splits. Official reference values below are from the paper's Table 2.

---

## Protocol

- **Official vanilla pairwise protocol.**
- **Consistent accuracy**: the same verdict must be correct in **both presentation orders**;
  random floor is 25%. This is stricter than single-order accuracy and removes position effects.
- Reference model (DeepSeek V4 Flash, direct) measured on the same judged set with the same pipeline.
- **Coverage**: 1,991 / 2,000 pairs completed; 12 orders (0.3%) rerun-excluded after repeated
  platform failures — disclosed rather than imputed.

---

## Results

| Model | Overall consistent accuracy % |
|------|:--:|
| **Decider Junior** | **67.1** |
| DeepSeek V4 Flash (direct) | 65.4 |

| Split | pairs | Decider | DeepSeek V4 Flash (direct) | o1 | o3-mini | R1 |
|------|:--:|:--:|:--:|:--:|:--:|:--:|
| Refusal (Answerable) | 250 | **97.2** | 94.4 | 96.0 | 95.2 | 92.0 |
| Faithfulness (QA) | 250 | **92.3** | 90.8 | 84.4 | 76.4 | 72.0 |
| Faithfulness (Summarization) | 250 | **68.7** | 67.2 | 59.2 | 58.0 | 50.4 |
| Completeness (Summarization) | 251 | **66.8** | 64.5 | 63.7 | 59.8 | 60.6 |
| Refusal (Unanswerable) | 250 | 59.8 | **62.8** | 48.4 | 34.4 | 52.0 |
| Completeness (QA) | 250 | **52.2** | 51.6 | 48.4 | 40.4 | 41.2 |
| Conciseness (QA) | 255 | **53.7** | 50.2 | 15.3 | 20.8 | 20.4 |
| Conciseness (Summarization) | 244 | **46.1** | 41.4 | 27.0 | 35.7 | 26.2 |

The official reference columns come from the official evaluation and are context; the Decider and
DeepSeek columns were both measured by us on the same judged set, so those two are directly
comparable.

The advantage is strongest on faithfulness and refusal tasks, while the deliberately near-tie
splits sit in the 46–60% range — that is the benchmark's difficulty design, not a measurement
failure.

---

## Confidence calibration

Confidence is emitted with every judgment and calibrated against outcomes on this benchmark. It
describes **how far apart the two candidates are** in our judgment. This benchmark deliberately
contains near-tie splits, so a low value here means the two candidates are close in quality — not
that the comparison itself was unreliable.

| Confidence tier | judgments | share | accuracy % | what the value means |
|------|:--:|:--:|:--:|------|
| ≥ 90% | 789 | 19.8% | 83.3 | one candidate clearly stronger |
| 80–90% | 1,486 | 37.3% | 76.4 | one candidate clearly stronger |
| 70–80% | 1,184 | 29.7% | 63.6 | closer call |
| < 70% | 529 | 13.3% | 55.4 | near-tie: the two candidates are close in quality, each with its own strengths |

A near-tie is never presented as a confident call: every judgment ships with the value that says
how close the two candidates were.

---

## Changelog

Results measured on a subset were published previously; they are superseded by the full official
8-split run above.
