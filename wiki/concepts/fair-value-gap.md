---
title: Fair Value Gap (FVG)
type: concept
tags: [ICT, FVG, imbalance, displacement, rebalancing]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Definition

A **Fair Value Gap** (FVG) is a 3-candle imbalance: bar[i+1] moves so strongly that there is a gap between bar[i].high and bar[i+2].low (bullish FVG) or between bar[i].low and bar[i+2].high (bearish FVG). It represents an area where price moved too fast for the market to transact at every level — creating an "unfilled" region.

## Quality of FVG

Not all FVGs are equal:
- **Good FVG**: candles with little wicks — price is unidirectional; shows momentum/distribution.
- **Poor FVG**: candles with many wicks on the FVG candles — price struggled, likely final push before manipulation. An FVG that then gets inverted (price trades through it from the other side) signals the opposing direction is likely.

## FVG within displacement range

Only the FVG **within the ICT displacement range** of the relevant move is the true target. Random FVGs outside this range are lower priority. The displacement range is typically measured from the last major swing level to the BOS bar.

## Role in market structure

- After a BOS, market returns to fill the FVG within the displacement range before continuing
- Market maker model: price displaces, creates FVG, returns to fill it, then continues the original direction
- FVG acts as an OB (order block) when the imbalance is inside an existing OB area

## Supports

- [[order-block]] — OB and FVG frequently coincide
- [[displacement]] — FVG is created by displacement moves
- [[strategies/ict-market-maker-model]] — FVG fill is step 2 of the model

## Contradicts

None identified.

## My Take

FVG is the most useful concept from the Notion exports for precise entry timing. The quality filter (wick analysis) is practical and testable. The "FVG within displacement range only" rule is a useful constraint that reduces noise by limiting which FVGs actually matter.
