---
title: Volume Delta Analysis
type: method
tags: [delta, volume, taker, CVD, microstructure, aggTrades]
created: 2026-04-18
updated: 2026-04-18
sources: 2
---

## Definition

**Delta** = taker buy volume − taker sell volume per bar (or per price bucket in a profile). A positive delta means aggressive buyers dominated; negative means aggressive sellers dominated.

**CVD (Cumulative Volume Delta)** = running sum of delta over time. A rising CVD with falling price = bearish divergence (sellers building despite price rise). Falling CVD with rising price = bullish divergence.

## Data requirements

Raw aggTrades data (tick-level): each trade has `is_buyer_maker` flag. If `is_buyer_maker=True`, the taker was selling (market sell order). If `False`, the taker was buying (market buy order).

`signed_qty = -qty if is_buyer_maker else +qty`

## Applications

### 1. Delta at swing endpoints

**Hypothesis**: at reversals, delta should show exhaustion (opposing the recent move direction).

**Result** (BTCUSDT Jan 2020, 5m, 1,883 swing points):
- Swing high reversal: delta_z = +0.359 vs continuation: +0.255 (direction correct, not significant)
- Swing low reversal: delta_z = −0.464 vs continuation: −0.335 (direction correct, not significant)
- Mann-Whitney p-value: NaN (computational issue — likely zero-variance groups)

**Conclusion**: directional signal exists but statistical test failed. Needs debugging before conclusions can be drawn.

### 2. Delta at volume profile levels (HVN)

HVN with buy delta (positive): +0.1501% 30-bar forward return
HVN with sell delta (negative): +0.0250% 30-bar forward return

Delta sign at HVN adds 6× the directional information of HVN alone.

### 3. CVD in wavelet research

Used as a feature in the jump classification model. CVD slope and CVD/price divergence are features in the micro-regime detector.

## Assumptions & limitations

- aggTrades is large (68M ticks for Jan 2021) — memory-intensive
- Taker buy/sell classification assumes `is_buyer_maker` from Binance aggTrades is accurate
- Delta divergence at swings needs statistical test debugging (NaN p-values)

## Supports

- [[concepts/volume-profile]] — delta profile per price bucket
- [[methods/multi-timeframe-alignment]] — CVD as alignment feature
- [[experiments/market-observation-jan2020]] — empirical results

## Questions generated

- [[questions/delta-reversal-signal-gap]] — why did the Mann-Whitney test return NaN?

## My Take

Delta is the closest thing to "intent" available from market data. The HVN delta sign finding is practically useful now. The swing endpoint analysis needs the NaN bug fixed before it can be trusted — this is priority debugging work.
