# CR v0.1.0 — Citation Rate

**Code:** `CR`  
**Version:** `0.1.0`  
**Category:** Citation  
**Direction:** Higher is better  
**Unit:** Proportion

## Purpose

CR measures the proportion of eligible controlled executions in which the evaluated target is explicitly presented by the system as a source, reference or linked destination.

It measures citation occurrence, not citation quality, authority, correctness, claim support, sentiment or prominence.

## Formula

Let `E` be the frozen set of eligible executions and `C_i` the binary citation outcome:

```text
C_i = 1 when at least one accepted citation matches the evaluated target
C_i = 0 when no accepted citation matches the evaluated target

CR = (Σ C_i) / |E|
```

Each execution contributes at most one unit to the numerator, even when the target is cited multiple times.

Valid range: `[0,1]`. Report numerator and denominator with the proportion.

## Citation rule

A valid citation must be visibly presented as attribution, a source or a reference under the frozen codebook. A plain target mention in the answer body is not a citation.

Target identity and normalization rules must be frozen before coding. Ambiguous matches are not counted until adjudicated.

## Denominator

An eligible execution with no target citation remains in the denominator with a zero. An execution showing no citations is also a valid zero when the absence can be verified from preserved evidence.

## Reporting

Report at minimum:

- target definition and matching rules;
- `N_planned`, `N_completed`, `N_eligible`, `N_cited_executions`, `N_uncited_executions`, `N_excluded`;
- CR numerator/denominator;
- collection condition and period;
- exclusions and limitations.

## Interpretation limits

CR does not establish that a citation correctly supports a claim, is primary or authoritative, is prominent, or influenced generation.

**Canonical scientific review:** [`gslhub/website`](https://github.com/gslhub/website/blob/main/docs/metrics/CR_v0.1.0_REVIEW.md)
