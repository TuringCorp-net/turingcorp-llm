# LiveBench Results *(archived)*

> **Archived.** Measured 2026-06-26 against the LiveBench release of 2026-01-08 and retained for
> traceability. These figures are **no longer published on the website**, and they are **not
> directly comparable to official LiveBench leaderboard numbers** — see the aggregation note below.

**Release**: 2026-01-08 (public leaderboard release) · 682 questions · 6 categories
**Models**: `turingcorp/team-junior-v1`, `turingcorp/team-senior-v1`

---

## Aggregation note

The overall and category figures below were aggregated **per question** (question-mean). The
official LiveBench leaderboard aggregates **per task** (task-mean). The two conventions do not agree
when tasks have unequal question counts: re-scoring our own answers both ways differs by roughly
**4.7 points on math** and ~6 points overall. Treat these numbers as our own aggregation of our own
answers, not as leaderboard-equivalent scores.

---

## TuringCorp Team Junior v1

| Category | Score |
|------|:--:|
| Language | **93.5** |
| Instruction Following | **87.4** |
| Reasoning | 84.5 |
| Math | 75.5 |
| Data Analysis | 61.5 |
| **Overall (question-mean)** | **80.5** |

Per-task: [connections: 93.5] [tablereformat: 86.0] [spatial: 88.0] [paraphrase: 87.4] [math_comp: 95.7] [zebra_puzzle: 81.0] [olympiad: 71.7] [AMPS_Hard: 59.0] [cta: 52.0] [tablejoin: 46.4]

---

## TuringCorp Team Senior v1

| Category | Score |
|------|:--:|
| Language | **94.2** |
| Instruction Following | **88.8** |
| Reasoning | **90.8** |
| Math | 80.4 |
| Data Analysis | 65.8 |
| **Overall (question-mean)** | **84.0** |

Per-task: [connections: 94.2] [tablereformat: 86.0] [spatial: 92.0] [paraphrase: 88.8] [math_comp: 95.7] [zebra_puzzle: 89.5] [olympiad: 73.7] [AMPS_Hard: 72.0] [cta: 60.0] [tablejoin: 51.3]

---

## Findings

1. **Reasoning scales with tier** — Junior (84.5) → Senior (90.8), +6.3, from the multi-round
   cross-review architecture.
2. **682/682 questions completed per model**, with no excluded questions.
3. Language and instruction following are the strongest categories for both tiers under this
   aggregation; see the caveat above before comparing to any leaderboard.

---

## Raw Data

Answers for both models: [result-package/](../../result-package/).
