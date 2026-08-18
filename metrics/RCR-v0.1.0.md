# RCR v0.1.0 — Response Consistency Rate

**Code:** `RCR`  
**Version:** `0.1.0`  
**Category:** Consistency  
**Direction:** Higher values indicate greater stability  
**Unit:** Proportion

## Purpose

RCR measures the proportion of valid repetition comparisons that show no substantive variation or low variation relative to a frozen baseline observation from the same experimental condition.

RCR evaluates stability, not factual correctness, usefulness or citation quality.

## Formula

Let `b` be the frozen baseline observation and `C` the set of valid comparable non-baseline observations:

```text
S_i = 1 when variationLevel_i ∈ {none, low}
S_i = 0 when variationLevel_i ∈ {medium, high}

RCR = (Σ S_i) / |C|
```

The baseline is reported but excluded from the denominator. If `|C| = 0`, RCR is not estimable.

## Baseline rule

The baseline must be selected by a pre-specified rule before comparing outcomes. For the first pilot, the expected rule is the first eligible repetition. If it is technically invalid, the next eligible repetition may be used only according to the predefined replacement rule and with documented justification.

## Comparable condition

Baseline and comparison executions must share the frozen experimental condition, including prompt/version, system profile, relevant account/access settings, language/locale, retrieval mode, memory/custom-instruction state and evaluated-target definition.

## Variation classification

The initial codebook uses four levels:

- `none` — no substantive variation;
- `low` — minor differences without changing the target outcome or primary conclusion;
- `medium` — material variation while preserving the primary outcome;
- `high` — material change in target outcome, conclusion or other core dimension.

The final variation level should conservatively reflect the highest material severity observed across the assessed dimensions.

## First-pilot resolution

With five executions and one frozen baseline there are four comparisons, so RCR can take only:

```text
0.00, 0.25, 0.50, 0.75, 1.00
```

A single five-execution pilot must not be presented as a stable estimate of general AI-system behavior.

## Reporting

Report at minimum:

- baseline execution/observation;
- comparison set;
- individual variation levels;
- RCR numerator/denominator;
- experimental condition;
- exclusions/deviations;
- known limitations.

**Canonical scientific review:** [`gslhub/website`](https://github.com/gslhub/website/blob/main/docs/metrics/RCR_v0.1.0_REVIEW.md)
