---
title: Why Does Delta Z-Score Not Separate Reversals from Continuations?
type: question
tags: [delta, swing, reversal, Mann-Whitney, statistical-testing, bug]
created: 2026-04-18
gap_source: experiments/market-observation-jan2020 Phase 1D
status: open
---

## Gap identified

The market observation experiment showed a directional delta signal at swing endpoints (reversals have higher absolute delta z-score than continuations) but the Mann-Whitney statistical test returned NaN for both swing highs and swing lows. This makes it impossible to determine if the signal is real.

## Clusters involved

Volume-delta cluster ↔ swing structure cluster. These should be strongly connected (delta at pivots is a core microstructure concept) but the link is broken by the test failure.

## Why it matters for the thesis

If delta exhaustion at swing endpoints is a real signal, it would provide a leading indicator for reversals that precedes price confirmation — enabling earlier entries than BOS-based methods. This could be the "final bar before reversal" pattern hinted at in the ICT notes.

## Research question

What caused the NaN p-values in the Mann-Whitney test, and does a valid statistical test confirm that delta z-score at reversals differs significantly from continuations?

## Related concepts

- [[concepts/volume-delta]] — delta methodology
- [[methods/volume-delta]] — implementation
- [[experiments/market-observation-jan2020]] — source of the NaN result

## Leads

**Probable causes of NaN:**
1. Zero-variance group: if all delta_z values in one group are identical (e.g., all NaN or 0), Mann-Whitney fails
2. The rolling delta_z calculation may produce NaN values for the first 20 bars; if swing points cluster in the early data, one group may be all-NaN
3. The `stats.mannwhitneyu` function returns NaN when input arrays contain NaN or have insufficient unique values

**Fix approach:**
1. Add `.dropna()` before Mann-Whitney call
2. Print delta_z distribution for each group to check for degenerate values
3. Use a non-parametric bootstrap test as fallback
4. Run on full year data (not just January) to get sufficient sample sizes

**Papers to find:** literature on order flow imbalance at price reversals (market microstructure)
