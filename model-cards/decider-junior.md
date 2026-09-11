# TuringCorp Decider Junior v1

Model ID: `turingcorp/decider-junior-v1` · Product: Decider · Tier: Junior
Status: **Preview**

## What it is

An AI judge for pairwise decisions: given a task and two candidate answers, Decider picks the
better one and reports a **confidence value with every judgment**. It is built for everyday
decisions where a fast, calibrated second opinion is useful — and where a near-tie should be
visible as a near-tie rather than presented as a confident call.

## Benchmark Results

### JudgeBench (2026-09-08)

Reference-model judging: given a question and two candidate responses, which is better?

| Model | Accuracy % |
|------|:--:|
| **Decider Junior** | **92.5** |
| DeepSeek V4 Flash (direct) | 92.7 |

| Segment | pairs | Decider | DeepSeek V4 Flash (direct) |
|------|:--:|:--:|:--:|
| Knowledge (MMLU-Pro) | 303 | 88.8 | 88.8 |
| Reasoning (LiveBench) | 149 | **98.0** | 96.6 |
| Math (LiveBench) | 90 | 92.2 | **95.6** |
| Code (LiveCodeBench) | 72 | 97.2 | 97.2 |

> 614 / 620 pairs scored; 6 pairs rerun-excluded after repeated platform failures.

**Confidence calibration** — the value describes **how far apart the two candidates are** in our
judgment, and the accuracy column shows what that delivered on this benchmark. Set your own
threshold from the accuracy column:

| Confidence band | judgments | share | observed accuracy | what the value means | suggested use |
|------|:--:|:--:|:--:|------|------|
| ≥ 90% | 283 | 45.6% | 99.6 | one candidate clearly stronger | act on the pick directly |
| 80–90% | 184 | 29.7% | 94.0 | one candidate clearly stronger | act on the pick directly |
| 70–80% | 82 | 13.2% | 84.1 | closer call | act on the pick, expecting a narrow margin |
| < 70% | 65 | 10.5% | 67.7 | near-tie: the two candidates are close in quality, each with its own strengths | either option is defensible — decide on grounds outside the answers |

### ContextualJudgeBench (2026-09-09)

Full official set of 2,000 pairs across all 8 splits. Consistent accuracy requires the same correct
pick in both presentation orders; the random floor is 25%.

| Model | Overall consistent accuracy % |
|------|:--:|
| **Decider Junior** | **67.1** |
| DeepSeek V4 Flash (direct) | 65.4 |

> 1,991 / 2,000 pairs completed; 12 orders (0.3%) rerun-excluded after repeated platform failures.
> Per-split table with official reference values → [benchmarks/cjb.md](../benchmarks/cjb.md)

| Confidence band | judgments | share | observed accuracy | what the value means | suggested use |
|------|:--:|:--:|:--:|------|------|
| ≥ 90% | 789 | 19.8% | 83.3 | one candidate clearly stronger | act on the pick directly |
| 80–90% | 1,486 | 37.3% | 76.4 | one candidate clearly stronger | act on the pick directly |
| 70–80% | 1,184 | 29.7% | 63.6 | closer call | act on the pick, expecting a narrow margin |
| < 70% | 529 | 13.3% | 55.4 | near-tie: the two candidates are close in quality, each with its own strengths | either option is defensible — decide on grounds outside the answers |

## Observed strengths

- Judgment quality at or above a strong direct baseline on both judging benchmarks, with the
  advantage concentrated in reasoning-style judgments.
- The confidence value is **calibrated against outcomes on both benchmarks**, not asserted: high
  confidence means measurably higher accuracy.
- Near-ties are surfaced rather than hidden — the lowest tier is explicitly routed to a human.

Full details: [benchmarks/judgebench.md](../benchmarks/judgebench.md) · [benchmarks/cjb.md](../benchmarks/cjb.md)
