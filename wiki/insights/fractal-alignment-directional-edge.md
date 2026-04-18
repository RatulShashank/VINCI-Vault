---
title: Fractal Alignment Transitions Have Short-Horizon Directional Edge
type: insight
tags: [fractal, alignment, multi-timeframe, EMA, edge, win-rate]
created: 2026-04-18
confidence: low
status: hypothesis
---

## Hypothesis

When all measured timeframes (1m, 5m, 15m, 60m) simultaneously agree on directional bias (all above or all below EMA(20)), the first bars of this alignment state have statistically significant directional edge.

## Proposed mechanism

Multi-TF alignment means the dominant institutional flow is consistent at all scales of resolution. This state is rare (only ~28% bull, ~16% bear) and represents periods where supply/demand is genuinely imbalanced. The transition into alignment (the moment of convergence) captures the strongest part of this imbalance before it is absorbed.

## Supporting evidence

From [[experiments/market-observation-jan2020]] (BTCUSDT Jan 2020, 1m):
- Bull alignment transitions: 5-bar win rate 63.5%, 30-bar win rate 57.3%
- Bear alignment transitions: 5-bar win rate 66.0%, 30-bar win rate 58.0%
- Kruskal-Wallis: TFs are statistically different in efficiency (p=0.000)

## What would falsify this

- Win rate ≤ 52% with transaction costs in out-of-sample test (2022 bear market)
- Win rate equivalent in "mixed" state vs alignment transition
- Effect disappears when controlling for HTF trend regime

## Experiment designed

Partial — [[experiments/market-observation-jan2020]] validates the concept on January 2020 only. Full backtest on 2019–2024 needed.

## Contradictions

None yet. Risk: January 2020 was a bullish month — bull alignment bias may inflate results.
