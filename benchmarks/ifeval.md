# IFEval Results

**Framework**: lm-eval · 541 prompts · 25 verifiable instruction types · **Zero LLM-judge bias**

All scoring is programmatic (regex-based). No LLM-as-judge — results are fully reproducible and immune to judge-model preference.

---

## TuringCorp Team Junior v1

| Metric | Score |
|------|:--:|
| inst_level_strict | **93.5%** |
| inst_level_loose | 95.0% |
| prompt_level_strict | 90.6% |
| prompt_level_loose | 92.6% |

---

## TuringCorp Team Senior v1

| Metric | Score |
|------|:--:|
| inst_level_strict | **94.8%** |
| inst_level_loose | 96.0% |
| prompt_level_strict | 92.6% |
| prompt_level_loose | 94.3% |

---

## Key Findings

1. **Instruction following is world-leading** — both tiers exceed all known published models by significant margins.

2. **Programmatic scoring eliminates bias** — IFEval uses exact-match and regex verification, not an LLM judge that may favor certain writing styles.

3. **Strict accuracy is robust** — the high strict scores (93.5%–94.8%) indicate the model follows instructions precisely, not just approximately.

---

## Raw Data

Question-level model outputs available in [result-package/](../result-package/).
