---
title: BOS Scoring — BTCUSDT Daily 2021
type: experiment
tags: [BOS, scoring, swing-levels, major-minor, calibration, 1D, BTCUSDT, 2021]
created: 2026-04-18
updated: 2026-04-18
notebook: codes/final/swing_structure_bos_result_1D_0.5 threshold._newipynb.ipynb
status: complete
sources: 1
---

## Hypothesis tested

A quantitative BOS score (body ratio, range expansion, volume, close type) can distinguish genuine BOS events (price holds the new structure) from fake ones (price reverses within 12 bars). Total score threshold of 0.50 (initial) / 0.60 (optimized) filters meaningfully.

## Method

- BTCUSDT 1D klines: 525,588 1m bars resampled to daily (2021-01-01 to 2021-12-31)
- 346 daily bars after ATR/volume MA warmup period
- Swing detection: strict 3-bar rule, one-bar confirmation lag
- Major/Minor classification: state machine tracking BOS events and retroactive labeling
- BOS scoring: body_score (w=0.35) + range_score (w=0.35) + vol_score (w=0.30) + close type bonus
- Genuine test: price must not return through broken level + 0.1% buffer within 12 daily bars
- Phase 5C: threshold sweep using F1 score optimization

## Data used

BTCUSDT 1D candles, full year 2021. aggTrades not available for this run.

## Results

### Structure detection
- 164 swing levels: 81 highs, 83 lows (avg 2.1 bars between swings)
- Major: 5 (3%), Minor: 159 (97%)
- 37 BOS events: 30 bull, 7 bear
- 9 above initial threshold (0.50), avg total score: 0.300

### BOS outcomes (n=37 measured)
- Genuine: 3 (8.1%)
- Fake: 34 (91.9%)
- Suspect fake: 0

### Score predictiveness (Spearman ρ vs genuine outcome)
| Component | ρ | p | Significant |
|-----------|---|---|-------------|
| body_score | +0.380 | 0.020 | ✓ |
| total_score | +0.390 | 0.017 | ✓ |
| close_bonus | +0.369 | 0.025 | ✓ |
| range_score | −0.074 | 0.663 | ✗ |
| vol_score | −0.148 | 0.381 | ✗ |

### Genuine rate by close type
| Type | Genuine rate | n |
|------|-------------|---|
| WICK | 0.0% | 21 |
| CLOSE | 15.4% | 13 |
| BODY | 33.3% | 3 |

### Threshold calibration
- Initial: 0.50
- Optimal: **0.60** (F1=0.571)
- Difference justifies update

### Genuine BOS forward returns (all 3 genuine events, 100% win rate)
| Horizon | Mean return |
|---------|-------------|
| 6 bars  | +19.7%      |
| 12 bars | +28.3%      |
| 24 bars | +19.0%      |
| 48 bars | +39.0%      |

## Conclusion

1. WICK BOS should be immediately filtered — 0% genuine rate is clear
2. Body score and total score are the only statistically significant predictors
3. Range expansion and volume are individually not predictive on daily BOS
4. Optimal threshold: 0.60 (was 0.50)
5. Genuine BOS events have massive forward returns, but n=3 is far too small to trust

## Shifts thesis?

Partially. Validates the structural framework (swing levels are real, BOS is detectable) but warns that most detected BOS events are fake on the daily timeframe in 2021.

## Assumptions & limitations

- 2021 was a strong bull year — bearish BOS events (n=7) are underpowered
- n=3 genuine events makes all statistics unreliable
- No aggTrades data — delta at BOS bar missing
- Threshold calibrated on training data (no out-of-sample test)

## Next steps

- Extend to 2019–2024 (5 years, multiple regimes)
- Add delta at BOS bar when aggTrades available
- Test cross-instrument (ETH, other perpetuals)
- Combine BOS score ≥0.60 with fractal alignment signal for composite filter
