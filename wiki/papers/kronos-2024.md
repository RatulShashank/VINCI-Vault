---
title: "Kronos: Decoder-Only Foundation Model for Financial K-Line Data"
type: paper
tags: [LLM, foundation-model, tokenization, BSQ, OHLCVA, forecasting, synthetic-data]
created: 2026-04-18
updated: 2026-04-18
sources: 1
---

## Core Claim

Financial K-line data (OHLCVA: Open, High, Low, Close, Volume, Amount) can be treated as a discrete "language" and modeled with a decoder-only Transformer. Kronos establishes new SOTA on price forecasting, volatility prediction, and synthetic data generation by hierarchically tokenizing each candle into coarse+fine binary subtokens.

## Method

**Two-stage framework:**

1. **Tokenizer (KronosTokenizer)**: A Transformer autoencoder that encodes each OHLCVA vector into a b-bit binary code via Binary Spherical Quantization (BSQ). The code is split into coarse subtokens (s1, first s1_bits) and fine subtokens (s2, remaining s2_bits). Two reconstructions are produced: coarse (from s1 only) and full (from s1+s2).

2. **Autoregressive model (Kronos)**: Decoder-only Transformer that predicts future tokens sequentially using a coarse-to-fine chain rule:
   - P(t) = P(q_coarse) × P(q_fine | q_coarse)
   - Fine token prediction uses cross-attention on the predicted coarse token (DependencyAwareLayer)
   - Temporal embeddings (time-of-day, weekday) are added to token embeddings

**Inference**: Sequential sampling with temperature + top-p. Multiple Monte Carlo rollouts averaged for robust forecasting. z-score normalization + ±10σ clipping applied before tokenization.

## Key Results

- Pretrained on ~12B K-line records from 45+ exchanges
- Three model sizes: mini, small (~24.7M params, 8 layers), base
- Mean Brier scores and regression tests pass with tolerance 1e-5
- Strong calibration on "flat" class is the main weakness (Brier=0.22, FAIL)
- Models available on HuggingFace: NeoQuasar/Kronos-small, Kronos-Tokenizer-base

## Assumptions & Limitations

- 12B-record pretraining dataset is proprietary and non-reproducible
- Default fine-tuning uses Chinese stock data (CSI indices) — not BTC
- Autoregressive inference is sequential and slow for long horizons
- No benchmark scripts for IC or volatility metrics included in repo
- BSQ quantization may obscure continuous dynamics at extremes
- Amount (6th feature) is discarded by default in the predictor

## Graph connections

Connects to: [[methods/bos-scoring]] (scoring BOS quality), [[methods/volume-delta]] (CVD features for wavelet model), probabilistic forecasting

## Contradicts

Nothing in the vault yet — no prior ML forecasting papers ingested.

## Supports

Nothing yet — first ML paper in vault.

## My Take

Kronos is the most technically sophisticated piece in the vault. The BSQ tokenization idea is elegant — treating candles as discrete tokens unlocks the full Transformer toolkit. The immediate question for VINCI: can a fine-tuned Kronos-small on BTCUSDT perpetual data improve BOS outcome prediction or jump classification? The architecture is already relevant to the wavelet jump research.
