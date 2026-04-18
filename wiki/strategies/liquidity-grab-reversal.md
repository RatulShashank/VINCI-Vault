---
title: Liquidity Grab and Reversal
type: strategy
tags: [liquidity, stop-hunt, reversal, BOS, FVG, OB, multi-TF]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Core Claim

When market sweeps a major swing level (liquidity grab), it signals an impending reversal. The direction of the first move after the sweep determines the future direction.

## Setup rules

1. Identify the major swing high or low on the relevant timeframe
2. Wait for price to take out the level (liquidity grab)
3. Observe the first BOS after the grab — this BOS direction is the signal direction
4. Enter on the retracement to the FVG within the displacement range of the BOS
5. Stop: below the low of the entry FVG (for longs) or above the high (for shorts)
6. Target: next opposing major swing level (ERL)

## Directionality rule

**The side that goes FIRST determines the final direction:**
- If market goes below a major swing low BEFORE going above a major swing high → **bullish** signal (the sweep below was the grab)
- If market goes above a major swing high BEFORE going below a major swing low → **bearish** signal

This is the most falsifiable claim in the notes and should be the primary backtest target.

## Multi-TF version

- 1H chart provides the structural context (major swing levels)
- 15m chart shows the FVG inside the displacement range
- 5m chart provides the precise entry timing and OB identification

Market may go below a swing low in 5m but only shows as a single candle in 1H — the 5m structure reveals the full manipulation.

## W-pattern variant

After hitting a large TF objective at level 1, market:
1. Pulls back and forms OB at level 2
2. Sweeps level 2 (the OB zone) creating the retracement
3. Final mitigation happens at level 3 (inside the W pattern)
4. Market does not go below 2 (that would shift structure)

## Empirical status

Not yet formally backtested. The directionality rule is derived from Notion exports (qualitative observations on BTCUSDT 2021 and 2024).

## Supports

- [[concepts/liquidity]] — core mechanism
- [[concepts/bos-break-of-structure]] — structural confirmation
- [[concepts/fair-value-gap]] — entry trigger
- [[concepts/order-block]] — entry zone
- [[concepts/market-structure]] — defines the swing levels to target

## Questions generated

- [[questions/first-move-directionality]] — quantitative test of the first-move rule

## My Take

This is the most interesting strategy candidate. The "first direction determines final direction" rule is specific enough to code and test. If it holds statistically, it's genuinely alpha-generating. Priority: formal backtest on BTCUSDT 1H data with precise swing level definitions.
