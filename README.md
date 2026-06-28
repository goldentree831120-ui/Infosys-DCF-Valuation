# Infosys DCF Valuation

A full discounted cash flow (DCF) valuation of Infosys Ltd. (NSE: INFY), cross-validated against peer comparables, built entirely in Excel.

## Overview

This project values Infosys using a 5-year discounted cash flow model anchored to historical financials (FY20–FY24), then sanity-checks the result against P/E and EV/EBITDA multiples from four IT sector peers.

## Methodology

1. **Historical financials** — pulled 5 years of Income Statement, Balance Sheet, and Cash Flow data from screener.in
2. **Free Cash Flow (FCF)** — calculated as Operating Cash Flow less Capex, with FCF margin derived from the historical average
3. **WACC** — built from:
   - Cost of Equity via CAPM (risk-free rate + Beta × equity risk premium)
   - After-tax Cost of Debt
   - Capital structure weights from the balance sheet
4. **5-year FCF projection** — forecast revenue growth and applied a consistent FCF margin assumption
5. **Terminal Value** — Gordon Growth Model, anchored to a ~4% long-term growth rate (India's long-run GDP growth)
6. **Enterprise Value → Equity Value → Intrinsic Value per Share** — standard DCF bridge
7. **Comparables cross-check** — benchmarked Infosys against TCS, Wipro, HCL Tech, and Tech Mahindra on P/E and EV/EBITDA, using sector median multiples to derive two additional implied valuations

## Key results

| Valuation method | Implied share price (₹) | vs Market price (₹1,498) |
|---|---|---|
| DCF Model | ~1,042 | Overvalued |
| P/E Comparables | ~1,498 | Fairly valued |
| EV/EBITDA Comparables | ~1,042 | Overvalued |
| **Average (blended)** | **~1,194** | **~20% overvalued** |

**Conclusion:** While Infosys trades in line with sector median P/E, both the DCF and EV/EBITDA comparables suggest the stock is trading at a premium to intrinsic value — indicating the market may be pricing in growth optimism not yet reflected in free cash flow generation.

*(Figures are based on FY24 data as of the time of analysis; re-running with updated financials will change the output.)*

## Tech stack

- Microsoft Excel (formula-driven model, no macros)
- Source data: [screener.in](https://www.screener.in)

## Repository contents

| File | Description |
|---|---|
| `Infosys_DCF_Valuation.xlsx` | Full model — Income Statement, Balance Sheet, Cash Flow, DCF Model, and Comparables sheets |

## How to use

Open `Infosys_DCF_Valuation.xlsx` in Excel. Key assumption cells (growth rate, WACC, terminal growth, FCF margin) are clearly labelled in the **DCF Model** sheet — change any of them to see the valuation update live.

## Notes & limitations

- DCF output is highly sensitive to the WACC and terminal growth rate assumptions; a sensitivity table (varying both ±2%) would be a natural enhancement
- Comparables use a small peer set (4 companies) — a larger peer universe would give a more robust sector median
- This is an educational/portfolio exercise, not investment advice
