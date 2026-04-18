# Cluster Analysis

Last updated: 2026-04-18
Source: Graphify run on quant-research/ — 425 nodes, 585 edges, 41 communities detected

---

## God nodes

Concepts with the highest degree centrality (most connected across the graph):

1. **VINCI Wiki Master Index** (degree 13) — catalog hub; connects to every wiki section
2. **Break of Structure (BOS)** (degree 13) — appears across concepts, experiments, scoring, charts, and strategies
3. **Wavelet Jump Classification — BTCUSDT 2022–2025** (degree 12) — most technically mature experiment; connects to Kronos + ICT
4. **VINCI Quant Research Vault (AGENTS.md)** (degree 11) — system configuration hub
5. **VINCI Thesis** (degree 11) — connects beliefs to evidence across all clusters
6. **Liquidity (BSL/SSL/ERL/IRL)** (degree 10) — appears in strategies, concepts, charts, and observations
7. **BOS Scoring — BTCUSDT Daily 2021** (degree 10) — experimental hub connecting methods to insights
8. **Market Observation — BTCUSDT January 2020** (degree 10) — empirical hub for volume/VWAP/fractal results
9. **Market Structure (Major Swing Sequence)** (degree 9) — foundational ICT concept
10. **ICT Market Structure Community** (degree 9) — cluster self-reference node

---

## Bridge nodes

Surprising cross-community connections discovered by graphify:

1. **Z-Score Normalization (Kronos) ↔ Volume Profile (LVN/HVN)** — Kronos preprocessing (±10σ clipping) is semantically similar to the distribution-based HVN/LVN detection logic. Both normalize price-volume distributions. Bridge: Kronos ML cluster → Volume cluster.

2. **Hierarchical Discrete Tokens ↔ HTF-to-LTF Hierarchy** — Kronos coarse+fine subtoken architecture mirrors the ICT HTF bias → LTF entry hierarchy. Bridge: ML cluster → ICT market structure cluster.

3. **BOS Scoring Pipeline** (hyperedge) — `bos-scoring` method → `bos-score-1d-2021` experiment → `close-type-predicts-bos-quality` insight: a fully validated chain.

4. **Wavelet Jump Stack** (hyperedge) — HMM Regime + Wavelet CWT Features + LightGBM form a complete classification pipeline, currently isolated from ICT cluster.

5. **ICT Price Delivery Mechanism** (hyperedge) — Displacement creates BOS and FVG, then rebalances via OB/FVG: a 4-node structural sequence spanning concepts cluster.

---

## Isolates

Concepts present in vault but not yet connected to anything:

1. **Wickless Scalp Strategy** — 2 notebooks in codes/final/, not yet ingested
2. **BTC Macro Correlation** — 2 notebooks in codes/final/, not yet ingested
3. **AMT (Auction Market Theory)** — 3 PDFs in raw/papers/, unreadable (file size exceeds LLM context limit)
4. **Research Pipeline** (01_research_pipeline_final.ipynb) — unread
5. **PDF papers** (7 total: arXiv wavelet, Kronos arXiv, pnas, AMT) — PDF extraction failed in current environment; alternative approach needed

---

## Community map

### Cluster 1: ICT Strategy & Gap Engine (50 nodes, community 0)
Core: BOS → FVG within Displacement → OB → Continuation; ERL/IRL cycle; session timing; gap engine protocols
Status: **Rich in description (Notion exports), weak in empirical validation**

### Cluster 2: ICT Market Structure (45 nodes, community 1)
Core: BOS, FVG, Displacement, Swing Levels, Liquidity, Market Structure, Fractal Alignment
Status: **Conceptually complete; needs cross-links to empirical cluster**

### Cluster 3: BOS Scoring Empirical (45 nodes, community 2)
Core: body_score, close_type, range_score, vol_score, threshold 0.60, BTCUSDT 2021 data
Status: **Good framework, thin sample (37 events, 3 genuine)**

### Cluster 4: Chart Pattern Library (~150 nodes, communities 3–22)
Core: 18 ICT-annotated trading chart images; concepts visually confirmed (OB, BOS, FVG, liquidity sweep, displacement)
Status: **Visual evidence layer — not yet cross-linked to quantitative experiments**

### Cluster 5: VINCI Research System (14 nodes, community 8)
Core: research loop, wiki protocols, graphify, gap engine, ingest/output-notes protocols
Status: **Infrastructure cluster — connects everything but is not itself validated**

### Cluster 6: Kronos ML Model (12 nodes, community 16)
Core: BSQ tokenizer, decoder-only transformer, hierarchical tokens, KronosPredictor
Status: **Technically mature, disconnected from ICT cluster — bridge opportunity via token hierarchy ↔ HTF/LTF**

### Cluster 7: Wavelet Jump Classification
Spans: Community 1 (god node), Community 16 (Kronos connection)
Core: HMM regime, CWT features, LightGBM, isotonic calibration, Brier scores
Status: **Validated model; no ICT feature integration yet**

### Disconnected: AMT Theory
No community yet. All PDFs unreadable. Zero connections to wiki.
