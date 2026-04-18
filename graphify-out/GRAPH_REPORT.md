# Graph Report - .  (2026-04-18)

## Corpus Check
- 75 files · ~50,608 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 425 nodes · 585 edges · 41 communities detected
- Extraction: 66% EXTRACTED · 32% INFERRED · 1% AMBIGUOUS · INFERRED: 190 edges (avg confidence: 0.81)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_ICT Strategy & Gap Engine|ICT Strategy & Gap Engine]]
- [[_COMMUNITY_ICT Market Structure|ICT Market Structure]]
- [[_COMMUNITY_BOS Scoring & Evidence|BOS Scoring & Evidence]]
- [[_COMMUNITY_Chart Patterns — Consolidation|Chart Patterns — Consolidation]]
- [[_COMMUNITY_Bearish Structure Charts|Bearish Structure Charts]]
- [[_COMMUNITY_Markup & Reversal Patterns|Markup & Reversal Patterns]]
- [[_COMMUNITY_BOS + Impulse Recovery|BOS + Impulse Recovery]]
- [[_COMMUNITY_Bullish Displacement Charts|Bullish Displacement Charts]]
- [[_COMMUNITY_VINCI Research System|VINCI Research System]]
- [[_COMMUNITY_ICT Price Action Charts|ICT Price Action Charts]]
- [[_COMMUNITY_Accumulation & Distribution|Accumulation & Distribution]]
- [[_COMMUNITY_BOS Chart Confirmation|BOS Chart Confirmation]]
- [[_COMMUNITY_Multi-Timeframe BOS|Multi-Timeframe BOS]]
- [[_COMMUNITY_1-2-3 Reversal Pattern|1-2-3 Reversal Pattern]]
- [[_COMMUNITY_ICT Liquidity Sequence|ICT Liquidity Sequence]]
- [[_COMMUNITY_Key Level Setups|Key Level Setups]]
- [[_COMMUNITY_Kronos ML Model|Kronos ML Model]]
- [[_COMMUNITY_SupportResistance Charts|Support/Resistance Charts]]
- [[_COMMUNITY_Bearish Trend Charts|Bearish Trend Charts]]
- [[_COMMUNITY_BTC Order Block Charts|BTC Order Block Charts]]
- [[_COMMUNITY_Raw Price Action Charts|Raw Price Action Charts]]
- [[_COMMUNITY_Session Boundary Charts|Session Boundary Charts]]
- [[_COMMUNITY_BOS Balancing Zone|BOS Balancing Zone]]
- [[_COMMUNITY_EMA Trend Signal|EMA Trend Signal]]
- [[_COMMUNITY_Wickless Scalp Strategy|Wickless Scalp Strategy]]
- [[_COMMUNITY_BTC Macro Correlation|BTC Macro Correlation]]
- [[_COMMUNITY_Quantitative Structure|Quantitative Structure]]
- [[_COMMUNITY_Volume Profile Gap|Volume Profile Gap]]
- [[_COMMUNITY_VWAP Gap|VWAP Gap]]
- [[_COMMUNITY_BOS Scoring Gap|BOS Scoring Gap]]
- [[_COMMUNITY_OB Mitigation Thesis Gap|OB Mitigation Thesis Gap]]
- [[_COMMUNITY_Swing Symmetry Observation|Swing Symmetry Observation]]
- [[_COMMUNITY_W-Pattern Market Structure|W-Pattern Market Structure]]
- [[_COMMUNITY_Hammer Candle Order Block|Hammer Candle Order Block]]
- [[_COMMUNITY_Premium & Discount Zones|Premium & Discount Zones]]
- [[_COMMUNITY_Range BOS Rule|Range BOS Rule]]
- [[_COMMUNITY_Liquidity Sweep Rule|Liquidity Sweep Rule]]
- [[_COMMUNITY_Experiment Template|Experiment Template]]
- [[_COMMUNITY_BTCUSDT 2021 Dataset|BTCUSDT 2021 Dataset]]
- [[_COMMUNITY_Insight Template|Insight Template]]
- [[_COMMUNITY_Question Template|Question Template]]

