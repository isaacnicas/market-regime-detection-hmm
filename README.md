# HMM Market Regime Classifier & Risk Overlay — SPY

**A production-minded quantitative system that detects market regimes in real time and applies a probability-weighted risk overlay for better drawdown control.**

### Live Portfolio Page
**[View Interactive Showcase →](https://isaacnicas.github.io/market-regime-detection-hmm/)**

### Overview

This project implements a **Hidden Markov Model (HMM)** to classify SPY into four market regimes (Bull, Bear, Sideways, High Volatility). The final version uses the model as a **risk overlay** — modulating equity exposure based on regime probabilities, volatility targeting, and realistic costs.

### Key Features
- Gaussian HMM with 4 regimes + probability outputs
- Macro features: VIX, 10Y-2Y yield spread, 200-day momentum
- Walk-forward retraining (5-year window, retrain every 3 months)
- Volatility targeting + 5bps transaction costs
- Risk overlay strategy (soft classification)

### Results (Walk-Forward)

| Strategy                    | Total Return | Sharpe | Max Drawdown | Ann. Volatility |
|-----------------------------|--------------|--------|--------------|-----------------|
| Buy & Hold                  | +565.01%     | 0.77   | -35.75%      | 17.21%          |
| **Walk-Forward Risk Overlay** | **-3.25%** | **-1.25** | **-4.92%** | **4.62%** |

**Key takeaway**: Excellent drawdown protection at the expense of return — a deliberate conservative risk management approach.

### Technologies
Python · yfinance · hmmlearn · scikit-learn · pandas · Chart.js

### Repository Structure
- `index.html` → Beautiful portfolio showcase (GitHub Pages)
- `notebooks/` → Analysis and backtesting
- Full code and data pipeline available
