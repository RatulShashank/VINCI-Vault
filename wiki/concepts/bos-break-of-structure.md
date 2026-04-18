---
title: Break of Structure (BOS)
type: concept
tags: [market-structure, BOS, ICT, trend-change, displacement]
created: 2026-04-18
updated: 2026-04-18
sources: 2
---

## Definition

A **BOS** (Break of Structure) occurs when price closes beyond the current Major Swing Level. Bullish BOS: bar closes above the current Major Swing High. Bearish BOS: bar closes below the current Major Swing Low. Wick-only breaks are lower quality; body-close or full-body breaks are stronger.

## On BOS: state update

- **Bullish BOS**: (1) the lowest swing low of the breakout leg becomes the new Major Swing Low; (2) the BOS bar's high becomes the candidate new Major Swing High; (3) leg resets.
- **Bearish BOS**: mirror — highest swing high of the leg becomes new Major Swing High.

## Quality scoring (quantitative)

Three components (weights from experiment):
- **body_score** (w=0.35): candle body / total candle range. Most predictive (ρ=+0.38, p=0.02).
- **range_score** (w=0.35): (high−low) / ATR(14), capped at 3×ATR. Not predictive alone.
- **vol_score** (w=0.30): volume / vol_MA(20), capped at 3×. Not predictive alone.

**Close type bonus** added on top:
- WICK only: ceiling 0.30, +0.00 bonus → 0% genuine empirically
- CLOSE beyond level: ceiling 0.65, +0.20 bonus → 15.4% genuine
- Full BODY beyond level: ceiling 1.0, +0.30 bonus → 33.3% genuine

**Optimal threshold**: 0.60 (F1=0.571, from 1D BTCUSDT 2021 calibration).

## Empirical results (1D BTCUSDT 2021, 346 bars)

- 37 BOS events detected: 30 bullish, 7 bearish
- 91.9% fake (price returned through broken level within 12 bars)
- 8.1% genuine (held for 12+ bars beyond level + 0.1% buffer)
- Genuine BOS forward returns (100% win rate on all 3 genuine events):
  - 6 bars: +19.7%
  - 12 bars: +28.3%
  - 48 bars: +39.0%

## Assumptions & limitations

- Sample n=3 genuine events is far too small for robust statistics; 100% win rate is noise not edge
- Single year (2021 — strong bull trend) biases toward bullish BOS
- aggTrades data unavailable → delta at BOS bar not measured
- Threshold calibrated on same data it was tested on (overfitting risk)

## Supports

- [[swing-levels]] — BOS defined via major swing levels
- [[displacement]] — BOS bar is often the displacement candle

## Contradicts

None identified.

## My Take

The close type result is the real finding here: wick-only BOS has zero genuine rate. This alone justifies filtering out wick breaks. The scoring system has the right structure but needs much more data (180+ days, multiple regimes) before the threshold is trustworthy. The huge forward returns on genuine BOS are tantalizing but built on 3 examples.
