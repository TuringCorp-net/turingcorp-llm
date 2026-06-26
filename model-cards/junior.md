# TuringCorp Team Junior v1

Status: **Preview**

## Benchmark Results

### LiveBench (Release 2026-01-08)

| Category | Score |
|------|:--:|
| Language | **93.5** |
| Instruction Following | **87.4** |
| Reasoning | 84.5 |
| Math | 75.5 |
| Data Analysis | 61.5 |
| **Overall** | **80.5** |

### IFEval

| Metric | Score |
|------|:--:|
| inst_level_strict | **93.5%** |
| inst_level_loose | 95.0% |
| prompt_level_strict | 90.6% |
| prompt_level_loose | 92.6% |

Full results: [benchmarks/livebench.md](../benchmarks/livebench.md) · [benchmarks/ifeval.md](../benchmarks/ifeval.md)

## Observed Strengths

- Language understanding and instruction following at or above frontier-model level
- Strong reasoning relative to non-thinking models
- Zero failures across all evaluated benchmarks

## Observed Limitations

- Data analysis tasks, particularly table-join operations
- Mathematics below specialized reasoning models
- Coding not yet evaluated
