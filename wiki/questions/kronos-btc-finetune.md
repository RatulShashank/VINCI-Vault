---
title: Can Kronos Fine-Tuned on BTCUSDT Improve Jump Classification?
type: question
tags: [Kronos, foundation-model, jump, wavelet, fine-tuning, OHLCVA]
created: 2026-04-18
gap_source: papers/kronos-2024 — application to BTC perpetuals unexplored
status: open
---

## Gap identified

Kronos is a pretrained foundation model for K-line data trained on 12B records from 45+ exchanges. The wavelet jump model uses hand-crafted CWT features. There is a direct opportunity to use Kronos embeddings (the tokenizer's latent representation) as richer input features for jump classification — but this connection has not been explored.

## Clusters involved

ML model cluster (Kronos, LightGBM) ↔ jump classification cluster (wavelet, HMM). Currently disconnected — two separate modeling approaches with no shared components.

## Why it matters for the thesis

If Kronos embeddings capture structural dynamics better than hand-crafted CWT features, replacing or augmenting the wavelet feature matrix with Kronos latents could improve the jump model's calibration, particularly for the flat class (current weakness: Brier 0.22).

## Research question

Do Kronos-small encoded representations of the 30-bar pre-jump window produce better jump outcome predictions than the current 47-feature CWT/CVD/regime matrix?

## Related concepts

- [[papers/kronos-2024]] — the model
- [[experiments/wavelet-jump-classification]] — current jump model
- [[methods/volume-delta]] — CVD features shared between both

## Leads

**Implementation steps:**
1. Install Kronos from HuggingFace (NeoQuasar/Kronos-small)
2. For each jump event, encode the 30-bar pre-jump OHLCVA window using `KronosTokenizer.encode()`
3. Extract the latent representation before quantization (encoder output)
4. Use these as features instead of (or alongside) the CWT features
5. Retrain LightGBM and compare Brier scores

**Key question:** Is the Kronos tokenizer's codebook trained on global markets applicable to BTCUSDT? Or does it need fine-tuning on BTC data?

**Risk:** Kronos was pretrained on stock data (CSI indices default). BTC crypto dynamics may be out-of-distribution for the pretrained tokenizer.
