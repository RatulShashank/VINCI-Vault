---
title: BOS Scoring System
type: method
tags: [BOS, scoring, displacement, body-ratio, volume, calibration]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Purpose

Quantify the quality of a Break of Structure event to distinguish genuine structural breaks (that hold) from false breaks (that reverse). Replaces discretionary "displacement quality" judgment.

## Score components

**Displacement score** (0 to 1, weighted sum):
```
disp_score = body_ratio × 0.35 + range_score × 0.35 + vol_score × 0.30
```
- `body_ratio`: candle body / (high − low), already 0–1
- `range_score`: (high − low) / ATR(14), capped at 3×ATR → normalized to 0–1
- `vol_score`: volume / vol_MA(20), capped at 3× → normalized to 0–1

**Close type ceiling and bonus:**
| Close type | Ceiling | Bonus |
|------------|---------|-------|
| WICK only  | 0.30    | +0.00 |
| CLOSE beyond level | 0.65 | +0.20 |
| Full BODY beyond level | 1.00 | +0.30 |

**Total score**: `min(disp_score × ceiling + bonus, ceiling)`

## Calibrated threshold

Optimal threshold from Phase 5C (1D BTCUSDT 2021): **0.60** (F1=0.571, up from initial guess of 0.50).

## Score predictiveness (Spearman ρ vs genuine outcome)

| Component | ρ | p-value | Significant? |
|-----------|---|---------|--------------|
| body_score | +0.380 | 0.020 | ✓ |
| total_score | +0.390 | 0.017 | ✓ |
| close_bonus | +0.369 | 0.025 | ✓ |
| range_score | −0.074 | 0.663 | ✗ |
| vol_score | −0.148 | 0.381 | ✗ |

## Key finding

**Body score and close type drive predictiveness; range and volume alone do not.** The close type alone (0% genuine for WICK, 33% for BODY) is the single most important filter.

## Assumptions & limitations

- Calibrated on 37 events (1D BTCUSDT 2021) — extremely small sample
- Only 3 genuine BOS events — threshold and weights are unreliable at this sample size
- Should be recalibrated on 180+ days, multiple instruments, multiple regimes
- aggTrades (delta at BOS bar) not included — may improve vol component

## Implementation notes

- State machine required: must track running Major Swing levels, current leg, and leg reset on each BOS
- One-bar confirmation lag: BOS confirmed at bar[i+1] close, not bar[i] close
- Genuine test: price must not return through broken level + 0.1% buffer within 12 bars

## Supports

- [[concepts/bos-break-of-structure]] — concept definition
- [[experiments/bos-score-1d-2021]] — validation experiment

## Questions generated

- Is the body score dominance robust across timeframes and instruments?
- Does adding delta at BOS bar improve vol_score predictiveness?

## My Take

The scoring framework is sound. The data is too thin to trust the weights or threshold. Priority: replicate on 2019–2023 daily data (multiple market regimes). The close-type filter alone is immediately actionable — just skip wick BOS events.
