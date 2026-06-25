# Methodology

TuringCorp models use a proprietary multi-model orchestration system. Each inference request is processed through a collaborative pipeline designed to produce higher-quality outputs than single-model approaches.

## Performance Characteristics

- **Output quality** benefits from the collaborative architecture
- **Latency** is higher than single-model inference due to the multi-step process
- **Quality scales** with model tier (Junior → Senior → Principal)

## Evaluation

All benchmark results are produced using the same API endpoint available to customers, with standard open-source evaluation frameworks (LiveBench, lm-eval) without modification.

To reproduce: obtain API access and use the LiveBench evaluation framework with endpoint `https://api.turingcorp.net/v1`.
