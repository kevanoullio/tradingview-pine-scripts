# 2-Year Moving Average Multiplier

> **TradingView Script Type:** Indicator
> **Primary Ticker Target:** BTCUSD / Established Liquid Assets
> **TradingView Publication URL:** [https://www.tradingview.com/script/zQdZFK78-2-Year-Moving-Average-Multiplier/]

---

### 📋 TradingView Publication Description (BBCode Source)

*Copy and paste the raw block below directly into TradingView's publication editor:*

```text
[image][https://www.tradingview.com/x/KtAuTcL9/](https://www.tradingview.com/x/KtAuTcL9/)[/image]

2-Year Moving Average Multiplier is a long-term trend and valuation overlay for your chart.

It plots a 2-year (730-day) SMA as a lower band and a multiplier line as an upper band to form a reference channel. Price inside the band is normal. Price above the upper band triggers a red fill (overextended). Price below the lower band triggers a green fill (potentially undervalued).

───────────────────

HOW IT WORKS

Three lines are drawn on your chart:

[list]
[*]Lower Band (green) is a 730-day Simple Moving Average, your long-term baseline.
[*]Upper Band (red) is the lower band times a multiplier, giving you an upper reference.
[*]Midpoint (white, dimmed) sits right between the two bands as a center reference.
[*]Conditional fills highlight when price breaks above or below the band boundaries.
[/list]

───────────────────

INPUTS

Indicator Settings:
[list]
[*]Moving Average Length is the SMA period in bars. 730 equals 2 calendar years.
[*]Moving Average Multiplier sets how far above the SMA the upper band sits.
[*]Source picks the price input for the SMA calculation.
[*]Resolution is the timeframe used for the calculation. Bands stay consistent no matter what chart resolution you view.
[/list]

Plot Options:
[list]
[*]Fill background within moving averages toggles the light blue fill between bands.
[*]Fill above and below ranges toggles the red and green breakout fills.
[*]Plot moving average mid point shows or hides the midpoint line.
[*]Plot daily highs and lows overlays daily high and low lines in blue.
[/list]

───────────────────

HOW TO USE

[list]
[*]Between bands means the asset is in its normal long-term range.
[*]Above upper band (red) means price is potentially overextended. Treat it as a caution signal, not an automatic sell.
[*]Below lower band (green) means price could be undervalued. Treat it as a watch signal, not an automatic buy.
[*]Adjust the multiplier to control sensitivity. Higher values mean fewer breakouts, lower values mean more.
[*]Change the length to adjust the indicator to be longer or shorter than 2 years.
[/list]

───────────────────

NOTES

[list]
[*]The SMA needs 730 bars of history to stabilize. Newer assets or short history will show incomplete values early on.
[*]Works best on liquid, established instruments, most notably on Bitcoin BTCUSD.
[*]Bands are locked to the chosen resolution so they won't shift when you change your chart timeframe.
[/list]

───────────────────

Disclaimer: This indicator is for educational and informational purposes only. It is not financial advice. Trading involves substantial risk of loss and past performance does not guarantee future results. Always do your own research and consult a qualified financial advisor before making investment decisions. The author assumes no liability for any losses incurred.
```
