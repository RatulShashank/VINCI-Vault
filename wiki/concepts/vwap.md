---
title: VWAP (Volume-Weighted Average Price)
type: concept
tags: [VWAP, market-microstructure, session, bands, confluence]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Definition

**VWAP** = cumulative(typical_price × volume) / cumulative(volume), reset each session. Typical price = (high + low + close) / 3. It represents the average price weighted by transaction size — the "fair" price institutional traders benchmark against.

## Standard deviation bands

±1σ and ±2σ bands computed from the rolling within-session standard deviation of price from VWAP. These mark statistical extremes of price from fair value.

## Empirical results (BTCUSDT Jan 2020, 1m bars)

Mean absolute 15-bar (15-minute) return when price touches each level:
| Event          | n     | Mean abs ret | Volume    | Taker buy% |
|----------------|-------|--------------|-----------|------------|
| VWAP           | 3,311 | 0.1388%      | 1.00×     | 49.3%      |
| 1SD_DN         | 3,411 | 0.1493%      | 0.92×     | 49.9%      |
| 1SD_UP         | 3,286 | 0.1437%      | 0.99×     | 51.5%      |
| 2SD_DN         | 2,155 | 0.1638%      | 1.05×     | 47.6%      |
| 2SD_UP         | 2,336 | 0.1813%      | 0.98×     | 51.4%      |
| VWAP + prev HL | 191   | 0.2099%      | 1.05×     | 50.5%      |

## Key findings

1. **Extremes move more**: 2σ bands produce ~30% more movement than VWAP touches
2. **VWAP + previous session high/low confluence** produces highest movement (0.21%), suggesting confluence amplifies the signal
3. Volume at touch is essentially flat across all events (~1×) — no volume spike at VWAP touches
4. Taker ratio is near 50% everywhere — VWAP touches are not directional by themselves

## Interpretation

These are **absolute** returns — not directional. VWAP touches produce volatility, not a specific direction. To get directional edge, VWAP must be combined with bias from [[market-structure]] or [[fractal-structure]].

## Assumptions & limitations

- Abs return measures movement, not direction — VWAP alone has no directional bias
- January 2020 only (31 sessions) — small sample
- 2σ upper band has highest movement (+0.18%) but n=2,336 means it fires frequently

## Supports

- [[volume-profile]] — VWAP and value area are complementary frameworks
- [[insights/vwap-confluence-amplifies-volatility]] — confluence finding

## My Take

VWAP is a volatility trigger, not a directional signal. The confluence finding (VWAP + prev session HL = +0.21%) is worth developing into a directional strategy by combining with structural bias. The 2σ upper band is the cleanest setup — rare enough to be meaningful, volatile enough to trade.
