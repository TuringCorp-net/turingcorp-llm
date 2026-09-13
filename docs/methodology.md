# Methodology

TuringCorp models run on a proprietary multi-model orchestration system: a single inference request
is processed through a collaborative pipeline rather than a single forward pass.

## Delivery contract

**Team** returns *content + reason*: the answer body together with the reasoning the model states
for its own conclusion. This is part of the product, not a debugging artefact, and it is what gets
scored — ProfBench evaluates every response criterion by criterion, derivations and intermediate
results included, so an answer that shows its work is scored on the work itself.

**Decider** returns a pick plus a **confidence value** with every judgment. The value describes how
far apart the two candidates are in its judgment — a high value means one of them is clearly
stronger, a low value means the two are evenly matched. That makes
it directly usable: a high value means you can act on the pick, a low value means either choice is
fine. It is a reading of how decisive the comparison was, not a verdict on either
candidate taken on its own. Thresholds are ours to publish, yours to set — see the per-benchmark
accuracy tables in [`benchmarks/`](../benchmarks/).

## Evaluation principles

1. **Official protocols, unmodified.** Each benchmark is run with its own official prompt,
   judging procedure and aggregation, whichever way the numbers fall out.
2. **Self-run, disclosed as such.** We are not a third-party leaderboard. Reference models are
   measured on the same judged set with the same pipeline, so model-vs-model columns are directly
   comparable; rows produced by an official judging pipeline are labelled as context only.
3. **Disclose coverage and exclusions.** Failures are excluded from scoring and reported
   (rerun-excluded after repeated platform failures) — never imputed, never silently dropped.
4. **Calibrate the judge.** Where our pipeline scores the answers, its agreement with the official
   labels is measured and published (for ProfBench: 74.0% agreement, F1 0.761, mean difference
   +2.4 points on the official o3 draft).
5. **Pre-empt the obvious artefacts.** A preference must survive a control before it is published:
   the ProfBench head-to-head was re-run with the two candidate answers exchanged between option A
   and option B on every task where a pick had been made (36 of 37 kept the same draft; the single
   change fell on a task the kernel had itself flagged as a near-tie), and judgments come from a panel
   of independent models rather than one model grading its own output.
6. **Raw data for verification.** Where a result package is published, it ships the underlying
   model outputs and per-criterion judgments so the scores can be re-derived independently. Packages
   are published for the current suite; retired benchmarks keep their summary numbers only.

## Reproducing

The API endpoint is the same one customers use:

```
https://api.turingcorp.net/v1
```

Obtain preview access (see [api.md](api.md)), then run the benchmark with its own official
framework and point it at this endpoint. Benchmark-specific protocol notes — dataset, judging
procedure, coverage, exclusions — are in [`benchmarks/`](../benchmarks/).

## Notes

- Latency is higher than a single-model call.
- Tier describes depth (Junior → Senior → Principal), not a different task.
