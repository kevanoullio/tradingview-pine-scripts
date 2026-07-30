# tradingview-pine-scripts
A curated collection of open-source Pine Script indicators, strategies, and libraries for TradingView all written by @KevanoTrades. Licensed under MPL 2.0.

---

# Pine Script Collection

[![License: MPL 2.0](https://img.shields.io/badge/License-MPL_2.0-blue.svg)](https://opensource.org/licenses/MPL-2.0)
[![TradingView](https://img.shields.io/badge/Platform-TradingView-blue?logo=tradingview)](https://www.tradingview.com/)

A modular collection of custom indicators, backtesting strategies, and reusable helper libraries written in **Pine Script** for TradingView.

## 📂 Repository Structure

```text
├── indicators/       # Custom charting indicators & signals
├── strategies/       # Backtestable quantitative trading strategies
├── libraries/        # Exportable helper modules for Pine Script
├── LICENSE           # Mozilla Public License 2.0
└── README.md

```

## 🚀 How to Use

### 1. Indicators & Strategies

1. Navigate to the `indicators/` or `strategies/` directory.
2. Open the desired `.pine` file and copy the raw source code.
3. Open **TradingView** in your browser or desktop app.
4. Click on the **Pine Editor** tab at the bottom of the chart.
5. Paste the code into the editor and click **Add to Chart**.

### 2. Importing Libraries

If using scripts from `libraries/`, you can import them into your own Pine Script code.
<br>The following is an example for a library called "LibraryName" and using v1:

```pinescript
//@version=6
import KevanoTrades/LibraryName/1 as lib
```

## 📜 License & Compliance

This repository is licensed under the **Mozilla Public License 2.0 (MPL 2.0)**.

* You are free to use, modify, and distribute these scripts.
* Modifications to existing files must remain open-source under MPL 2.0.
* Original author headers (`// © KevanoTrades`) must be preserved in all derived files.

See the [LICENSE](https://www.google.com/search?q=./LICENSE) file for full details.