## God Nodes (most connected - your core abstractions)
1. `VINCI Wiki Master Index` - 13 edges
2. `Break of Structure (BOS)` - 13 edges
3. `Wavelet Jump Classification — BTCUSDT 2022–2025` - 12 edges
4. `VINCI Quant Research Vault (AGENTS.md)` - 11 edges
5. `VINCI Thesis — Core Beliefs and Evidence` - 11 edges
6. `Liquidity (Buy-Side / Sell-Side / ERL / IRL)` - 10 edges
7. `BOS Scoring — BTCUSDT Daily 2021` - 10 edges
8. `Market Observation — BTCUSDT January 2020` - 10 edges
9. `Cluster 1: ICT Market Structure (10 pages)` - 9 edges
10. `Market Structure (Major Swing Sequence Defines Trend)` - 9 edges

## Surprising Connections (you probably didn't know these)
- `Z-Score Normalization and ±10σ Clipping (Data Preprocessing)` --semantically_similar_to--> `Volume Profile (POC, VAH, VAL, HVN, LVN)`  [INFERRED] [semantically similar]
  raw/papers/deep-research-report.md → wiki/concepts/volume-profile.md
- `Hierarchical Discrete Token (Coarse + Fine Subtokens)` --semantically_similar_to--> `HTF-to-LTF Hierarchy (Higher Timeframe Bias, Lower Timeframe Entry)`  [INFERRED] [semantically similar]
  raw/papers/deep-research-report.md → wiki/concepts/market-structure.md
- `Gap Engine Protocol` --references--> `Gap: ICT Structure Cluster vs Empirical Validation Cluster (Disconnected)`  [INFERRED]
  AGENTS.md → gap-engine/gaps.md
- `Gap Engine Protocol` --references--> `Gap: AMT Cluster vs Everything (Disconnected)`  [INFERRED]
  AGENTS.md → gap-engine/gaps.md
- `VINCI Quant Research Vault (AGENTS.md)` --references--> `VINCI Quant Research Vault (CLAUDE.md)`  [EXTRACTED]
  AGENTS.md → CLAUDE.md

## Hyperedges (group relationships)
- **ICT Core Trade Sequence: BOS + FVG (within Displacement) + OB = Entry** — cluster_god_node_bos, cluster_god_node_fvg, rebalancing_ob_definition, cluster_bridge_displacement [EXTRACTED 1.00]
- **Gap Pattern: ICT Structure + No Experiment + No Backtest = Disconnected Cluster Gap** — cluster_community_ict_structure, gaps_disconnected_ict_empirical, gaps_thesis_first_move_directionality [EXTRACTED 0.95]
- **Research Pipeline: Gap Engine Protocol → Question to Insight → Insight to Experiment** — agents_gap_engine_protocol, agents_question_insight_protocol, agents_insight_experiment_protocol [EXTRACTED 1.00]
- **ICT Price Delivery Mechanism: Displacement creates BOS and FVG, then rebalances via OB/FVG** — concept_displacement, concept_bos, concept_fvg, concept_order_block [EXTRACTED 0.95]
- **Kronos Tokenization Pipeline: OHLCVA → BSQ → Hierarchical Coarse+Fine Tokens** — deep_research_report_ohlcva, deep_research_report_bsq, deep_research_report_hierarchical_token, deep_research_report_kronos_tokenizer [EXTRACTED 1.00]
- **Multi-Timeframe Structural Bias: Market Structure + Fractal Alignment + Session Timing** — concept_market_structure, concept_fractal_structure, concept_market_structure_session_timing [INFERRED 0.80]
- **BOS Scoring Validation Pipeline: Method → Experiment → Insight** — method_bos_scoring, bos_score_1d_2021_experiment, insight_close_type_bos [EXTRACTED 0.95]
- **Wavelet Jump Model Stack: HMM Regime + Wavelet Features + LightGBM** — wavelet_jump_hmm, wavelet_jump_lightgbm, wavelet_jump_experiment [EXTRACTED 1.00]
- **ICT Structural Concepts: Liquidity + BOS + FVG Form the Setup Framework** — concept_liquidity, concept_bos, concept_fair_value_gap [EXTRACTED 0.95]

## Communities

### Community 0 - "ICT Strategy & Gap Engine"
Cohesion: 0.06
Nodes (50): Gap Engine Protocol, Rationale: Gaps are Where Edge is Born — underdeveloped cluster = research opportunity, Core Strategy: BOS → Return to FVG within Displacement Range → OB → Continuation, Hypothesis: BOS Level Marks Extent of Retracement / Stop Hunt Zone, Concept: ERL to IRL to ERL Market Delivery, Rule: Not All FVGs Equal — Low-Wick FVG Signals Momentum Distribution, BackTest Journal, Rule: Major Swing Levels (Body-Based) vs Minor Swing Levels (+42 more)

