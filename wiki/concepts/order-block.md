---
title: Order Block (OB)
type: concept
tags: [ICT, order-block, rebalancing, manipulation, smart-money]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Definition

An **Order Block** (OB) is the last opposing candle (or group of candles) before a significant directional displacement. It represents where smart money placed orders that caused the move — market is expected to return to this zone to "mitigate" the manipulation.

- **Bullish OB**: the last bearish candle (or series of red candles) before a strong up move.
- **Bearish OB**: the last bullish candle (or series of green candles) before a strong down move.

## Identification rules

1. Look for the **last opposite-colour candle** just before the impulsive displacement.
2. A large hammer or strong single-candle move also acts as a good OB.
3. Continuous same-colour candles just before displacement = OB zone (e.g., continuous green candles before a BOS up are a bearish OB for future).
4. Premise matters — an OB is only valid within the context of the directional bias. An arbitrary retracement candle is not an OB.

## Rebalancing mechanics

- When market returns to an OB, it bounces: fills the OB zone and continues in the displacement direction.
- Extent: market does not go beyond the 3rd candle of the swing that formed the OB (for bullish OB, it won't go below the 3rd candle's low; for bearish OB, won't go above the 3rd candle's high).
- Market may go beyond the OB slightly if there's a minor FVG inside the OB area, but not beyond the structure that would negate the OB's premise.

## W-structure pattern

After hitting a large timeframe objective, market balances itself by:
1. Hitting one level (point 1)
2. Forming an OB / completing the move at point 2
3. Finishing mitigation at point 3 (W-shaped retracement)

Market does not go below the structural pivot of the W pattern as that would shift market structure.

## Supports

- [[fair-value-gap]] — OB and FVG often coincide, forming strong confluence
- [[displacement]] — OB is defined by the displacement that follows it
- [[strategies/ict-market-maker-model]] — OB is the entry point in the model

## My Take

OB is the most mechanical concept in ICT — the "last opposing candle" rule is simple to code. The hard part is premise: distinguishing a valid OB from a random opposite candle requires knowing the broader directional bias. The 3rd candle rule for extent is testable and worth formalizing.
