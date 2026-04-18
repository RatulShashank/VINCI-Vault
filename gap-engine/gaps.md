# VINCI Gap Register

Last updated: 2026-04-18
Source: Initial vault build (no graphify-out/GRAPH_REPORT.md yet — graphify not run)

---

## Disconnected clusters

### ICT structure cluster ↔ Empirical validation cluster
**Gap**: The ICT concepts (BOS, FVG, OB, liquidity, market maker model) are richly described in Notion exports but have almost zero empirical validation. The experimental cluster (volume profile, BOS scoring, wavelet) tests related ideas but does not directly validate the core ICT mechanisms.
**Bridge needed**: A formal backtest of the liquidity grab → BOS → FVG fill → continuation sequence on BTCUSDT.

### Wavelet/ML cluster ↔ ICT structure cluster
**Gap**: The wavelet jump model (Kronos, HMM, LightGBM) and the ICT market structure concepts live in completely separate conceptual spaces. No feature in the wavelet model references swing levels, BOS, or FVG. No paper or experiment links jump classification to structural events.
**Bridge needed**: Design an experiment testing whether jumps that coincide with ICT BOS events have different classification profiles than random jumps.

### AMT (Auction Market Theory) cluster ↔ Everything
**Gap**: Three AMT-related PDFs are in raw/papers/ but completely unread. AMT is a different theoretical framework from ICT and may support or contradict the structural concepts. Zero connections to anything in the wiki.
**Bridge needed**: Read the AMT papers and create wiki/concepts/auction-market-theory.md.

---

## Weak clusters

### Volume profile cluster (< 3 source papers)
- Only 1 experiment (31 sessions, January 2020) with no academic paper backing
- Delta profile result inconclusive (NaN bug)
- No testing on bear market or multi-month data

### VWAP cluster (< 3 source papers)
- Only 1 experiment, directional character not established
- No academic paper on VWAP in raw/papers/

### BOS scoring cluster (tiny sample)
- 37 BOS events, 3 genuine — cannot draw robust conclusions
- No second instrument tested
- No aggTrades data at BOS bars

---

## Contradiction gaps

None formally identified yet. Potential contradictions not yet filed:
- ICT claims wick BOS can be real → experiment shows 0% genuine rate (supports, not contradicts)
- ICT emphasizes session timing → no empirical test run

---

## Thesis gaps

Beliefs in thesis.md with no supporting experiments:
1. **First-move directionality**: "The direction broken first determines the final direction" — core ICT claim, zero empirical evidence → [[questions/first-move-directionality]]
2. **OB mitigation as entry**: Claimed to produce high-quality entries — never tested
3. **ICT session timing** (Asian → London → NY sequence): Never tested
4. **FVG within displacement range only**: Filtering claim never quantified

---

## Suggested next sources (3–5 papers)

1. **"Order Flow and Asset Prices"** — academic treatment of how order flow imbalance predicts short-term returns (bridges delta cluster to structure cluster)
2. **AMT papers** — already in raw/papers/, just unread: read Auction Market Theory (AMT) and Trading Executive Summary.pdf
3. **"Intraday Patterns in Cryptocurrency Markets"** — session timing effects (Asian/London/NY) — validates ICT session claims
4. **Wavelet scattering for finance** — theoretical foundation for the jump model (links wavelet cluster to academic literature)
5. **Kronos paper** (arXiv 2412.20138v7 — already in raw/papers/) — unread, read the actual paper not just the deep research summary