### Community 1 - "ICT Market Structure"
Cohesion: 0.09
Nodes (45): Break of Structure (BOS), BOS Close Type (Wick / Close-Beyond / Full-Body), BOS Quality Scoring System (body_score, range_score, vol_score), Displacement (ICT Displacement Range), Rationale: Displacement Range as FVG/OB Quality Filter, ERL → IRL → ERL Cycle, Fair Value Gap (FVG), Fractal Alignment Transition Event (All-TF EMA Consensus Moment) (+37 more)

### Community 2 - "BOS Scoring & Evidence"
Cohesion: 0.06
Nodes (45): Body Score (BOS Component), Close Type Bonus (BOS Score), BOS Scoring — BTCUSDT Daily 2021, Notebook: swing_structure_bos_result_1D, Rationale: F1 Optimization for Threshold Selection, BOS Score Optimal Threshold 0.60, Close Type Is Dominant Predictor of BOS Quality, Mechanism: Wick Rejection Signals Immediate Absorption (+37 more)

### Community 3 - "Chart Patterns — Consolidation"
Cohesion: 0.14
Nodes (20): Break of Structure (BOS), Candlestick Price Chart, Consolidation / Ranging Zone, Dashed Rectangle Zone (Liquidity Pool or OB), Distribution Zone (Post-Rally Selloff), Downswing / Bearish Market Structure, Fair Value Gap (FVG), Fair Value Gap or Order Block (Left White Box) (+12 more)

### Community 4 - "Bearish Structure Charts"
Cohesion: 0.18
Nodes (16): Break of Structure (BOS), Candlestick Price Chart, Dashed Horizontal Reference Line (Equilibrium / Mid-Level), Bearish Downtrend Market Structure, Horizontal Price Levels (Key Levels), ICT Killzone (Session Timing), Liquidity Pools / Resting Liquidity, Lower High Lower Low (LH-LL) Pattern (+8 more)

### Community 5 - "Markup & Reversal Patterns"
Cohesion: 0.22
Nodes (15): Bearish Rejection / Price Reversal at High, Bullish Rally / Markup Phase, Candlestick Price Chart, Dashed White Horizontal Line (Equilibrium / 50% Level), Initial Downtrend Phase, Fair Value Gap (FVG), Grey Shaded Rectangle Zone (Fair Value Gap or Order Block), Horizontal Blue Solid Line (Key Support/Resistance Level) (+7 more)

### Community 6 - "BOS + Impulse Recovery"
Cohesion: 0.19
Nodes (15): Bearish Correction / Retracement Phase, Break of Structure (BOS), Bullish Impulse Move, Bullish Recovery After Correction, Candlestick Price Action Chart, Dark Theme TradingView-Style Chart, ICT Killzone Session Boundary, Liquidity Sweep / Stop Hunt (Implied by Impulse then Reversal) (+7 more)

### Community 7 - "Bullish Displacement Charts"
Cohesion: 0.19
Nodes (15): Initial Bearish Downtrend Leg, Blue Pin Marker at Top (Target / POI Reached), Break of Structure (BOS), Bullish Displacement / Strong Rally, Candlestick Price Chart, Dashed Horizontal Mid-Level, Key Horizontal Level (Blue Line), Annotated Level Label '1' (+7 more)

### Community 8 - "VINCI Research System"
Cohesion: 0.18
Nodes (14): Code Ingest Protocol (codes/final/), Research Core Loop: Raw Data → Wiki → Graph → Gap Detection → Questions → Insights → Experiments → Thesis, Graphify Tool, Insight to Experiment Protocol, Lint Protocol (Weekly Wiki Self-Heal), Paper Ingest Protocol, Question to Insight Protocol, Rationale: Contradictions are Signal — never smooth over conflicts, file in wiki/contradictions/ (+6 more)

### Community 9 - "ICT Price Action Charts"
Cohesion: 0.22
Nodes (14): Bearish Candles (Red), Bullish Candles (Green), Candlestick Price Action Chart, ICT (Inner Circle Trader) Concepts, Key Price Level (Horizontal Blue Line), Liquidity Pool Above Swing Highs (Dashed White Rectangle), Liquidity Sweep / Stop Hunt Above Swing Highs, Market Structure Retracement Into Order Block (+6 more)

### Community 10 - "Accumulation & Distribution"
Cohesion: 0.24
Nodes (14): Bearish Distribution Zone (Red Shaded), Break of Structure (Bullish BOS), Bullish Accumulation Zone (Green Shaded), Candlestick Price Chart, Key Price Levels (Dotted Horizontal Lines), Equal Highs (EQH) Liquidity Pool, Equal Lows (EQL) Liquidity Pool, Liquidity Sweep (+6 more)

