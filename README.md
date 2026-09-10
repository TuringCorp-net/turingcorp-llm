# TuringCorp LLM

Benchmark results, raw data, methods and model cards for TuringCorp language models.

👉 **API**: `https://api.turingcorp.net/v1` (OpenAI-compatible) · Small-scale preview. [Apply for a license key →](docs/api.md#preview-license-key)
📊 **Results as text**: [api.turingcorp.net/benchmarks](https://api.turingcorp.net/benchmarks) — script-free, table-complete
🧾 **Data (JSON)**: [api.turingcorp.net/benchmarks/latest.json](https://api.turingcorp.net/benchmarks/latest.json)
🤖 **For AI agents**: [llms.txt](https://api.turingcorp.net/llms.txt) · [agent brief (Markdown)](https://api.turingcorp.net/index.md) · [OpenAPI 3.1](https://api.turingcorp.net/openapi.json) — requesting `Accept: text/markdown` from any page returns the Markdown version
📧 **Contact**: `iAsk@turingcorp.net`

> This repository is the **detailed** publication channel: it carries more than the website — full
> per-split results, raw model outputs for independent verification, methods and model cards.
> The website and this repository are published **together**: a change to model positioning, model
> descriptions or benchmark data is only complete when **both** are updated.

---

## Models

| Model ID | Product | Tier | Card | Status |
|------|------|:--:|------|:--:|
| `turingcorp/decider-junior-v1` | Decider | Junior | [card](model-cards/decider-junior.md) | Preview |
| `turingcorp/decider-senior-v1` | Decider | Senior | [card](model-cards/decider-senior.md) | Preview |
| `turingcorp/team-junior-v1.1` | Team | Junior | [card](model-cards/team-junior.md) | Preview |
| `turingcorp/team-senior-v1` | Team | Senior | [card](model-cards/team-senior.md) | Preview |
| `turingcorp/team-principal-v1` | Team | Principal | [card](model-cards/team-principal.md) | Preview |

**Decider** is an AI judge: given a task and two candidate answers, it picks the better one and
reports a calibrated confidence value with every judgment. **Team** is collaborative multi-path
analysis: independent reasoning paths cross-examine each other, and the final answer is delivered
as *content + reason* — the answer body together with the reasoning the model states for it.

Published benchmark results currently cover **Decider Junior** and **Team Junior v1.1**.

---

## Benchmark Results

Every number below is **self-run with the benchmark's official protocol** — these are not
third-party leaderboards. Where an official reference model appears, its rows come from the
official judging pipeline and are context, not a head-to-head comparison, unless stated otherwise.

### Decider — JudgeBench (2026-09-08)

Reference-model judging: given a question and two candidate responses, which is better?

| Model | Accuracy % |
|------|:--:|
| **Decider Junior** | **92.5** |
| DeepSeek V4 Flash (direct) | 92.7 |

> 614 / 620 pairs scored; 6 pairs rerun-excluded after repeated platform failures.
> Full details → [benchmarks/judgebench.md](benchmarks/judgebench.md)

### Decider — ContextualJudgeBench (2026-09-09)

The full official 2,000-pair set across all 8 splits. Consistent accuracy requires the same
correct pick in both presentation orders (random floor 25%).

| Model | Overall consistent accuracy % |
|------|:--:|
| **Decider Junior** | **67.1** |
| DeepSeek V4 Flash (direct) | 65.4 |

> Full per-split table, with official reference values from the paper → [benchmarks/cjb.md](benchmarks/cjb.md)

### Team Junior v1.1 — ProfBench (2026-09-10)

40 expert-level tasks (Physics PhD / Chemistry PhD / Finance MBA / Consulting MBA), scored
**criterion by criterion** against the official rubric, all three columns read by one
judging pipeline.

| Model | Score / 100 |
|------|:--:|
| **Team Junior v1.1** | **63.3** |
| DeepSeek V4 Flash (direct) | 57.4 |
| official o3 draft | 55.6 |

| Domain | tasks | Team | DeepSeek V4 Flash (direct) | official o3 draft |
|------|:--:|:--:|:--:|:--:|
| Chemistry PhD | 10 | **75.5** | 69.4 | 60.8 |
| Consulting MBA | 10 | **70.8** | 70.3 | 64.9 |
| Finance MBA | 10 | 54.6 | 48.2 | **57.5** |
| Physics PhD | 8 | **49.6** | 37.8 | 35.2 |

> 38 of 40 tasks scored: two tasks were excluded when a member model failed to produce an answer
> during the run — disclosed rather than imputed. **All three columns are reported on those same
> 38 tasks**, the set every model completed. Team leads the official o3 draft by **+7.7 points** and
> the direct baseline by **+4.9 points**, and the decision kernel picked the team draft **36 : 1**
> head-to-head without ever seeing the rubric.
> Full details → [benchmarks/profbench.md](benchmarks/profbench.md)

### Archived benchmarks

[LiveBench](benchmarks/archive/livebench.md) (2026-01-08) and [IFEval](benchmarks/archive/ifeval.md)
were published in June 2026 and are retained for traceability. They are **no longer shown on the
website**; see the archive pages for the aggregation caveat that applies to the LiveBench figures.

---

## Result Packages

Raw model outputs for independent verification:

| Package | Release | Contents |
|------|------|------|
| [turingcorp-team-junior-v1.1_profbench-20260910.zip](result-package/turingcorp-team-junior-v1.1_profbench-20260910.zip) | ProfBench 2026-09-10 | Team answers (content + reason), per-criterion judge ratings, decision-kernel picks, position-swap audit |
| [turingcorp-team-junior-v1_livebench-20260108.zip](result-package/turingcorp-team-junior-v1_livebench-20260108.zip) | LiveBench 2026-01-08 *(archived)* | Junior answers |
| [turingcorp-team-senior-v1_livebench-20260108.zip](result-package/turingcorp-team-senior-v1_livebench-20260108.zip) | LiveBench 2026-01-08 *(archived)* | Senior answers |
| [turingcorp-team-junior-v1_ifeval.zip](result-package/turingcorp-team-junior-v1_ifeval.zip) | IFEval *(archived)* | Junior outputs |
| [turingcorp-team-senior-v1_ifeval.zip](result-package/turingcorp-team-senior-v1_ifeval.zip) | IFEval *(archived)* | Senior outputs |

---

## Third-Party Leaderboards

We do not currently appear on any third-party leaderboard. Every number published here and on the
website is self-run with the benchmark's own official protocol, with coverage and exclusions
disclosed per benchmark.

---

## Repository

```
turingcorp-llm/
├── README.md
├── benchmarks/        ← Per-benchmark results and protocol notes
│   └── archive/       ← Retired benchmarks, kept for traceability
├── model-cards/       ← Model descriptions
├── docs/              ← API docs, methodology
└── result-package/    ← Raw results for independent verification
```

---

*Last updated: 2026-09-11.*
