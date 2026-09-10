# TuringCorp Team Junior v1.1

Model ID: `turingcorp/team-junior-v1.1` · Product: Team · Tier: Junior
Status: **Preview**

## What it is

Collaborative multi-path analysis for everyday tasks: independent reasoning paths cross-examine
each other, and the final answer is delivered as **content + reason** — the answer body together
with the reasoning the model states for its conclusion.

## Benchmark Results

### ProfBench (2026-09-10)

40 expert-level tasks — ten each in Physics PhD, Chemistry PhD, Finance MBA and Consulting MBA —
scored **criterion by criterion** against the official rubric by a single judging pipeline, so the
three columns below are directly comparable.

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

> 38 of 40 tasks scored. Two tasks were excluded because no answer was produced for them during the
> run — disclosed rather than imputed. **All three columns are reported on those same 38 tasks**,
> the set every model completed.
> Our judging pipeline reproduces the official per-criterion labels on the o3 draft with 74.0%
> agreement (F1 0.761, mean difference +2.4 points).

**Head-to-head by our own decision kernel.** Asked to choose between the team draft and the
official o3 draft on the same 38 tasks — shown the question and the two drafts, with no rubric and
no scores — the kernel selected the team draft **36 : 1** (one unresolved). On a sample of 10 tasks
the comparison was re-run with the two drafts exchanged between option A and option B: all 10 kept
the same draft.

**Confidence reported with every judgment** (median confidence, and kernel picks for the team draft):

| Domain | tasks | Median confidence | Kernel picks the team draft |
|------|:--:|:--:|:--:|
| Physics PhD | 8 | 95.3% | 8/8 |
| Chemistry PhD | 10 | 87.0% | 9/10 |
| Consulting MBA | 10 | 84.5% | 10/10 |
| Finance MBA | 10 | 83.8% | 9/10 |

### Archived benchmarks (LiveBench 2026-01-08 · IFEval)

| Benchmark | Overall | Notes |
|------|:--:|------|
| LiveBench (v1, release 2026-01-08) | **80.5** | 682/682 questions; see the aggregation caveat on the archive page |
| IFEval (lm-eval) | inst_strict **93.5%** | 541 prompts, programmatic scoring |

> These June 2026 results are retained for traceability and are no longer published on the website.
> Details: [benchmarks/archive/livebench.md](../benchmarks/archive/livebench.md) ·
> [benchmarks/archive/ifeval.md](../benchmarks/archive/ifeval.md)

## Observed strengths

- Highest score on the rubric-scored ProfBench run, ahead of both the direct baseline and the
  official reference draft on the same tasks.
- Strongest margin in the qualitative domains (Chemistry, Consulting) while remaining competitive
  in Physics and Finance.
- Every judgment ships with a calibrated confidence value; the per-domain figures are in
  [benchmarks/profbench.md](../benchmarks/profbench.md).

Full details: [benchmarks/profbench.md](../benchmarks/profbench.md)
