# JudgeBench Results

**Release**: 2026-09-08 · **Model**: `turingcorp/decider-junior-v1` (Decider Junior)
**Dataset**: JudgeBench, 620 pairs — sources: MMLU-Pro / LiveBench Reasoning / Math / LiveCodeBench

---

## Protocol

- **Official judging protocol**, first-verdict-per-pair accounting.
- Reference model (DeepSeek V4 Flash, direct) measured on the same judged set with the same pipeline.
- **Coverage**: 614 / 620 pairs scored. 6 pairs were rerun-excluded after repeated platform
  failures — disclosed rather than imputed.

---

## Results

| Model | Accuracy % |
|------|:--:|
| **Decider Junior** | **92.5** |
| DeepSeek V4 Flash (direct) | 92.7 |
| Agreement between the two | 95.9 |

| Segment | pairs | Decider | DeepSeek V4 Flash (direct) |
|------|:--:|:--:|:--:|
| Knowledge (MMLU-Pro) | 303 | 88.8 | 88.8 |
| Reasoning (LiveBench) | 149 | **98.0** | 96.6 |
| Math (LiveBench) | 90 | 92.2 | **95.6** |
| Code (LiveCodeBench) | 72 | 97.2 | 97.2 |

Decider's advantage is concentrated in reasoning-style judgments; on this benchmark the two models
are effectively level overall.

---

## Confidence calibration

Confidence is emitted with every judgment and calibrated against outcomes on this benchmark. It
describes **how far apart the two candidates are** in our judgment: a high value means one of them
is clearly stronger, a low value means the two are close in quality and each has its own strengths.

| Confidence tier | judgments | share | accuracy % | what the value means |
|------|:--:|:--:|:--:|------|
| ≥ 90% | 283 | 45.6% | 99.6 | one candidate clearly stronger |
| 80–90% | 184 | 29.7% | 94.0 | one candidate clearly stronger |
| 70–80% | 82 | 13.2% | 84.1 | closer call |
| < 70% | 65 | 10.5% | 67.7 | near-tie: the two candidates are close in quality, each with its own strengths |

Accuracy tracks the value on this benchmark, so it is a reading of how decisive the comparison
was — not a verdict on either candidate taken on its own.

---

## Raw data

Question-level results are available on request during the preview phase.
