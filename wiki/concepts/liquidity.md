---
title: Liquidity
type: concept
tags: [ICT, liquidity, stop-hunt, ERL, IRL, buy-side, sell-side]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Definition

**Liquidity** refers to clusters of resting orders (stop losses, limit orders) that price targets to fill large institutional positions. Smart money needs liquidity to enter and exit positions efficiently; it engineers price to reach these pools.

## Types

- **Buy-side liquidity (BSL)**: resting buy stops above swing highs. Market hunts these to fill institutional sell orders.
- **Sell-side liquidity (SSL)**: resting sell stops below swing lows. Market hunts these to fill institutional buy orders.
- **ERL (External Range Liquidity)**: liquidity outside the current range — swing highs and lows beyond the established range. Higher priority targets.
- **IRL (Internal Range Liquidity)**: liquidity inside the current range — FVGs, imbalances, OBs. Lower-priority retracement targets.

## Mechanics of the liquidity grab

1. Market moves toward the liquidity pool (stop hunt)
2. Once liquidity is taken (swing broken), market dumps opposite — below the **immediate** major swing level, not the previous one
3. The direction of the FIRST move determines the ultimate direction:
   - Goes below a major swing first → bullish ultimately
   - Goes above a major swing first → bearish ultimately
4. After taking one liquidity pool, market must balance by reaching the opposite pool

## Key rules

- Market targets and sweeps highs in premium zone during bearish bias; ignores lows
- After crossing 50% of a range, if bearish: all liquidity above 50% is gathered before dumping — not a reversal, still continuation
- Once BOS down occurs, market stops seeking upward liquidity
- Market does not randomly extend beyond a swing: it goes to the exact FVG or OB level that justifies the extension

## Supports

- [[swing-levels]] — swing highs/lows are the liquidity pools
- [[strategies/liquidity-grab-reversal]] — tradeable pattern built on this concept
- [[fair-value-gap]] — FVG is often the IRL target after a liquidity grab

## My Take

The directionality-by-first-move rule is the most powerful and testable idea in the Notion exports. "Which direction happens first determines the direction" is a falsifiable hypothesis. This should be the first thing to backtest formally.
