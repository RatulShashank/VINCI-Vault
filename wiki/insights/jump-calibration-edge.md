---
title: Wavelet Jump Model Is Calibrated at 40–70% Confidence Band
type: insight
tags: [wavelet, jump, LightGBM, calibration, edge, Brier, HMM]
created: 2026-04-18
confidence: medium
status: tested
---

## Hypothesis

A LightGBM model trained on wavelet + microstructure features to predict 1-hour BTC jump outcomes produces calibrated probability estimates in the 40–70% confidence range, representing actionable edge.

## Proposed mechanism

Jumps in BTC perpetuals carry information in their pre-jump wavelet structure (volatility buildup shape, imaginary trend of CWT coefficients) and microstructure (CVD slope, funding rate change). These features capture the endogenous vs exogenous nature of the jump, which predicts whether the directional move will continue or reverse within 1 hour.

## Supporting evidence

From [[experiments/wavelet-jump-classification]] (BTCUSDT 2022–2025):
- At 40–50% confidence: predicted 43.4%, actual 44.5% — deviation 1.1% (EDGE)
- At 50–60% confidence: predicted 53.8%, actual 51.7% — deviation 2.1% (EDGE)
- At 60–70% confidence: predicted 62.6%, actual 62.1% — deviation 0.5% (EDGE)
- At 70–80% confidence: predicted 76.4%, actual 71.4% — deviation 5.0% (NO EDGE)
- Strong directional classes (strong_up, strong_down): Brier 0.068–0.070 (excellent)
- 85% of jumps are endogenous — internal structural dynamics dominate

## What would falsify this

- Calibration deviation >5% in fresh year (2026)
- Strong directional class Brier degrades to >0.15 on new data
- Edge disappears when accounting for transaction costs and bid/ask spread

## Experiment designed

[[experiments/wavelet-jump-classification]] — validated on 2025 hold-out data.

## Contradictions

None. Limitation: flat class remains poorly calibrated (Brier 0.22) — excludes meaningful portion of the signal space.
