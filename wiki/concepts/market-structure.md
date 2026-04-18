---
title: Market Structure
type: concept
tags: [market-structure, trend, BOS, range, ICT, HTF, LTF]
created: 2026-04-18
updated: 2026-04-18
sources: 2
---

## Definition

Market structure is the sequence of Major Swing Highs and Major Swing Lows that defines the trend. A trend is not just "higher highs and higher lows" — it specifically refers to the **Major** swing levels, not minor ones.

## Trend classification

- **Uptrend**: sequence of higher Major Swing Highs and higher Major Swing Lows. Market should NOT break a Major Swing Low; it can break any number of minor swing lows.
- **Downtrend**: lower Major Swing Highs and lower Major Swing Lows. Market should NOT break a Major Swing High.
- **Range**: no clear directional break of major levels.

## Range identification

A range has two types:
- **Bullish internal range**: formed by first a down move then an up move (First ↓, then ↑). BOS determines which is first.
- **Bearish internal range**: formed by first an up move then a down move (First ↑, then ↓).

## Key rules

1. Market can violate minor swing levels freely — this is noise.
2. Violation of a Major Swing Low in an uptrend = probability of stall or reversal.
3. After a BOS, market must retrace to balance the FVG within the displacement range before continuing.
4. When market breaks a structure at an important level (ERL), it will balance the leg above/below it.

## Multi-timeframe hierarchy

Lower timeframe structure exists within higher timeframe structure. An LTF bearish swing is often just a retracement in an HTF bullish trend. Resolution: read from HTF to LTF — HTF determines bias; LTF determines entry.

## Session timing effects

- Asian high is typically taken first in London session, London high taken in New York
- NY open and midnight marks act as anchors for intraday structure
- Day bias (bullish/bearish) is determined by which side price targets first

## Supports

- [[swing-levels]] — structural pivots
- [[bos-break-of-structure]] — transitions between structural states
- [[fractal-structure]] — multi-TF alignment of structural bias
- [[liquidity]] — structural moves target liquidity pools

## My Take

The most important practical insight from the notes: perspective determines everything. The same market looks bullish on 1H and bearish on 4H — the HTF always wins for bias, LTF for entries. Coding Major/Minor correctly is the hardest step and the biggest source of discretionary error.