### Community 11 - "BOS Chart Confirmation"
Cohesion: 0.19
Nodes (14): Bearish Candles (Red), Break of Structure (BOS) — Bullish, Bullish Candles (Teal/Green), Candlestick Price Chart, Pre-Drop Consolidation / Distribution, Downtrend Leg (Bearish Swing), Horizontal Support / Liquidity Level, Liquidity Sweep / Stop Hunt (+6 more)

### Community 12 - "Multi-Timeframe BOS"
Cohesion: 0.2
Nodes (14): 4-Hour Timeframe Context, Break of Structure (4H Timeframe), Bullish Reversal After BOS, Candlestick Price Chart, Initial Downtrend Phase, Liquidity Levels (Horizontal Lines), Market Structure Analysis, Mid-chart Support Level (Right) (+6 more)

### Community 13 - "1-2-3 Reversal Pattern"
Cohesion: 0.26
Nodes (13): 1-2-3 Reversal Pattern, Bearish (Red) Candlesticks, Blue Dashed Horizontal Support/Resistance Line, Bullish (Green) Candlesticks, Candlestick Trading Chart, Downtrend Price Action, Partial Recovery / Bounce After Lows, Point 1 - Prior Swing High / Trend Start (+5 more)

### Community 14 - "ICT Liquidity Sequence"
Cohesion: 0.24
Nodes (13): Break of Structure (BOS), Candlestick Price Chart, Displacement / Impulse Move (Large Bearish Candle), ICT (Inner Circle Trader) Market Structure Concepts, Liquidity Grab Below Swing Low, Market Structure Reversal (Downtrend to Uptrend), Order Block / Demand Zone Point 3, Premium / Resistance Zone (Dashed Top Boundary) (+5 more)

### Community 15 - "Key Level Setups"
Cohesion: 0.23
Nodes (13): Blue Horizontal Key Level (Support/Resistance Line), Candlestick Price Chart, Dashed Horizontal Arrow (Price Direction Projection), Dashed Vertical Line (Significant Time or Price Event Marker), Demand Zone / Order Block (Brown Shaded Region, Label 3), Liquidity Sweep Below Key Level, Market Structure Shift (Rally then Breakdown), Order Block (Institutional Accumulation Zone) (+5 more)

### Community 16 - "Kronos ML Model"
Cohesion: 0.23
Nodes (12): Kronos Decoder-Only Autoregressive Transformer, Binary Spherical Quantization (BSQ), DependencyAwareLayer — Cross-Attention Coarse-to-Fine, Hierarchical Discrete Token (Coarse + Fine Subtokens), Kronos Foundation Model — Deep Research Report, KronosPredictor — Inference Wrapper, KronosTokenizer — Transformer Autoencoder for K-line Tokenization, Monte Carlo Forecasting with Sample Count (+4 more)

### Community 17 - "Support/Resistance Charts"
Cohesion: 0.23
Nodes (12): Bearish Candles (Red), Bullish Candles (Green), Candlestick Price Action Chart, Dashed Horizontal Level (Support/Key Level), Dotted Horizontal Level (Resistance/Key Level), Double Top / Double Rejection Pattern, Liquidity Sweep at Highs, Market Structure Shift (Bearish) (+4 more)

### Community 18 - "Bearish Trend Charts"
Cohesion: 0.23
Nodes (12): Bearish Continuation Move (Right Section), Initial Bearish Impulse Move (Left Section), Bearish Trend / Downtrend Price Action, Break of Structure (BOS) Bearish, Candlestick Price Chart (Bearish Trend), Mid-Chart Consolidation / Dealing Range Between Sessions, Price Displacement / Delivery (ICT Model), Liquidity Sweep / Wick Rejections (+4 more)

### Community 19 - "BTC Order Block Charts"
Cohesion: 0.24
Nodes (12): Bearish Continuation / Break Down, Binance BTC Candlestick Chart, Break of Structure (BOS), Bullish Order Block, Price Consolidation / Ranging Zone, Descending Bearish Trendline, Equilibrium (50% Fibonacci Level), Fair Value Gap (FVG) (+4 more)

