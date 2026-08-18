# MCP v0.1.0 — Mean Citation Position

**Code:** `MCP`  
**Version:** `0.1.0`  
**Category:** Position  
**Direction:** Lower values indicate earlier appearance  
**Unit:** Ordinal position

## Purpose

MCP measures the average visible position of the **first valid citation of the evaluated target** across eligible executions in which the target was cited and its position was observable.

MCP is conditional on citation and should be interpreted together with CR.

## Formula

Let `C_pos` be the eligible cited executions with an observable target-citation position and let `P_i` be the one-based position of the first valid target citation:

```text
P_i = min(position of every accepted target citation in the frozen primary surface)

MCP = (Σ P_i) / |C_pos|
```

If `|C_pos| = 0`, MCP is **not estimable**; it must never be reported as zero.

Recommended precision: two decimal places.

## Primary citation surface

Before collection begins, define one comparable primary citation surface, such as inline citations, end references, source cards or a sources panel.

Positions from incomparable interfaces or citation surfaces must not be combined into one MCP value.

## Multiple citations

Each execution contributes only its earliest accepted target-citation position. Uncited executions do not receive an artificial position or penalty rank.

## Reporting

Report at minimum:

- total eligible executions;
- executions citing the target;
- cited executions with observable position;
- individual first positions and their sum;
- primary citation surface;
- MCP value;
- CR from the same analytical sample;
- exclusions and interface limitations.

## Interpretation limits

MCP does not measure citation frequency, citation quality, claim support, authority or general visibility. An early MCP combined with a low CR must not be interpreted as strong overall visibility.

**Canonical scientific review:** [`gslhub/website`](https://github.com/gslhub/website/blob/main/docs/metrics/MCP_v0.1.0_REVIEW.md)
