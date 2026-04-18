---
title: ICT Market Maker Model
type: strategy
tags: [ICT, market-maker, liquidity, FVG, OB, BOS, smart-money]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Core Claim

Markets are driven by institutional "smart money" that engineers price to reach liquidity pools (stops and limits), fills orders at OBs/FVGs, and then delivers price to its objective. The retail trader's job is to read the delivery signature and trade with the delivery.

## The Model

1. **Accumulation**: Smart money accumulates at OB/FVG; price consolidates
2. **Manipulation (liquidity grab)**: price sweeps the opposite side (stop hunt) to fuel the move
3. **Distribution / Displacement**: strong directional move (BOS), creating FVG
4. **Rebalancing**: price returns to fill FVG within displacement range (entry zone)
5. **Continuation**: price delivers to objective (next ERL)

## ERL → IRL → ERL

Market cycles between External Range Liquidity (swing highs/lows outside the range) and Internal Range Liquidity (FVGs, OBs inside the range). Typical sequence:

- In bullish phase: price sweeps ERL below (sell-side liquidity grab), then targets ERL above. Internal FVGs are filled en route.
- Bearish phase: mirror.

## Entry logic

- Wait for BOS in the intended direction
- Wait for pullback into the OB or FVG within the displacement range
- Enter at the mitigation of the OB (or FVG fill)
- Stop below the Major Swing Low (for longs) or above Major Swing High (for shorts)

## Time-based context

- Session times matter: Asian forms the range, London takes Asian highs/lows, New York completes the move
- NY open acts as a structural anchor — price returning below NY midnight open = bearish day bias
- Day bias determines which side gets swept first

## Limitations

- Entirely discretionary in its original form — "premise" and "perspective" are judgment-dependent
- No published statistics on win rate or expectancy
- Requires accurate identification of Major vs Minor levels (hard to automate reliably)

## Supports

- [[concepts/liquidity]] — core fuel mechanism
- [[concepts/order-block]] — entry zone
- [[concepts/fair-value-gap]] — entry zone
- [[concepts/displacement]] — delivery mechanism
- [[concepts/bos-break-of-structure]] — structural trigger

## Contradicts

None within the vault currently.

## My Take

The model is internally consistent and describes price action well post-hoc. The challenge is that "premise" is a weasel word — in real time, multiple premises are competing. The quantitative BOS scoring experiment is the right first step toward making this model less discretionary.
