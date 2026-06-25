# TuringCorp LLM

Benchmark results and documentation for TuringCorp language models.

👉 **API**: `https://api.turingcorp.net/v1` (OpenAI-compatible)
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

| Benchmark | Junior | Senior | Principal |
|------|:--:|:--:|:--:|
| [LiveBench](benchmarks/livebench.md) | **79.8** | — | — |
| AIME | running | — | — |
| MMLU-Pro | — | — | — |
| GPQA | — | — | — |

---

## Repository

```
turingcorp-llm/
├── README.md
├── benchmarks/        ← Per-benchmark results
├── model-cards/       ← Model descriptions
└── docs/              ← API docs, methodology
```
