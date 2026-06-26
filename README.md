# TuringCorp LLM

Benchmark results and documentation for TuringCorp language models.

👉 **API**: `https://api.turingcorp.net/v1` (OpenAI-compatible) · Small-scale preview. [Apply for a license key →](docs/api.md#preview-license-key)
📧 **Contact**: `iAsk@turingcorp.net`

---

## Models

| Tier | Model ID | Status |
|------|------|:--:|
| **Junior** | `turingcorp/team-junior-v1` | Preview |
| **Senior** | `turingcorp/team-senior-v1` | Preview |
| **Principal** | `turingcorp/team-principal-v1` | Preview |

---

## Benchmark Results

### LiveBench (Release 2026-01-08 · Public Leaderboard)

| Tier | Overall | Language | IF | Reasoning | Math | Data |
|------|:--:|:--:|:--:|:--:|:--:|:--:|
| **Junior** | 80.5 | **93.5** | 87.4 | 84.5 | 75.5 | 61.5 |
| **Senior** | 84.0 | **94.2** | **88.8** | **90.8** | 80.4 | 65.8 |

> 682/682 questions per model. Zero failures. Full details → [benchmarks/livebench.md](benchmarks/livebench.md)

### IFEval (lm-eval · Programmatic Scoring)

| Tier | inst_strict | inst_loose | prompt_strict | prompt_loose |
|------|:--:|:--:|:--:|:--:|
| **Junior** | 93.5% | 95.0% | 90.6% | 92.6% |
| **Senior** | **94.8%** | **96.0%** | **92.6%** | **94.3%** |

> 541 prompts. Zero LLM-judge bias. Full details → [benchmarks/ifeval.md](benchmarks/ifeval.md)

---

## Result Packages

Raw model outputs + full scores for independent verification:

| Package | Release | Models |
|------|------|------|
| [turingcorp-team-junior-v1_livebench-20260108.zip](result-package/turingcorp-team-junior-v1_livebench-20260108.zip) | LiveBench 2026-01-08 | Junior |
| [turingcorp-team-senior-v1_livebench-20260108.zip](result-package/turingcorp-team-senior-v1_livebench-20260108.zip) | LiveBench 2026-01-08 | Senior |
| [turingcorp-team-junior-v1_ifeval.zip](result-package/turingcorp-team-junior-v1_ifeval.zip) | IFEval (lm-eval) | Junior |
| [turingcorp-team-senior-v1_ifeval.zip](result-package/turingcorp-team-senior-v1_ifeval.zip) | IFEval (lm-eval) | Senior |

---

## Repository

```
turingcorp-llm/
├── README.md
├── benchmarks/        ← Per-benchmark results
├── model-cards/       ← Model descriptions
├── docs/              ← API docs, methodology
└── result-package/    ← Raw results for independent verification
```
