---
title: Multi-Timeframe Alignment
type: method
tags: [multi-timeframe, alignment, fractal, EMA, trend, signal]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Purpose

Detect moments when all observed timeframes agree on trend direction simultaneously — these transitions have statistically measurable directional edge.

## Implementation

1. Compute EMA(20) on each timeframe: 1m, 5m, 15m, 60m
2. Assign trend direction: +1 if close > EMA, −1 if close < EMA
3. Forward-fill higher TF directions onto the 1m index
4. Compute alignment score = sum of directions (−4 to +4)
5. **Bull signal**: score transitions from <4 to +4 (all TFs just aligned bullish)
6. **Bear signal**: score transitions from >−4 to −4 (all TFs just aligned bearish)

## Results (BTCUSDT Jan 2020, 1m bars, 44,639 bars)

| State | % of time |
|-------|-----------|
| Full bull (+4) | 28.1% |
| Full bear (−4) | 16.5% |
| Mixed | 55.4% |

Transitions: 1,333 bull entries, 743 bear entries

**Forward return at transitions** (direction-adjusted):
| Horizon | Bull mean | Bull win% | Bear mean | Bear win% |
|---------|-----------|-----------|-----------|-----------|
| 5 bars  | +0.039%   | 63.5%     | +0.054%   | 66.0%     |
| 15 bars | +0.059%   | 59.6%     | +0.067%   | 59.8%     |
| 30 bars | +0.084%   | 57.3%     | +0.081%   | 58.0%     |
| 60 bars | +0.115%   | 54.7%     | +0.087%   | 54.1%     |

## Key findings

1. Win rates peak at short horizons (5 bars: 63–66%) and decay
2. Bear alignment has slightly higher short-term win rate than bull
3. 55% of time is "mixed" — most bars have no signal
4. Edge exists but is small: ~57–66% win rate needs tight transaction cost control

## Extensions

- Add volume or delta confirmation at transition point
- Combine with BOS scoring for higher-conviction entries
- Test in trending vs ranging regimes separately

## Assumptions & limitations

- EMA(20) is a simple proxy for trend; other trend definitions may improve results
- January 2020 only — one regime
- No transaction costs modeled
- 1-bar lag in higher TF signals (forward-fill introduces some timing imprecision)

## Supports

- [[concepts/fractal-structure]] — concept foundation
- [[experiments/market-observation-jan2020]] — empirical data

## My Take

The 5-bar win rate of 63–66% is the most actionable number in the vault. At 1m bars, 5 bars = 5 minutes, so this is a very short-term signal. The key question: is this edge real or is it a January 2020 artifact? Testing on a full year with costs is the immediate priority.