### Community 20 - "Raw Price Action Charts"
Cohesion: 0.25
Nodes (11): Bearish Candles (Red), Bullish Candles (Green), Candlestick Price Chart, Dark-Theme Chart Interface, ICT Time-Based Entry Concept, Potential Liquidity Sweep / Stop Hunt, Post-Marker Price Structure (Right of Dashed Line), Pre-Marker Price Structure (Left of Dashed Line) (+3 more)

### Community 21 - "Session Boundary Charts"
Cohesion: 0.28
Nodes (9): Bearish Candles (Red), Blue Dashed Vertical Line (Key Level / Session Boundary), Bullish Candles (Teal/Green), Candlestick Price Chart, Liquidity Level or Equilibrium Marker, Market Structure (Bearish Price Action), Price Delivery (Bearish Sequence Left of Line), Potential Reversal or Continuation Zone (Right of Line) (+1 more)

### Community 22 - "BOS Balancing Zone"
Cohesion: 0.46
Nodes (8): Balancing Above the Leg That BOS, Break of Structure (BOS), Candlestick Price Action, Daily Order Block (Daily OB), Horizontal Price Level (Support Zone), Price Retracement After BOS, Smart Money Concepts (SMC) Framework, Trading Chart with Smart Money Concepts Annotations

### Community 23 - "EMA Trend Signal"
Cohesion: 1.0
Nodes (2): EMA(20) Trend Direction Signal, Rationale: EMA(20) as Simple Proxy for Trend Direction Across TFs

### Community 24 - "Wickless Scalp Strategy"
Cohesion: 1.0
Nodes (1): Isolate: Wickless Scalp Strategy

### Community 25 - "BTC Macro Correlation"
Cohesion: 1.0
Nodes (1): Isolate: BTC Macro Correlation

### Community 26 - "Quantitative Structure"
Cohesion: 1.0
Nodes (1): Cluster 3: Quantitative Structure (3 pages)

### Community 27 - "Volume Profile Gap"
Cohesion: 1.0
Nodes (1): Gap: Volume Profile Cluster Weak (< 3 source papers)

### Community 28 - "VWAP Gap"
Cohesion: 1.0
Nodes (1): Gap: VWAP Cluster Weak (< 3 source papers)

### Community 29 - "BOS Scoring Gap"
Cohesion: 1.0
Nodes (1): Gap: BOS Scoring Cluster Weak (tiny sample, 37 events)

### Community 30 - "OB Mitigation Thesis Gap"
Cohesion: 1.0
Nodes (1): Thesis Gap: OB Mitigation as Entry (never tested)

### Community 31 - "Swing Symmetry Observation"
Cohesion: 1.0
Nodes (1): Observation: Number of swings on left predicts number on right

### Community 32 - "W-Pattern Market Structure"
Cohesion: 1.0
Nodes (1): Observation: W-Type Market Structure After LTF Objective Hit

### Community 33 - "Hammer Candle Order Block"
Cohesion: 1.0
Nodes (1): Observation: Large Hammer Candle as Order Block

### Community 34 - "Premium & Discount Zones"
Cohesion: 1.0
Nodes (1): Concept: Premium and Discount Zones with Fibonacci Range

### Community 35 - "Range BOS Rule"
Cohesion: 1.0
Nodes (1): Rule: Bullish Range = Up then Down; Bearish Range = Down then Up (via BOS)

### Community 36 - "Liquidity Sweep Rule"
Cohesion: 1.0
Nodes (1): Rule: Market Above 50% Level in Bearish Range Sweeps Liquidity Before Dumping

### Community 37 - "Experiment Template"
Cohesion: 1.0
Nodes (1): Experiment Template

### Community 38 - "BTCUSDT 2021 Dataset"
Cohesion: 1.0
Nodes (1): BTCUSDT 1D 2021 Dataset

### Community 39 - "Insight Template"
Cohesion: 1.0
Nodes (1): Insight Template

### Community 40 - "Question Template"
Cohesion: 1.0
Nodes (1): Question Template

## Ambiguous Edges - Review These
- `Isolate: Auction Market Theory (AMT)` → `Cluster 1: ICT Market Structure (10 pages)`  [AMBIGUOUS]
  gap-engine/cluster-analysis.md · relation: conceptually_related_to
- `Liquidity Grab and Dump (BTCUSDT Multi-TF)` → `Temp 1 (BTCUSDT, March 9 2024 — stub note)`  [AMBIGUOUS]
  raw/notion-exports/Temp 1 96c34f712ddc48cbaaed926a5beeb499.md · relation: conceptually_related_to
