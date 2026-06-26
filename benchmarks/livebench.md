# LiveBench Results

**Release**: 2026-01-08 (public leaderboard release) · 682 questions · 6 categories

---

## TuringCorp Team Junior v1

| Category | Score | vs GPT-5.5 | vs Claude 4.8 | vs Gemini 3.5 Flash |
|------|:--:|:--:|:--:|:--:|
| Language | **93.5** | +5.8 | +12.1 | +8.9 |
| Instruction Following | **87.4** | +14.4 | +19.9 | +11.8 |
| Reasoning | 84.5 | -3.2 | -5.2 | +2.5 |
| Math | 75.5 | — | — | — |
| Data Analysis | 61.5 | — | — | — |
| **Overall** | **80.5** | — | — | — |

Per-task: [connections: 93.5] [tablereformat: 86.0] [spatial: 88.0] [paraphrase: 87.4] [math_comp: 95.7] [zebra_puzzle: 81.0] [olympiad: 71.7] [AMPS_Hard: 59.0] [cta: 52.0] [tablejoin: 46.4]

---

## TuringCorp Team Senior v1

| Category | Score | vs GPT-5.5 | vs Claude 4.8 | vs Gemini 3.5 Flash |
|------|:--:|:--:|:--:|:--:|
| Language | **94.2** | +6.5 | +12.8 | +9.6 |
| Instruction Following | **88.8** | +15.8 | +21.3 | +13.2 |
| Reasoning | **90.8** | +3.1 | +1.1 | +8.8 |
| Math | 80.4 | — | — | — |
| Data Analysis | 65.8 | — | — | — |
| **Overall** | **84.0** | — | — | — |

Per-task: [connections: 94.2] [tablereformat: 86.0] [spatial: 92.0] [paraphrase: 88.8] [math_comp: 95.7] [zebra_puzzle: 89.5] [olympiad: 73.7] [AMPS_Hard: 72.0] [cta: 60.0] [tablejoin: 51.3]

---

## Key Findings

1. **Language and IF are world-leading** — both Junior and Senior exceed all models on the January 2026 leaderboard by significant margins.

2. **Reasoning scales with tier** — Junior (84.5) → Senior (90.8), surpassing GPT-5.5 (87.7) and competitive with Claude 4.8 Opus (89.7).

3. **Data Analysis is the primary weakness** — tablejoin and cta tasks represent the largest gap to close.

4. **Unique model profile**: Language >> Reasoning, the inverse of most frontier models. Consistent with the multi-model orchestration architecture optimized for planning, verification, and structured output.

---

## Comparison with Frontier Models (2026-01-08 Leaderboard)

| Model | Language | IF | Reasoning | Global |
|------|:--:|:--:|:--:|:--:|
| **TuringCorp Senior** | **94.2** | **88.8** | **90.8** | **84.0** |
| **TuringCorp Junior** | 93.5 | 87.4 | 84.5 | 80.5 |
| GPT-5.5 Thinking xHigh | 87.7 | 73.0 | 87.7 | 82.8 |
| Claude 4.8 Opus xHigh | 81.4 | 67.5 | 89.7 | 79.5 |
| Claude Fable 5 xHigh | 88.5 | 60.0 | 87.3 | 78.6 |
| Gemini 3.5 Flash High | 84.6 | 75.6 | 82.0 | 80.7 |

---

## Raw Data

Question-level model outputs available in [result-package/](../result-package/). Full score breakdown at `https://api.turingcorp.net/benchmarks/latest.json`.
