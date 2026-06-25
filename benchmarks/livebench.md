# LiveBench Results

**Release**: 2026-06-25 (our run) · Official leaderboard uses 2026-01-08

## TuringCorp Junior v1 — Full Run

| Metric | Value |
|------|------|
| Questions | 682/682 completed |
| Failures / Timeouts | 0 / 0 |
| Total Tokens | 7,752,493 |
| Input / Output Split | 2.9M (38%) / 4.8M (62%) |
| Elapsed Time | 72 minutes |

## Category Scores

| Category | Score | Notes |
|------|:--:|------|
| Language | **93.5** | #1 on official leaderboard |
| Instruction Following | **87.4** | #1, +11.8 over next best |
| Reasoning | **84.5** | Above Gemini 3.5 Flash; below Claude 4.8 / GPT-5.5 |
| Math | **80.1** | Below Gemini 3 Flash (84.2) and GPT-5 Mini (82.2) |
| Data Analysis | **61.5** | Weakest category; tablejoin (46.4) and cta (52.0) |

## Task Breakdown

| Task | Score | Category |
|------|:--:|------|
| math_comp | 95.7 | Math |
| connections | 93.5 | Language |
| spatial | 88.0 | Reasoning |
| story_generation | 87.4 | IF |
| tablereformat | 86.0 | Data Analysis |
| zebra_puzzle | 81.0 | Reasoning |
| AMPS_Hard | 76.0 | Math |
| olympiad | 71.7 | Math |
| cta | 52.0 | Data Analysis |
| tablejoin | 46.4 | Data Analysis |

## Comparison with Frontier Models

*Data from LiveBench 2026-01-08 official leaderboard for comparability.*

| Model | Language | IF | Reasoning | Global |
|------|:--:|:--:|:--:|:--:|
| **TuringCorp Junior** | **93.5** | **87.4** | 84.5 | 79.8 |
| GPT-5.5 Thinking xHigh | 87.7 | 73.0 | 87.7 | **82.8** |
| Claude Fable 5 xHigh | 88.5 | 60.0 | 87.3 | 78.6 |
| Claude 4.8 Opus xHigh | 81.4 | 67.5 | **89.7** | 79.5 |
| Gemini 3.5 Flash High | 84.6 | 75.6 | 82.0 | 80.7 |
| Gemini 3 Pro Preview High | 84.6 | 65.9 | 77.4 | 76.0 |
| GPT-5 Mini High | 75.5 | 65.3 | 68.3 | 65.9 |

## Key Findings

1. **Language (93.5) and IF (87.4) are unprecedented** — no other model on the January 2026 leaderboard comes within 5 points in Language or 10 points in IF.

2. **Reasoning is competitive but not dominant** — sits above all non-xHigh models but below Claude 4.8/GPT-5.5 with maximum thinking effort.

3. **Data analysis is the primary weakness** — tablejoin (46.4) and cta (52.0) represent the largest gap to close. Senior and Principal tiers with multi-round review are expected to improve these scores.

4. **Model profile is unique**: Language >> Reasoning, the inverse of most frontier models. This is consistent with the multi-model orchestration architecture.

## Raw Data

Question-level results available at `https://api.turingcorp.net/benchmarks/latest.json`.

Question-level results available via the API endpoint.
