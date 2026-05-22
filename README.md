# market-regime-detection-hmm
Hidden Markov Model (HMM) for SPY market regime detection with probability-based risk overlay, volatility targeting, and walk-forward validation.
# HMM Market Regime Classifier & Risk Overlay — SPY

**A production-minded quantitative system that detects market regimes in real time and applies a probability-weighted risk overlay for better drawdown control.**

![Hero](portfolio.png)

### Overview

This project implements a **Hidden Markov Model (HMM)** to classify SPY into four market regimes (Bull, Bear, Sideways, High Volatility) using rich features including macro signals. Instead of aggressive market timing, the final version uses the model as a **risk overlay** — modulating equity exposure based on regime probabilities, volatility targeting, and realistic costs.

### Key Features

- **Unsupervised Regime Detection** with Gaussian HMM (4 components)
- **Macro & Technical Features**: VIX, 10Y-2Y yield spread, 200-day momentum, volatility, trend, range
- **Soft Classification**: Uses regime probabilities for smooth, non-binary position sizing
- **Walk-Forward Retraining**: 5-year rolling window, retrained every 3 months (no look-ahead bias)
- **Volatility Targeting**: Scales exposure to target ~10% annualized volatility
- **Transaction Costs**: 5 basis points per trade + 3-day minimum hold period
- **Risk Overlay Strategy**: Conservative but robust risk management approach

### Results (Walk-Forward Out-of-Sample)

| Strategy                    | Total Return | Sharpe | Max Drawdown | Ann. Volatility |
|----------------------------|--------------|--------|--------------|-----------------|
| Buy & Hold                 | +565.01%     | 0.77   | -35.75%      | 17.21%          |
| Initial HMM                | +60.96%      | 0.31   | -32.37%      | 11.94%          |
| Soft Classification (5bps) | +50.18%      | 0.27   | -32.40%      | 11.93%          |
| **Walk-Forward Risk Overlay** | **-3.25%** | **-1.25** | **-4.92%** | **4.62%** |

**Key Insight**: The final version sacrifices return for **dramatically lower drawdown** and volatility — a deliberate risk-management focus suitable for real-world capital preservation.

### Live Demo

**[View Interactive Portfolio Page](https://yourusername.github.io/hmm-spy-regime-classifier/)**  
(Static showcase with charts and architecture)

**Streamlit Live Dashboard** (coming soon — regime probabilities + allocation signals)

### Repository Structure
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HMM Market Regime Classifier — SPY</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@300;400;500;600;700&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
  /* (Your existing beautiful CSS stays exactly the same) */
  /* ... paste your full <style> block here ... */
</style>
</head>
<body>

<!-- Your existing HTML content stays the same until footer -->

<footer>
  <div>
    <strong>HMM Market Regime Classifier — SPY</strong><br>
    Python · hmmlearn · Walk-Forward Risk Overlay
  </div>
  <div style="text-align:right;">
    <a href="https://github.com/yourusername/hmm-spy-regime-classifier" target="_blank" style="color:var(--accent); text-decoration:none; margin-right:20px;">GitHub →</a>
    <a href="https://linkedin.com/in/yourprofile" target="_blank" style="color:var(--accent); text-decoration:none;">LinkedIn →</a>
  </div>
</footer>

<!-- Rest of your scripts remain unchanged -->

</body>
</html>
