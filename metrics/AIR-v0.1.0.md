# AIR v0.1.0 — Answer Inclusion Rate

**Code:** `AIR`  
**Version:** `0.1.0`  
**Category:** Visibility  
**Direction:** Higher is better  
**Unit:** Proportion

## Purpose

AIR measures the proportion of eligible controlled executions in which a predefined evaluated target is visibly included in the generated answer body.

AIR measures answer-level presence only. It must remain separate from citation occurrence, citation quality, recommendation strength, prominence, factual use and sentiment.

## Formula

Let `E` be the frozen set of eligible executions and `M_i` the binary inclusion outcome:

```text
M_i = 1 when the evaluated target is visibly included in the generated answer body
M_i = 0 when the evaluated target is not visibly included

AIR = (Σ M_i) / |E|
```

Valid range: `[0,1]`.

Report the raw numerator and denominator together with the proportion. Recommended precision: four decimal places.

## Inclusion rule

The evaluated target and valid aliases/variants must be frozen before coding.

Count only unambiguous target presence in the answer body according to the frozen codebook. Do not convert a source-only appearance in a citation panel or reference list into AIR inclusion.

## Denominator

An eligible execution remains in the denominator when the target is absent; that is a valid zero. Technical failures may be excluded only under predefined rules and must be reported separately.

## Reporting

Report at minimum:

- target definition;
- `N_planned`, `N_completed`, `N_eligible`, `N_included`, `N_excluded`;
- AIR numerator/denominator;
- prompt/system condition;
- collection period;
- exclusions and limitations.

## Interpretation limits

AIR does not establish that the target was cited, recommended, used as evidence, presented favourably or likely to appear under another prompt/system/date/location.

**Canonical scientific review:** [`gslhub/website`](https://github.com/gslhub/website/blob/main/docs/metrics/AIR_v0.1.0_REVIEW.md)
