# JudgeBench Results

**Release**: 2026-09-08 · **Model**: `turingcorp/decider-junior-v1` (Decider Junior)
**Dataset**: JudgeBench, 620 pairs — sources: MMLU-Pro / LiveBench Reasoning / Math / LiveCodeBench

---

## Protocol

- **Official judging protocol**. Both columns use the first successful verdict per pair.
- Reference model (DeepSeek V4 Flash, direct) measured on the same judged set with the same pipeline.
- **Coverage**: 614 / 620 pairs scored. 6 pairs were rerun-excluded after repeated platform
  failures — disclosed rather than imputed.

---

## Results

| Model | Accuracy % |
|------|:--:|
| **Decider Junior** | **92.5** |
| DeepSeek V4 Flash (direct) | 92.2 |
| Agreement between the two | 96.1 |

| Segment | pairs | Decider | DeepSeek V4 Flash (direct) |
|------|:--:|:--:|:--:|
| Knowledge (MMLU-Pro) | 303 | 88.8 | 87.8 |
| Reasoning (LiveBench) | 149 | **98.0** | 96.6 |
| Math (LiveBench) | 90 | 92.2 | **95.6** |
| Code (LiveCodeBench) | 72 | 97.2 | 97.2 |

Decider's advantage is concentrated in reasoning-style judgments; on this benchmark the two models
are effectively level overall.

---

## Confidence calibration

Confidence is emitted with every judgment and calibrated against outcomes on this benchmark. It
describes **how far apart the two candidates are** — and the accuracy column shows what that
delivered here. Set your own threshold from the accuracy column; for high-stakes or irreversible
decisions, apply your own review policy.

| Confidence band | judgments | share | observed accuracy | what the value means | suggested use |
|------|:--:|:--:|:--:|------|------|
| ≥ 90% | 283 | 45.6% | 99.6 | one candidate clearly stronger | Act on it |
| 80–90% | 184 | 29.7% | 94.0 | one candidate stronger | Go with it |
| 70–80% | 82 | 13.2% | 84.1 | closer call | Act on it after a quick look |
| < 70% | 65 | 10.5% | 67.7 | near-tie — evenly matched | Either choice is fine |

A high value means the comparison was decisive and the pick can be acted on directly; a low value
means the two are close in quality, where either choice is defensible.

---

## Raw data

Question-level results are available on request during the preview phase.
