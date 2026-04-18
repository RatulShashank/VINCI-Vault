---
title: VWAP + Previous Session High/Low Confluence Amplifies Volatility
type: insight
tags: [VWAP, confluence, volatility, previous-session, key-levels]
created: 2026-04-18
confidence: low
status: hypothesis
---

## Hypothesis

When price touches VWAP at the same price as the previous session's high or low, the resulting volatility is significantly higher than VWAP touches alone — because two independent level-types are confluent, concentrating resting orders at the same price.

## Proposed mechanism

VWAP represents the institutional "fair value" anchor for the current session. Previous session highs/lows represent stop clusters (liquidity). When they coincide, the same price level attracts both mean-reversion VWAP traders AND stop-hunt participants, creating higher transactional activity and larger price moves.

## Supporting evidence

From [[experiments/market-observation-jan2020]] (BTCUSDT Jan 2020, 1m):
- VWAP_PREV_HL confluence: 0.210% abs 15-bar return (n=191)
- Plain VWAP touch: 0.139% abs 15-bar return (n=3,311)
- 2σ upper band: 0.181% abs 15-bar return
- Confluence is +51% higher volatility than plain VWAP

## What would falsify this

- Confluence abs return ≤ VWAP alone in larger dataset
- Volume at confluence not meaningfully elevated (observed: 1.05× vs 1.00×, marginal)
- Effect is directional rather than volatility-based (taker at confluence: 50.5% — neutral)

## Experiment designed

Not yet designed. Would need: isolate confluence events, test directionality with structural bias, measure on full year.

## Contradictions

None. Note: n=191 confluence events in one month is reasonable, but confidence remains low until replicated.
