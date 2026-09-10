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

Confidence is emitted with every judgment and validated against outcomes on this benchmark:

| Confidence tier | judgments | share | accuracy % | routing guidance |
|------|:--:|:--:|:--:|------|
| ≥ 90% | 283 | 45.6% | 99.6 | auto-accept |
| 80–90% | 184 | 29.7% | 94.0 | adopt after a quick review |
| 70–80% | 82 | 13.2% | 84.1 | review before adopting |
| < 70% | 65 | 10.5% | 67.7 | near-tie, route to a human |

Accuracy rises monotonically with the reported confidence, so the value works as a routing signal:
adopt the high-confidence calls, review the rest, and let a human take the near-ties. It is a
routing aid, not a substitute for the decision-maker.

---

## Raw data

Question-level results are available on request during the preview phase.
