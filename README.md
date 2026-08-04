# tradingview-pine-scripts

[![License: MPL 2.0](https://img.shields.io/badge/License-MPL_2.0-blue.svg)](https://opensource.org/licenses/MPL-2.0)
[![TradingView](https://img.shields.io/badge/Platform-TradingView-blue?logo=tradingview)](https://www.tradingview.com/)

# Pine Script Collection

A modular, open-source collection of custom indicators, backtesting strategies, and exportable helper libraries written in **Pine Script** for TradingView by [@KevanoTrades](https://www.tradingview.com/u/KevanoTrades/). Licensed under MPL 2.0.

---

## 📂 Repository Structure

Each script lives in its own dedicated subfolder within its respective category directory. Each subfolder contains the source code, documentation, and a visual example.

```text
tradingview-pine-scripts/
├── indicators/         # Custom indicators & signal overlays
│   |── moving_average_convergence_divergence/
│   |   |── moving_average_convergence_divergence.pine
│   |   |── moving_average_convergence_divergence.md
│   |   |── moving_average_convergence_divergence.png
│   └── *.pine
├── strategies/         # Quantitative backtesting strategies
│   |── relative_strength_index_strategy/
│   |   |── relative_strength_index_strategy.pine
│   |   |── relative_strength_index_strategy.md
│   |   |── relative_strength_index_strategy.png
│   └── *.pine
├── libraries/          # Reusable Pine modules for public import
│   |── ehlers_super_smoother/
│   |   |── ehlers_super_smoother.pine
│   |   |── ehlers_super_smoother.md
│   |   |── ehlers_super_smoother.png
│   └── *.pine
├── LICENSE             # Mozilla Public License 2.0
└── README.md           # Repository index and contributor workflow
```

## 🚀 How to Use

### 1. Indicators & Strategies

1. Navigate to the `indicators/` or `strategies/` directory and enter the desired script's subfolder.
2. Open the `.pine` file and copy the raw source code.
3. Open **TradingView** in your browser or desktop app.
4. Click on the **Pine Editor** tab at the bottom of the chart.
5. Paste the code into the editor and click **Add to Chart**.
6. Refer to the `.md` file in the script's folder for detailed usage instructions and parameter descriptions.
7. View the `.png` file in the same folder for a visual example of the script in action.

### 2. Importing Libraries

To import a public library from `libraries/` into your own scripts, use the `/version` integer string assigned by TradingView. Library updates are backward-compatible because TradingView permanently freezes previous published versions:

```pinescript
//@version=5
import KevanoTrades/Double_Triple_EMA/1 as ema

// Call library function
myDema = ema.dema(close, 14)

```

---

## 🛠️ Development & Versioning Strategy

This monorepo uses a **Single-File + Script-Scoped Tagging** strategy that maps 1:1 onto TradingView's platform architecture.

### 1. Embedded Documentation & Revisions

While header comments remain for TradingView's parser (using `//@description`, `//@function`, `//@param`), the primary documentation, detailed parameter descriptions, and revision history now reside in the accompanying `.md` file within each script's subfolder.

TradingView automatically parses these tags when you copy/paste the code into the Pine Editor to pre-fill public publication pages.

```pinescript
// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © KevanoTrades

//@version=5

// The 2 Pole and 3 Pole Super Smoother Filters were developed by John Ehlers and described in "Chapter 13: Super Smother" of his book "Cybernetic Analysis for Stocks and Futures".
// The 2 Pole Smoother is described as being a better approximation of price, whereas the 3 Pole Smoother has superior smoothing.
// Special thanks to Alex Orekhov (everget) for their excellent open source code for both two and three pole!

// @description Provides the functions to calculate 2 Pole & 3 Pole Ehlers Super Smoother Filters
library("Ehlers_Super_Smoother", true)

// @function Calculates 2 Pole Ehlers Super Smoother Filter
// @param _source -> Open, Close, High, Low, etc ('close' is used if no argument is supplied)
// @param _length -> Ehlers Super Smoother length
// @returns 2 Pole Ehlers Super Smoothing to an input source at the specified input length

// ============================================================================
// REVISION HISTORY
// ============================================================================
// v2: Corrected "Description", no other changes, v2 will work exactly like v1
// v1: Initial public release.
// ============================================================================
```

### 2. Script-Scoped Git Tagging

Since every script in this repository has its own independent lifecycle on TradingView, we do not use global repository tags like `v1.0.0`.

Instead, tags are scoped to the **script name** and the **TradingView published integer version** (`/1`, `/2`, `/3`):

$$\text{Format: } \texttt{<prefix>-<script-name>-v<tradingview-version>}$$

**Tagging Prefix Summary:**
- `ind-`: Indicators
- `str-`: Strategies
- `lib-`: Libraries

#### Example Workflow when Publishing an Update

1. Update script locally and copy it to TradingView's Pine Editor.
2. Click **Publish** $\rightarrow$ **Update Existing** on TradingView (TradingView assigns Version 2).
3. Commit and tag the release locally:

```bash
# 1. Commit the code change to main
git add libraries/ehlers_super_smoother/ehlers_super_smoother.pine
git commit -m "Update ehlers_super_smoother library for TradingView v2 (#v2)"

# 2. Tag using the prefixed script name and TV version number
git tag lib-ehlers_super_smoother-v2

# 3. Push to GitHub
git push origin main
git push origin lib-ehlers_super_smoother-v2

```

#### Inspecting Historical TradingView Versions

To check out or diff the code as it existed when TradingView Version 1 was published:

```bash
# Inspect Version 1
git checkout lib-double-triple-ema-v1

# Compare changes between Version 1 and Version 2 on TV
git diff lib-ehlers_super_smoother-v1 lib-ehlers_super_smoother-v2 libraries/ehlers_super_smoother/ehlers_super_smoother.pine

```

---

## 📜 License & Compliance

This repository is licensed under the **Mozilla Public License 2.0 (MPL 2.0)**.

* You are free to use, modify, and distribute these scripts.
* Modifications to existing files must remain open-source under MPL 2.0.
* Original author headers (`// © KevanoTrades`) must be preserved in all derived files.

See the [LICENSE](https://www.google.com/search?q=./LICENSE) file for full details.
