# Nifty 50: Quantitative Analysis of Return Behaviour, Volatility Regimes, and Market Seasonality Anomalies (2000–Present)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Tuke6X4ZkmoRXYQK2-pITmmXI8S8lCfa?usp=sharing)
&nbsp;&nbsp;

---
## Project overview

This notebook presents a systematic, multi-layered quantitative study of the **Nifty 50 index**:
India's benchmark large-cap equity index comprising the top 50 companies listed on the National
Stock Exchange (NSE).Using the **25 years(6,520 trading days)** of daily **OHLC** price data
spanning January 2000 to the present, the analysis examines how the index behaves across
different market regimes, risk environments, and calendar periods.
<div align="center"<b>
  <sub>Tech Stack: Python · pandas · NumPy · Plotly · Seaborn · Matplotlib</sub>
</div></b>

---

## Dataset

| Property        | Detail                                              |
|-----------------|-----------------------------------------------------|
| **Source**      | National Stock Exchange of India (NSE)              |
| **File**        | `NIFTY50.csv`                                       |
| **Period**      | January 2000 – Present                              |
| **Records**     | 6,520 trading days                                  |

### Column descriptions

| Column  | Type      | Description                                   |
|---------|-----------|-----------------------------------------------|
| `date`  | `object`  | Trading date in `DD-MM-YYYY` format           |
| `open`  | `float64` | Opening price of the session                  |
| `high`  | `float64` | Intraday high price                           |
| `low`   | `float64` | Intraday low price                            |
| `close` | `float64` | Closing price of the session                  |

---
### Key Analytical Metrics

| section | Analysis | Description |
|-------------|----------|-------------|
| 2.1 | Daily log returns | `ln(Pₜ / Pₜ₋₁)`: foundation for all downstream risk calculations |
| 2.2 | Rolling volatility | 21 day (short term) and 252 day (annual baseline) annualised volatility |
| 2.3 | Dual-pane regime chart | Price + volatility regimes with high stress period shading |
| 2.4 | Risk-return scatter | Each trading day plotted by 21D volatility vs log return |
| 2.5 | Regime split histogram | Return distributions for calm vs panic market regimes |
| 2.6 | Maximum drawdown | Running peak to trough decline: MDD = **−59.86%** |
| 2.7 | ATR volatility channel | 14 day Average True Range(ATR) with ±2×ATR dynamic bands |
| 2.8 | Moving averages | SMA-50, SMA-200, EMA-20, EMA-50 overlaid on price |

### Strategic analytical questions

| Sub-section | Analysis | Description |
|-------------|----------|-------------|
| 3.1.1 | Day of week Anomaly | Average return and volatility by weekdays |
| 3.1.2 | Month of year effect | Seasonal return patterns by calendar month |
| 3.2 | Overnight(Gap) vs intraday(Grind)| Cumulative return decomposition: gap return vs intraday grind |

---

# Conclusion & key takeaways

### Return & growth
- Nifty 50 has delivered a strong long-run compounding trajectory despite severe interruptions(2008-2010, 2020),  reflecting the structural growth of the Indian economy over 2000–2026.
- Daily log returns are approximately zero-mean but exhibit significant non-normality: the distribution has fatter tails than a Gaussian would predict.

### Volatility & regime behaviour
- Short-term volatility (21-day) frequently and dramatically exceeds the long-run baseline (252-day), confirming that volatility is not constant.
- The regime-split histogram makes this concrete: the return distribution during high-volatility periods has visibly fatter tails and a flatter centre than during calm periods.

### Downside risk
- The maximum drawdown of **−59.86%** from peak to trough represents the most severe wealth erosion in the dataset, occurring during the 2008 Global Financial Crisis.
- The drawdown chart reveals that Nifty has experienced multiple periods of prolonged underwater duration, not just single sharp crashes.

### Technical structure
- The ATR volatility channel confirms that daily price ranges expand and contract systematically with market stress, providing a data-grounded frame for position sizing.
- The SMA-50 / SMA-200 crossover system captures the broad structural trend shifts that characterise Nifty's multi-year bull and bear cycles through **Golden Cross & Death Cross**.

### Day-of-the-week effect
- **Wednesday** show the highest average daily returns among all five sessions.
- **Monday** shows the only negative average return, consistent with the
  globally-observed *Monday effect* — where markets tend to open the week with subdued or negative sentiment.

### Month-of-the-year effect
- **November, December** stand out as the strongest positive months on average,
  consisted with `Santa Claus` Effect.
- **Jan - March** shows negative average returns,probably due to financial year end.

### Overnight gap vs intraday grind

- The **overnight return** : measured from each session's previous close to the next day's
  open — has compounded **consistently upward** across the full 25-year period.
- The **intraday return** : measured from each session's open to its close — tells the
  opposite story entirely. The cumulative intraday curve trends **downward** over the full
  period.

---

*Analysis conducted on daily OHLC data sourced from NSE. All returns are price returns only
and do not account for dividends, taxes, or transaction costs. Past performance and historical
patterns are not indicative of future results.*

---

