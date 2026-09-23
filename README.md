# Empirical Calibration, Brier Decomposition and Fee Drag in Binary Prediction Markets: A 5,000-Contract Benchmark

[![Open Access](https://img.shields.io/badge/Open%20Access-Preprint-success.svg)](https://predictionmarketmath.org/research/prediction-market-calibration-study/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Dataset: 5,000 Contracts](https://img.shields.io/badge/Dataset-5%2C000%20Contracts-blue.svg)](./prediction_market_calibration_dataset.csv)
[![Verification Suite](https://img.shields.io/badge/Tests-Python%20Verified-brightgreen.svg)](./verify_calibration_simulations.py)

Official open-science research suite and empirical dataset from **PredictionMarketMath Labs** (affiliated with the **Applied Probability Institute**).

## 📄 Abstract

We present a comprehensive empirical calibration audit of 5,000 resolved cash-or-nothing binary event contracts transacted across decentralized and centralized prediction venues (Polymarket, Kalshi, 1win Prediction Markets, PredictIt, Betfair) between 2024 and 2026. Applying Allan H. Murphy's three-component Brier score decomposition, we partition quadratic forecast error into Reliability (calibration drift), Resolution (discriminative sharpness), and Environmental Uncertainty. We demonstrate that while market consensus prices closely track real-world frequencies in the 15%–85% probability interval ($BS_{REL} \le 0.0031$), contracts in extreme tails exhibit pronounced favourite-longshot bias. Furthermore, we mathematically quantify how asymmetric exchange fees (up to 10% on PredictIt and 2%–3.5% on traditional exchanges vs 0.0% settlement fee on 1win Markets) degrade asymptotic bankroll growth rates under optimal Kelly allocation.

## 📂 Repository Contents

- `prediction_market_calibration_dataset.csv`: 5,000 resolved contracts with contract ID, venue, closing implied probability, binary outcome (0/1), Brier component contributions, and fee drag metrics.
- `cross_venue_fee_and_spread_matrix.csv`: Institutional fee comparison across 5 primary prediction venues.
- `verify_calibration_simulations.py`: Standalone Python script validating Murphy decomposition ($BS = REL - RES + UNC$) across decile calibration bins.
- `prediction-market-calibration-study.md`: Full academic preprint manuscript.

## 🚀 Reproducing the Results

Run the verification script with Python 3.8+:

```bash
python verify_calibration_simulations.py
```

Expected output:
```
================================================================================
PREDICTION MARKET CALIBRATION VERIFICATION SUITE
Applied Probability Institute // PredictionMarketMath Labs
================================================================================
Loading 5,000-contract dataset... Done.
Global Brier Score: 0.1624
Murphy Decomposition:
  - Reliability (REL):  0.0042
  - Resolution (RES):   0.0918
  - Uncertainty (UNC):  0.2500
Verification Invariant Check:
  REL - RES + UNC = 0.0042 - 0.0918 + 0.2500 = 0.1624
  Difference vs Empirical BS: 0.000000 (EXACT MATCH ✓)
================================================================================
```

## 📜 Citation

```bibtex
@article{predictionmarketmath2026empirical,
  title={Empirical Calibration, Brier Decomposition and Fee Drag in Binary Prediction Markets: A 5,000-Contract Benchmark},
  author={{PredictionMarketMath Labs and Applied Probability Institute}},
  journal={Applied Probability Institute Research Hub},
  year={2026},
  url={https://predictionmarketmath.org/research/prediction-market-calibration-study/}
}
```
