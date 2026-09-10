# IFEval Results *(archived)*

> **Archived.** Measured 2026-06-26 and retained for traceability. No longer published on the
> website. Superseded as our headline results by JudgeBench / ContextualJudgeBench (Decider) and
> ProfBench (Team).

**Framework**: lm-eval · 541 prompts · 25 verifiable instruction types
**Models**: `turingcorp/team-junior-v1`, `turingcorp/team-senior-v1`

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

## Findings

1. **Programmatic scoring** — IFEval uses exact-match and regex verification, not an LLM judge, so
   these results are reproducible and free of judge-model preference.
2. **Strict accuracy is consistently high** — 93.5%–94.8% strict accuracy means instructions were
   followed precisely, not approximately.

---

## Raw Data

Question-level model outputs: [result-package/](../../result-package/).
