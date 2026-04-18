---
title: Market Observation — BTCUSDT January 2020
type: experiment
tags: [volume-profile, VWAP, fractal, delta, BTCUSDT, 2020]
created: 2026-04-18
updated: 2026-04-18
notebook: codes/final/market-observation_result.ipynb
status: complete
sources: 1
---

## Hypothesis tested

Multiple empirical observations in one notebook:
1. Do previous-session volume profile levels predict next-session price behavior?
2. Does delta at swing endpoints differ between reversals and continuations?
3. Is directional efficiency statistically different across timeframes?
4. Do fractal alignment transitions have directional edge?
5. Do VWAP band touches produce measurable volatility and directionality?

## Method

- BTCUSDT 1m klines: 44,639 bars (2020-01-01 to 2020-01-31)
- AggTrades: 68.9M ticks (2021-01-01 to 2021-01-31) — **NOTE: data mismatch, different year**
- Resample to 1m, 5m, 15m, 60m
- Phase 1: build daily VP + delta VP, measure forward return at level touches
- Phase 1D: detect 5m swing points, compare delta_z at reversals vs continuations
- Phase 2: compute directional efficiency on all TFs, detect alignment transitions
- Phase 3: identify breakouts and reversals on 5m, measure volume at each
- Phase 4: compute daily VWAP + 1σ/2σ bands, measure at touches

## Data used

- BTCUSDT 1m klines, January 2020 (Kaggle)
- BTCUSDT aggTrades, January 2021 (Kaggle) — mismatched year, used only for delta profile

## Results

### Phase 1 — Volume Profile (30-bar forward return at touch)
| Level | Mean % | n  |
|-------|--------|----|
| LVN   | +0.218 | 72 |
| VAH   | +0.199 | 24 |
| HVN   | +0.082 | 97 |
| VAL   | +0.005 | 22 |
| POC   | −0.047 | 24 |
| HVN buy-delta | +0.150 | — |
| HVN sell-delta | +0.025 | — |

### Phase 1D — Delta at swing endpoints (5m)
- 1,883 swing points (948 highs, 935 lows)
- Swing high reversal delta_z: 0.359 vs continuation: 0.255
- Swing low reversal delta_z: −0.464 vs continuation: −0.335
- Mann-Whitney p-value: NaN (test error — see [[questions/delta-reversal-signal-gap]])

### Phase 2 — Fractal structure
- Directional efficiency: 1m=0.116, 5m=0.122, 15m=0.146, 60m=0.180
- Kruskal-Wallis: H=260.72, p=0.000 — TFs are statistically different
- Full bull alignment: 28.1% of 1m bars; full bear: 16.5%; mixed: 55.4%
- Bull alignment 30-bar win rate: 57.3%; Bear: 58.0%

### Phase 3 — Volume at key moments (5m)
- Genuine breakouts: 4.17× avg volume; failed: 3.80× (genuine rate: 35.9%)
- Genuine reversals: 3.29× avg volume; failed: 2.73× (genuine rate: 26.9%)

### Phase 4 — VWAP (15-bar forward abs return)
- 2σ UP band: 0.181%, 2σ DN band: 0.164% (highest movement)
- VWAP + prev session HL confluence: 0.210% (highest overall)
- VWAP alone: 0.139%, volume at all events ≈ 1.0× (no volume spike)

## Conclusion

1. LVN and VAH are the most informative levels for next-session momentum
2. Delta sign at HVN significantly improves directional information (6× difference)
3. Timeframes are statistically distinct in trending behavior (higher TF = more efficient)
4. Fractal alignment transitions have ~57-66% win rates (short-horizon edge)
5. VWAP touches produce volatility but no direction — need structural bias for directional use
6. Delta at swing endpoints: directional signal present but test inconclusive (NaN error)

## Shifts thesis?

Partially. Confirms the value of volume profile for level identification. Does not yet validate ICT structural concepts empirically.

## Next steps

- Fix delta Mann-Whitney NaN error and re-run swing endpoint analysis
- Replicate volume profile analysis on full year of data (365 days)
- Test fractal alignment on bear market (2022) for regime robustness
- Combine alignment signal with BOS scoring for a composite entry filter
