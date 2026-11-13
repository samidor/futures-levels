# Futures Key Levels

Daily options-based support and resistance levels for major futures contracts.

## Instruments

| Report | Futures | Underlying ETF/Index | Volatility Index |
|--------|---------|---------------------|-----------------|
| **ES** | S&P 500 E-mini | SPY + SPX | VIX |
| **NQ** | Nasdaq 100 E-mini | QQQ + NDX | VXN |
| **CL** | Crude Oil | USO | OVX |
| **GC** | Gold | GLD + GDX | GVZ |

## What Each Report Includes

- **Key Levels** — Support and resistance levels derived from options open interest, filtered statistically (z-score >= 1 SD) and capped within +/-5% of the previous settlement price. Levels are classified as Call Wall, Put Wall, Pivot, Call Support, or Put Resistance based on the call/put OI ratio.

- **0DTE Levels** — Same methodology applied to same-day expiring options, which often drive intraday price action.

- **Standard Deviation Levels** — Both Barchart-sourced SD levels (from the ETF cheat sheet) and IV-based SD levels calculated from the relevant volatility index.

- **Max Pain** — The strike price at which total options pain is minimized, calculated from 0DTE options for each underlying.

- **Dark Pool Prints** — Large off-exchange block trades filtered by minimum premium (ES >= $50M, NQ >= $20M, CL >= $2M, GC >= $1M), converted to equivalent futures prices.

## How Levels Are Calculated

1. Options open interest is fetched from the CBOE delayed quotes API for each ETF and index
2. Strikes are grouped and OI is aggregated across sources (e.g., SPY + SPX for ES)
3. Statistical filtering removes noise: only levels with total OI >= mean + 1 standard deviation are kept
4. ETF/index strikes are converted to futures prices using real-time price ratios and the futures premium over the cash index
5. Levels beyond +/-5% of the previous settlement are excluded

## Data Sources

- **CBOE** — Options open interest (delayed ~15 min)
- **Barchart** — Futures prices, ETF standard deviation levels, volatility indices
- **ChartExchange** — Dark pool prints, index closing prices

## Disclaimer

This information is for educational and informational purposes only. It does not constitute financial advice, investment recommendations, or a solicitation to buy or sell any securities or futures contracts. Trading futures and options involves substantial risk of loss. Past performance is not indicative of future results. Always do your own research and consult a qualified financial advisor before making any trading decisions.
