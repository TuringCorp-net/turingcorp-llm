# IFEval Results

**Framework**: lm-eval · 541 prompts · 25 verifiable instruction types · **Zero LLM-judge bias**

All scoring is programmatic (regex-based). No LLM-as-judge — results are fully reproducible and immune to judge-model preference.

---

## TuringCorp Team Junior v1

| Metric | Score | vs GPT-4o | vs Claude Opus 4 |
|------|:--:|:--:|:--:|
| inst_level_strict | **93.5%** | +9.8 | +6.2 |
| inst_level_loose | **95.0%** | +6.6 | — |
| prompt_level_strict | **90.6%** | +9.8 | — |
| prompt_level_loose | **92.6%** | +9.6 | — |

---

## TuringCorp Team Senior v1

| Metric | Score | vs GPT-4o | vs Claude Opus 4 |
|------|:--:|:--:|:--:|
| inst_level_strict | **94.8%** | +11.1 | +7.5 |
| inst_level_loose | **96.0%** | +7.6 | — |
| prompt_level_strict | **92.6%** | +11.8 | — |
| prompt_level_loose | **94.3%** | +11.3 | — |

---

## Comparison with Published Models

| Model | inst_strict | inst_loose |
|------|:--:|:--:|
| **TuringCorp Senior** | **94.8%** | **96.0%** |
| **TuringCorp Junior** | 93.5% | 95.0% |
| GPT-4o (published) | 83.7% | 88.4% |
| Claude Opus 4 (published) | 87.3% | — |
| Llama-3.1 405B (published) | 85.6% | — |

---

## Key Findings

1. **Instruction following is world-leading** — both tiers exceed all published models by 6–11 points.

2. **Programmatic scoring eliminates bias** — IFEval uses exact-match and regex verification, not an LLM judge that may favor certain writing styles.

3. **Strict accuracy is robust** — the high strict scores (93.5%–94.8%) indicate the model follows instructions precisely, not just approximately.

---

## Raw Data

Question-level model outputs available in [result-package/](../result-package/).
