---
title: Volume Profile
type: concept
tags: [volume, market-microstructure, POC, VAH, VAL, HVN, LVN, delta]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Definition

Volume Profile maps volume traded at each price level over a session. Unlike time-based volume, it reveals where the market has accepted or rejected price.

## Key levels

- **POC (Point of Control)**: price level with the highest volume. Represents the fairest price of the session.
- **VAH (Value Area High)**: upper boundary of the zone containing 70% of session volume.
- **VAL (Value Area Low)**: lower boundary of the 70% value area.
- **HVN (High Volume Node)**: price levels with volume > 2× session median. Strong support/resistance — price accepts and dwells here.
- **LVN (Low Volume Node)**: price levels with volume < 0.4× session median. Price tends to travel through these quickly.

## Delta volume profile

Same as above but uses signed volume (taker buy − taker sell) per price bucket. Requires aggTrades tick data. A HVN with positive delta = buyers dominated at that level; negative delta = sellers dominated.

## Empirical results (BTCUSDT Jan 2020, 31 daily sessions)

30-bar (30-minute) forward return when next-day price touches previous session level:
| Level | Mean return | n |
|-------|-------------|---|
| LVN   | +0.2178%    | 72 |
| VAH   | +0.1988%    | 24 |
| HVN   | +0.0817%    | 97 |
| VAL   | +0.0050%    | 22 |
| POC   | −0.0465%    | 24 |

HVN with buy-delta: +0.1501% vs HVN with sell-delta: +0.0250% (delta direction matters).

## Interpretation

- LVN is the best forward return when touched — price moves quickly through thin areas, enabling momentum plays
- POC has mean-reverting character (−0.05%) — price is "fair" here and tends to consolidate
- VAH acts as resistance-turned-support (or vice versa)
- n values are small (31 days) — patterns are directional but not statistically robust yet

## Assumptions & limitations

- Only January 2020 data (31 sessions) — strongly limited sample
- aggTrades data was from Jan 2021, not Jan 2020 — delta profile has data mismatch
- Results need replication over 365+ days to assess robustness

## Supports

- [[vwap]] — VWAP and value area are related structural concepts
- [[methods/volume-delta]] — delta profile is a core input
- [[experiments/market-observation-jan2020]] — source of all empirical numbers

## My Take

The LVN > VAH > HVN > VAL > POC ranking is counterintuitive (LVN being highest) but makes mechanical sense — price whips through thin areas. The delta sign at HVN is the most interesting signal and deserves a dedicated experiment with a full year of data.
