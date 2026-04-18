---
title: Does the First Directional Move at a Major Swing Level Predict Final Direction?
type: question
tags: [liquidity, BOS, directionality, first-move, swing, ICT, backtest]
created: 2026-04-18
gap_source: concepts/liquidity — "first direction determines final direction" claim
status: open
---

## Gap identified

The Notion exports make a strong and specific claim: "It's all a matter of which direction happens first that determines the direction." When market is at a major swing level and breaks both directions sequentially, the side that was broken FIRST determines the ultimate direction. This claim has no quantitative evidence in the vault yet.

## Clusters involved

ICT market structure cluster ↔ empirical validation cluster. The structural concepts are well-developed but untested; the experimental cluster has BOS scoring and volume profile but not this specific directional test.

## Why it matters for the thesis

This is the highest-potential falsifiable claim in the vault. If it holds (>60% accuracy), it constitutes a tradeable signal based purely on structural sequence — no volume, no delta required. It would be the foundation of [[strategies/liquidity-grab-reversal]].

## Research question

Given a major swing level that is broken in both directions within a defined window (N bars), does the direction of the FIRST break predict the direction of the move at bar N+K with statistically significant accuracy?

## Related concepts

- [[concepts/liquidity]] — theoretical basis
- [[concepts/bos-break-of-structure]] — measurement of direction
- [[concepts/swing-levels]] — definition of major levels
- [[strategies/liquidity-grab-reversal]] — strategy dependent on this

## Leads

**Implementation plan:**
1. Use the swing detection state machine from [[experiments/bos-score-1d-2021]]
2. Identify all instances where price breaks both the current major high and major low within N bars (N = 5, 10, 20)
3. Record which side was broken first
4. Measure forward return at K bars in the direction of the FIRST break
5. Compare against random baseline and against LAST break direction

**Expected sample size:** On 1D data (2019–2024), roughly 250 such events. On 15m data, thousands.

**Papers to find:** literature on "first test" at price levels, market microstructure at support/resistance