- `Grey Shaded Rectangle Zone (Fair Value Gap or Order Block)` → `Order Block`  [AMBIGUOUS]
  raw/notion-exports/image 2.png · relation: conceptually_related_to
- `Liquidity Pools / Resting Liquidity` → `Dashed Horizontal Reference Line (Equilibrium / Mid-Level)`  [AMBIGUOUS]
  raw/notion-exports/image 7.png · relation: conceptually_related_to
- `Bullish Impulse Move` → `Liquidity Sweep / Stop Hunt (Implied by Impulse then Reversal)`  [AMBIGUOUS]
  raw/notion-exports/image 9.png · relation: conceptually_related_to
- `Price Action Analysis` → `Potential Liquidity Sweep / Stop Hunt`  [AMBIGUOUS]
  raw/notion-exports/image 14.png · relation: conceptually_related_to
- `Swing Low / Liquidity Pool (Sell-Side)` → `Dashed Horizontal Mid-Level`  [AMBIGUOUS]
  raw/notion-exports/image 16.png · relation: conceptually_related_to

## Knowledge Gaps
- **114 isolated node(s):** `VINCI Quant Research Vault (CLAUDE.md)`, `Source Epistemic Hierarchy`, `Rationale: No Passive Storage — every input must connect, challenge, or extend the wiki`, `Rationale: Thesis is King — every ingest ends with 'does this shift thesis.md?'`, `Rationale: Contradictions are Signal — never smooth over conflicts, file in wiki/contradictions/` (+109 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **Thin community `EMA Trend Signal`** (2 nodes): `EMA(20) Trend Direction Signal`, `Rationale: EMA(20) as Simple Proxy for Trend Direction Across TFs`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Wickless Scalp Strategy`** (1 nodes): `Isolate: Wickless Scalp Strategy`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `BTC Macro Correlation`** (1 nodes): `Isolate: BTC Macro Correlation`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Quantitative Structure`** (1 nodes): `Cluster 3: Quantitative Structure (3 pages)`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Volume Profile Gap`** (1 nodes): `Gap: Volume Profile Cluster Weak (< 3 source papers)`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `VWAP Gap`** (1 nodes): `Gap: VWAP Cluster Weak (< 3 source papers)`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `BOS Scoring Gap`** (1 nodes): `Gap: BOS Scoring Cluster Weak (tiny sample, 37 events)`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `OB Mitigation Thesis Gap`** (1 nodes): `Thesis Gap: OB Mitigation as Entry (never tested)`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Swing Symmetry Observation`** (1 nodes): `Observation: Number of swings on left predicts number on right`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `W-Pattern Market Structure`** (1 nodes): `Observation: W-Type Market Structure After LTF Objective Hit`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Hammer Candle Order Block`** (1 nodes): `Observation: Large Hammer Candle as Order Block`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Premium & Discount Zones`** (1 nodes): `Concept: Premium and Discount Zones with Fibonacci Range`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Range BOS Rule`** (1 nodes): `Rule: Bullish Range = Up then Down; Bearish Range = Down then Up (via BOS)`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Liquidity Sweep Rule`** (1 nodes): `Rule: Market Above 50% Level in Bearish Range Sweeps Liquidity Before Dumping`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Experiment Template`** (1 nodes): `Experiment Template`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `BTCUSDT 2021 Dataset`** (1 nodes): `BTCUSDT 1D 2021 Dataset`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Insight Template`** (1 nodes): `Insight Template`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.
- **Thin community `Question Template`** (1 nodes): `Question Template`
  Too small to be a meaningful cluster - may be noise or needs more connections extracted.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **What is the exact relationship between `Isolate: Auction Market Theory (AMT)` and `Cluster 1: ICT Market Structure (10 pages)`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `Liquidity Grab and Dump (BTCUSDT Multi-TF)` and `Temp 1 (BTCUSDT, March 9 2024 — stub note)`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `Grey Shaded Rectangle Zone (Fair Value Gap or Order Block)` and `Order Block`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `Liquidity Pools / Resting Liquidity` and `Dashed Horizontal Reference Line (Equilibrium / Mid-Level)`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `Bullish Impulse Move` and `Liquidity Sweep / Stop Hunt (Implied by Impulse then Reversal)`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `Price Action Analysis` and `Potential Liquidity Sweep / Stop Hunt`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._
- **What is the exact relationship between `Swing Low / Liquidity Pool (Sell-Side)` and `Dashed Horizontal Mid-Level`?**
  _Edge tagged AMBIGUOUS (relation: conceptually_related_to) - confidence is low._