---
title: Close Type Is the Dominant Predictor of BOS Quality
type: insight
tags: [BOS, close-type, body, wick, scoring, filtering]
created: 2026-04-18
confidence: medium
status: tested
---

## Hypothesis

The way a BOS candle closes relative to the broken level (wick only vs close beyond vs full body beyond) predicts whether the BOS will hold better than displacement quality metrics (range expansion, volume).

## Proposed mechanism

A wick-only BOS means the closing price returned inside the range — sellers/buyers absorbed the breakout immediately. The market rejected the new level within the same bar. A full-body close beyond means the market spent the entire bar on the new side — indicating genuine acceptance, not just a temporary excursion.

## Supporting evidence

From [[experiments/bos-score-1d-2021]] (BTCUSDT 1D 2021, n=37 BOS events):
- WICK BOS: 0% genuine (n=21)
- CLOSE BOS: 15.4% genuine (n=13)
- BODY BOS: 33.3% genuine (n=3)

Spearman ρ: close_bonus vs genuine = +0.369, p=0.025 (significant)
body_score vs genuine = +0.380, p=0.020 (significant)

Range expansion and volume were NOT statistically significant predictors.

## What would falsify this

- WICK BOS genuine rate > 10% on larger dataset (1,000+ events)
- BODY BOS genuine rate not significantly different from CLOSE BOS
- Close type loses significance when controlling for trend regime

## Experiment designed

[[experiments/bos-score-1d-2021]] — validated (partially). Needs replication on larger dataset.

## Contradictions

None — no conflicting evidence yet.
