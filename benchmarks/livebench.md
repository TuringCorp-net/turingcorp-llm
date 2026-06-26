# LiveBench Results

**Release**: 2026-01-08 (public leaderboard release) · 682 questions · 6 categories

---

## TuringCorp Team Junior v1

| Category | Score |
|------|:--:|
| Language | **93.5** |
| Instruction Following | **87.4** |
| Reasoning | 84.5 |
| Math | 75.5 |
| Data Analysis | 61.5 |
| **Overall** | **80.5** |

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
| **Overall** | **84.0** |

Per-task: [connections: 94.2] [tablereformat: 86.0] [spatial: 92.0] [paraphrase: 88.8] [math_comp: 95.7] [zebra_puzzle: 89.5] [olympiad: 73.7] [AMPS_Hard: 72.0] [cta: 60.0] [tablejoin: 51.3]

---

## Key Findings

1. **Language and IF are world-leading** — both Junior and Senior exceed all models on the January 2026 leaderboard by significant margins.

2. **Reasoning scales with tier** — Junior (84.5) → Senior (90.8), a +6.3 improvement from the additional cross-review round.

3. **Data Analysis is the primary weakness** — tablejoin and cta tasks represent the largest gap to close.

4. **Unique model profile**: Language >> Reasoning, the inverse of most frontier models. Consistent with the multi-model orchestration architecture optimized for planning, verification, and structured output.

---

## Raw Data

Question-level model outputs available in [result-package/](../result-package/). Full score breakdown at `https://api.turingcorp.net/benchmarks/latest.json`.
