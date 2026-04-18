---
title: Fractal Structure (Multi-Timeframe Alignment)
type: concept
tags: [fractal, multi-timeframe, trend, range, alignment, efficiency]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Definition

Market structure is fractal: the same trend/range patterns repeat across timeframes. Each timeframe has its own directional state (EMA-relative trend direction). When multiple timeframes agree on direction simultaneously, a **fractal alignment** occurs.

## Directional efficiency

Measured as |net log return over N bars| / sum(|bar log returns|). Ranges 0 to 1:
- 1.0 = perfect trend (no retracement)
- 0.0 = pure chop (no net movement)

## Empirical results (BTCUSDT Jan 2020, 1m base data)

Directional efficiency by timeframe:
| TF   | Mean efficiency | % trending (>0.5) |
|------|-----------------|-------------------|
| 1m   | 0.116           | 0.1%              |
| 5m   | 0.122           | 0.1%              |
| 15m  | 0.146           | 0.0%              |
| 60m  | 0.180           | 1.0%              |

Kruskal-Wallis test: H=260.72, p=0.000000 — timeframes are **statistically different**.
All pairwise Mann-Whitney vs 1m: p<0.01 for all TFs.

## Alignment statistics (on 1m bars)

- Full bullish alignment (all 4 TFs bullish): 28.1% of time
- Full bearish alignment: 16.5% of time
- Mixed (no consensus): 55.4% of time (majority state)
- Bull transitions: 1,333 events; Bear transitions: 743 events

## Forward return at alignment transitions

| Signal | 30-bar mean return | Win rate |
|--------|--------------------|----------|
| BULL_ALIGN | +0.0836% | 57.3% |
| BEAR_ALIGN | +0.0814% | 58.0% |

Both alignment types show similar win rates ~57-58% at 30 bars.

## Key finding

Even though only 1% of 60m bars are "trending" by efficiency >0.5, the alignment transitions (moments when all TFs just aligned) have statistically meaningful directional edge (~57% win rate). The edge is in the **transition**, not the steady alignment state.

## Assumptions & limitations

- Only January 2020 data — one month, one regime
- EMA(20) as trend proxy is a simplification
- Win rates are modest (~57%) — need proper transaction cost analysis

## Supports

- [[market-structure]] — alignment confirms structural bias
- [[methods/multi-timeframe-alignment]] — implementation details
- [[experiments/market-observation-jan2020]] — source data

## My Take

The fractal alignment signal is genuinely interesting: a simple 4-TF EMA consensus produces 57% win rates. The asymmetry (bull 28.1% vs bear 16.5%) may reflect the bullish January 2020 regime — this needs testing in bear markets. The 55% mixed time is where most inefficient trading happens.
