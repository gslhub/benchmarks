<div align="center">

# GSLHub Benchmarks

### Reproducible evaluation for Generative Search, GEO and AI visibility

**Benchmark specifications, metric definitions, synthetic validation fixtures and publication rules for GSLHub**

**English** · [Español](./README.es.md)

[Website](https://gslhub.com) · [Research methodology](https://github.com/gslhub/research) · [Metrics software](https://github.com/gslhub/software/tree/main/packages/metrics-core) · [Platform](https://github.com/gslhub/website)

</div>

---

## Purpose

`gslhub/benchmarks` is the public benchmark layer of **GSLHub — Generative Search Lab Hub**.

The repository defines reproducible evaluation frameworks for studying whether and how generative systems include, cite and position evaluated targets, and how stable those outcomes remain across controlled repetitions.

It intentionally separates **benchmark specification** from **research results**. A benchmark may be public before any real experimental dataset or doctoral finding is released.

## Current benchmark

### GSL-BENCH-GEO-01

The first benchmark family evaluates controlled Generative Search / GEO visibility using four governed metrics:

| Code | Metric | Primary question |
|---|---|---|
| **AIR** | Answer Inclusion Rate | In what proportion of eligible answers is the target visibly included? |
| **CR** | Citation Rate | In what proportion of eligible executions is the target explicitly cited? |
| **MCP** | Mean Citation Position | When cited, where does the first valid target citation appear? |
| **RCR** | Response Consistency Rate | How stable are repeated responses relative to a frozen baseline? |

The canonical research protocol and observation/citation codebook live in [`gslhub/research`](https://github.com/gslhub/research).

## Reference implementation

The first independent implementation of these four metric specifications is [`@gslhub/metrics-core`](https://github.com/gslhub/software/tree/main/packages/metrics-core) in [`gslhub/software`](https://github.com/gslhub/software).

The package is intentionally independent of the GSLHub CMS/database layer and exposes deterministic calculation outputs, eligibility exclusions, numerator/denominator data and SHA-256 input/output checksums. Its automated test suite reproduces the synthetic fixture in this repository.

The **benchmark specification remains normative**. Software implementations are versioned separately so they can be validated against the specification they claim to implement.

## Repository structure

```text
benchmarks/
├── benchmarks/
│   └── GSL-BENCH-GEO-01/
│       ├── README.md
│       └── benchmark.yaml
├── metrics/
│   ├── AIR-v0.1.0.md
│   ├── CR-v0.1.0.md
│   ├── MCP-v0.1.0.md
│   └── RCR-v0.1.0.md
├── fixtures/
│   └── synthetic-validation.json
├── RESULTS-POLICY.md
├── CITATION.cff
└── README.md
```

## Benchmark principles

A GSLHub benchmark must be:

- **versioned** — material methodological changes create a new version;
- **auditable** — results remain traceable to preserved evidence and coded observations;
- **condition-aware** — prompt, AI-system profile, interface, locale and other relevant conditions are frozen or reported;
- **explicit about exclusions** — failed or non-comparable executions are documented, not silently removed;
- **separate from synthetic validation** — software fixtures are never presented as scientific findings;
- **reproducible** — formulas, numerator/denominator rules and missing-data handling are documented.

## Synthetic validation fixture

The repository contains a deliberately synthetic fixture used only to validate deterministic calculations:

```text
AIR = 3 / 4 = 0.75
CR  = 2 / 4 = 0.50
MCP = 6 / 3 = 2.00
RCR = 3 / 4 = 0.75
```

These numbers are **not empirical findings**, do not describe any AI system and must never be cited as research results.

The same expected values are asserted by the public `@gslhub/metrics-core` test suite, providing a cross-repository specification-to-implementation check.

## Results

Real benchmark results are published only after:

1. protocol freeze;
2. controlled execution;
3. artifact preservation;
4. coding and review;
5. eligibility/exclusion resolution;
6. deterministic metric validation;
7. research approval for public release.

See [`RESULTS-POLICY.md`](RESULTS-POLICY.md).

## Licensing

Original benchmark specifications and documentation are intended for open scientific reuse under **Creative Commons Attribution 4.0 International (CC BY 4.0)** unless a file states otherwise.

Datasets and third-party material are licensed separately according to provenance and rights.

## Citation

Citation metadata is provided in [`CITATION.cff`](CITATION.cff). When using a specific benchmark release, cite the benchmark identifier and version in addition to this repository.

---

© 2026 GSLHub / Eduardo Yauri
