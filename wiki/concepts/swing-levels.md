---
title: Swing Levels
type: concept
tags: [market-structure, swing, major, minor, ICT]
created: 2026-04-18
updated: 2026-04-18
sources: 2
---

## Definition

A swing level is a 3-candle structure. A **swing high** forms when bar[i].high > bar[i-1].high AND bar[i].high > bar[i+1].high. A **swing low** is the mirror: bar[i].low < bar[i-1].low AND bar[i].low < bar[i+1].low. The candle colour does not matter — only the high/low relationship. Confirmation arrives one bar later (one-bar lag, no lookahead).

## Major vs Minor

**Major Swing High**: the highest swing high of the leg that broke above a previous Major Swing High via a BOS. Before a BOS up, the candidate major high is the highest swing high in the current leg.

**Major Swing Low**: the lowest swing low of the leg that produced the bullish BOS. Assigned retroactively to the lowest swing low in the breakout leg.

All other swing levels are **Minor**. Major levels determine the trend; minor levels are micro-structure within a leg.

## Empirical data (1D BTCUSDT 2021)

- 346 daily bars produced 164 swing levels: 81 highs, 83 lows
- Only 5 were classified as Major (3%), 159 as Minor
- Average bars between swings: 2.1 (on daily TF — very frequent)

## Role in trend

- **Uptrend**: each Major Swing Low must hold. A close below a Major Swing Low signals potential trend change or stall.
- **Downtrend**: mirror rule — each Major Swing High must hold.
- Market breaks minor swing levels freely without changing trend character.

## Supports

- [[bos-break-of-structure]] — BOS is defined relative to Major Swing Levels
- [[market-structure]] — trend is defined by the sequence of major swing highs and lows
- [[experiments/bos-score-1d-2021]] — empirical BOS results on daily BTCUSDT

## Contradicts

None identified.

## My Take

The 3-bar rule is clean and mechanical. The Major/Minor classification is the hard part — it is state-machine logic, not a simple local rule. Most discretionary traders misidentify majors; the empirical finding that only 5/164 are Major on the daily 2021 chart shows how rare genuine structural pivots are.
