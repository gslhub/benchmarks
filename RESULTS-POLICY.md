# GSLHub Benchmark Results Policy

This policy defines when a benchmark result may be presented as a **GSLHub empirical result**.

## 1. No synthetic-to-empirical promotion

Synthetic fixtures, deterministic calculator tests, development records and `TEST-` data are never research findings.

They may validate software or calculation logic, but they must remain clearly labelled as non-empirical.

## 2. Minimum release gate

A real benchmark result should not be published until all of the following are satisfied:

1. the benchmark and protocol versions are frozen;
2. the evaluated target and matching rules are frozen;
3. the planned executions are completed or every deviation/exclusion is documented;
4. raw response/interface evidence is preserved according to protocol;
5. observation and citation coding is complete;
6. required quality-control/reviewer decisions are complete;
7. metric eligibility and exclusion rules have been applied;
8. the calculation is reproducible from frozen inputs;
9. numerator/denominator or raw positions are independently checked;
10. known limitations and the exact experimental condition are documented;
11. any dataset/evidence intended for release has passed privacy, rights and licensing review;
12. the responsible researcher approves public release.

## 3. Required result metadata

A public result should identify:

- benchmark code and version;
- metric code and version;
- project/experiment identifier when public;
- prompt version or a stable prompt identifier;
- evaluated target definition;
- AI system and observable interface/model profile;
- relevant account/access/search conditions;
- language, locale, location/timezone where applicable;
- collection date/time window;
- sample counts;
- exclusions;
- result value and raw components;
- codebook/protocol versions;
- evidence/dataset availability;
- known limitations.

## 4. Small-sample language

Pilot-scale results must be described as **results under the tested condition**, not as permanent properties of a model, provider or generative-search system.

A five-execution pilot is primarily useful for validating procedure, coding and reproducibility. Broad generalization requires larger and repeated studies.

## 5. Corrections

A published result is not silently overwritten.

If a material error is found:

- preserve the original release/history;
- document the error;
- issue a corrected version or release;
- identify which inputs, rules or calculations changed;
- update citations/DOIs or release notes where applicable.

## 6. Separation of benchmark and dataset licenses

Benchmark specifications may be openly licensed while released datasets can require a different license or additional restrictions. Every dataset release must state its own provenance and license.
