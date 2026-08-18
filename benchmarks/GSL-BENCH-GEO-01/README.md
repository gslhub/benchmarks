# GSL-BENCH-GEO-01

**Name:** GSLHub Generative Search / GEO Visibility Benchmark  
**Benchmark code:** `GSL-BENCH-GEO-01`  
**Specification version:** `0.1.0`  
**Status:** Pilot / methodological validation  
**Research protocol:** [`gslhub/research`](https://github.com/gslhub/research/tree/main/protocols/GSL-GEO-BENCH-01)  
**Codebook:** [`gslhub/research`](https://github.com/gslhub/research/blob/main/codebooks/OBSERVATIONS-CITATIONS-v0.1.0-ES.md)

## Objective

Evaluate the visibility of a predefined target in generative-search experiences under controlled, repeated conditions.

The benchmark distinguishes four dimensions that must not be conflated:

1. **answer inclusion** — target appears visibly in the generated answer body;
2. **citation occurrence** — target appears as an explicit source/reference;
3. **citation position** — first valid target citation position on the frozen primary citation surface;
4. **response consistency** — stability of repeated responses relative to a pre-specified baseline.

## Pilot design

The initial protocol uses five controlled independent repetitions of one frozen experimental condition:

```text
1 baseline execution
4 comparison executions
```

This pilot validates the benchmark workflow. A five-execution round is not sufficient to claim general or permanent behavior of an AI system.

## Required frozen condition

Before a benchmark round begins, document and freeze where applicable:

- research project and experiment;
- benchmark/specification version;
- exact prompt and prompt version;
- evaluated target and matching rules;
- AI system/provider and visible model/interface profile;
- account/access tier;
- web-search or retrieval mode;
- language and locale;
- declared location and timezone;
- memory/custom-instruction state;
- repetition count and ordering;
- primary citation surface for MCP;
- inclusion/exclusion rules;
- codebook and metric-definition versions.

## Evidence requirements

Each execution should preserve enough evidence to reconstruct what was observed. The canonical GSLHub protocol requires textual response preservation, visual interface capture and execution-context metadata, with durable artifact storage and integrity checks where applicable.

## Metrics

- [`AIR v0.1.0`](../../metrics/AIR-v0.1.0.md)
- [`CR v0.1.0`](../../metrics/CR-v0.1.0.md)
- [`MCP v0.1.0`](../../metrics/MCP-v0.1.0.md)
- [`RCR v0.1.0`](../../metrics/RCR-v0.1.0.md)

## Reporting minimum

Every released benchmark result should report at minimum:

- benchmark and metric version;
- evaluated target definition;
- prompt/system condition;
- collection period;
- `N_planned`, `N_completed`, `N_eligible` and `N_excluded`;
- numerator/denominator or raw positions, depending on metric;
- result value and rounding rule;
- exclusions and reasons;
- baseline for RCR;
- primary citation surface for MCP;
- known limitations;
- dataset/evidence release status.

## Result status

No real doctoral result is included in this repository at initialization. The only bundled values are synthetic calculator-validation fixtures and are clearly labelled as non-empirical.
