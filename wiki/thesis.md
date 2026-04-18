# VINCI Thesis

Last updated: 2026-04-18

---

## Core belief

**BTC perpetual futures price delivery is not random.** It follows a liquidity-driven delivery mechanism where institutional participants engineer price to reach specific levels (liquidity pools, OBs, FVGs) before displacing. This delivery is readable in advance from market structure and order flow, and quantifiable in degree using microstructure data.

---

## Supported beliefs

### 1. Major Swing Levels are structural anchors (confidence: HIGH)
Major swing levels (defined by the BOS state machine) define the trend. Only their violation constitutes a trend change. This is confirmed by the BOS experiment: 91.9% of detected BOS events are fake, suggesting the market tests major levels frequently but only rarely genuinely breaks them.

**Evidence**: [[experiments/bos-score-1d-2021]]

### 2. BOS quality is predictable from candle structure (confidence: MEDIUM)
Body score (ρ=+0.38, p=0.02) and close type (0% genuine for wick-only, 33% for body-close) are statistically significant predictors of genuine BOS. Range expansion and volume are not.

**Evidence**: [[experiments/bos-score-1d-2021]], [[insights/close-type-predicts-bos-quality]]

### 3. Volume profile levels guide next-session behavior (confidence: LOW-MEDIUM)
LVN > VAH > HVN > VAL > POC in terms of forward momentum at next-session touch. Delta sign at HVN adds significant directional information.

**Evidence**: [[experiments/market-observation-jan2020]]
**Caveat**: Only 31 sessions of data. Needs replication.

### 4. Fractal alignment transitions have short-horizon edge (confidence: LOW)
When 1m/5m/15m/60m EMA direction all align simultaneously, the first 5 bars show 63–66% win rate.

**Evidence**: [[experiments/market-observation-jan2020]], [[insights/fractal-alignment-directional-edge]]
**Caveat**: January 2020 only — bullish regime. Bear market replication needed.

### 5. BTC jump dynamics are classifiable and calibrated (confidence: MEDIUM)
Wavelet + microstructure features produce calibrated jump outcome predictions at 40–70% confidence. 85% of jumps are endogenous. Strong directional classes (strong_up/down) have Brier 0.068–0.070.

**Evidence**: [[experiments/wavelet-jump-classification]], [[insights/jump-calibration-edge]]

---

## Unvalidated hypotheses (beliefs without experiment)

- **First-move directionality**: The direction broken FIRST at a major swing level predicts the ultimate direction. (No backtest yet — [[questions/first-move-directionality]])
- **OB mitigation as entry**: Entering at the last opposing candle before displacement is a high-quality entry. (Not quantified)
- **ICT session timing**: Asian high/London high sequence predicts NY direction. (Not quantified)
- **FVG within displacement range is the only valid target**: FVGs outside the displacement range are noise. (Not quantified)

---

## What would shift this thesis

1. First-move directionality backtest showing <52% accuracy → the structural narrative collapses
2. BOS scoring replication on 500+ events showing close type is not predictive → revert to simpler rule
3. Jump model Brier degrading to >0.20 on 2026 data → model is overfit
4. Fractal alignment failing in bear market 2022 → regime-dependent only

---

## Open gaps (from [[gap-engine/gaps.md]])

1. No wickless strategy wiki page (unprocessed notebooks)
2. No BTC macro correlation wiki page (unprocessed notebooks)
3. No author pages (ICT cited repeatedly without a page)
4. Delta Mann-Whitney NaN bug blocks swing endpoint analysis
5. All PDFs unread (AMT theory, wavelet papers, pnas paper)
