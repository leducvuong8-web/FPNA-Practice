
# FP&A Commercial Performance Analysis & FY2026 Forecasting

### Financial Variance Analysis | Demand Forecasting | Strategic Decision Support

**Sector:** UK Leisure & Entertainment  
**Tools:** Python, Excel, Pandas, Scikit-learn, XGBoost, Statsmodels  
**Analysis Cutoff:** 1 June 2026

---

## 1. Executive Summary

This project develops an end-to-end FP&A framework for Nova Leisure Group, a synthetic UK leisure operator with five locations.

The objective is to answer three business questions:

1. **What happened?** Identify the drivers behind FY2025 financial underperformance.
2. **What happens next?** Forecast site-level demand and financial performance through December 2026.
3. **What should management do?** Evaluate three strategies using scenario and sensitivity analysis.

The analysis combines **6,805 cleaned financial transactions, 240 budget records, and 2,550 daily footfall observations**.

## 2. FY2025 Financial Performance

Nova reported an **EBITDA shortfall of £785K (−15%)** against budget, despite revenue falling by only 2.1%.

| KPI | FY2025 Result |
|---|---:|
| Revenue | £17.64M |
| Revenue Variance | −£381K |
| COGS Variance | −£119K |
| Wage Variance | −£184K |
| EBITDA | £4.45M |
| EBITDA Margin | 25.24% |

Revenue underperformance accounted for approximately 48.5% of the EBITDA shortfall, while cost overruns explained the remaining 51.5%.

**[INSERT CHART: FY2025 EBITDA Budget vs Actual Waterfall]**

F&B contributed the largest revenue shortfall, while Bristol recorded the lowest site-level EBITDA margin (24.45%).

**[INSERT CHART: FY2025 Site Profitability Comparison]**

## 3. UK Macroeconomic Context

As of 1 June 2026, the UK leisure sector faced continued demand and cost pressures.

| Indicator | Latest Available |
|---|---:|
| UK Headline CPI (Apr 2026) | 2.8% |
| Food Inflation | 3.0% |
| UK Retail Footfall (Apr 2026) | −10.7% YoY |
| National Living Wage (21+) | £12.71/hour |
| Bank Rate | 3.75% |

Despite weak retail footfall nationwide, Nova's own visitor numbers declined by only **0.5% YoY** during January–25 May 2026.

This suggests that revenue recovery and cost efficiency should be evaluated together rather than assuming a broad collapse in demand.

## 4. Forecasting Methodology

### Step 1 – Data Cleaning

- Removed 30 blank rows and 25 duplicate transactions.
- Reclassified 105 incorrectly coded transactions.
- Standardized account descriptions and addressed missing departmental tags.
- Reconciled cleaned financial records with the P&L structure.

### Step 2 – Demand Forecasting

Four forecasting models were evaluated:

| Statistical | Machine Learning |
|---|---|
| Holt-Winters | Random Forest |
| SARIMA | XGBoost |

Rolling-origin backtesting evaluated MAE, WAPE and forecast bias over 28-day and 90-day horizons.

The **Year-Ago Same Weekday benchmark** outperformed all four models, achieving approximately **12.2% weighted WAPE**.

**[INSERT CHART: 01_model_wape.png — Forecast Model Comparison]**

The selected approach forecasts site-level daily visitors through 31 December 2026.

**[INSERT CHART: 02_footfall_forecast.png — Actual vs Forecast Footfall]**

### Step 3 – Financial Forecasting

Demand forecasts are integrated into a driver-based financial model covering:

- Revenue by business segment
- COGS and input-cost inflation
- Wage costs and labor productivity
- Fixed and variable operating expenses
- Monthly EBITDA and EBITDA margin

FY2026 financial figures are model estimates, not reported actuals.

## 5. Strategic Alternatives

Three strategies were evaluated for June–December 2026.

| Strategy | Main Objective |
|---|---|
| Strategy 1 – Revenue Growth | Recover 50% of FY2025 revenue budget gaps |
| Strategy 2 – Cost Optimization | Reduce COGS ratio and improve wage efficiency |
| Strategy 3 – Combined | Integrate revenue growth and cost optimization |

Strategy assumptions are derived from FY2025 budget gaps and historical operating costs, with phased implementation from July 2026.

## 6. Scenario & Sensitivity Analysis

Three macroeconomic scenarios were tested:

| Driver | Bear | Base | Bull |
|---|---:|---:|---:|
| Footfall Shock | −5% | 0% | +3% |
| Additional COGS Inflation | +2% | 0% | −1% |
| Additional Wage Inflation | +1.5% | 0% | 0% |

The analysis compares strategies using forecast EBITDA, EBITDA margin, incremental EBITDA and Bear Case resilience.

**[INSERT CHART: 13_scenario_comparison.png — Strategic Scenario Comparison]**

A further sensitivity test evaluated **25 combinations of footfall and COGS shocks**.

**[INSERT CHART: 14_ebitda_sensitivity.png — EBITDA Sensitivity Heatmap]**

## 7. Results & Recommendation

**Strategy 3 – Combined Revenue Growth & Cost Optimization** achieved the strongest results under the tested assumptions.

| Metric | Strategy 3 |
|---|---:|
| Base Case EBITDA | £2.995M |
| EBITDA Margin | 26.88% |
| Incremental EBITDA | +£96.7K |
| Bear Case EBITDA | £2.557M |
| Bear Case Incremental EBITDA | +£93.2K |
| Sensitivity Tests Won | 25/25 |

**[INSERT CHART: 03_strategy_ebitda.png — Monthly EBITDA Forecast by Strategy]**

### Recommendation

Adopt **Strategy 3** through a phased H2 2026 rollout, prioritizing revenue improvement alongside procurement efficiency and workforce optimization.

The combined strategy provides the highest projected profitability and strongest Bear Case performance within the tested scenarios.

All strategic impacts are model-based estimates and remain subject to implementation validation.

## 8. Repository Files

| File | Description |
|---|---|
| `Clean data.ipynb` | Data cleaning, account mapping and reconciliation |
| `Forecast.ipynb` | Statistical and ML forecasting, financial modelling and strategy evaluation |
| `2025_Actual_Clean.csv` | Cleaned FY2025 financial transactions |
| `Actual_vs_Budget.xlsx` | FY2025 financial analysis, budget and footfall data |
| `fpa_2026_outputs/` | Model results, forecasts and visualizations |

### Run Locally

Install dependencies:

`pip install pandas numpy matplotlib scikit-learn statsmodels xgboost openpyxl`

Run `Clean data.ipynb` to reproduce the cleaned ledger, then execute `Forecast.ipynb`.

## 9. Data Sources & Disclaimer

**Original synthetic dataset:**  
[Amogh21hh – FPA Commercial Variance Engine](https://github.com/Amogh21hh/FPA-Commercial-Variance-Engine)

**Macroeconomic references:**
- [Office for National Statistics](https://www.ons.gov.uk/)
- [British Retail Consortium](https://brc.org.uk/)
- [UK Government – National Minimum Wage](https://www.gov.uk/national-minimum-wage-rates)
- [Bank of England](https://www.bankofengland.co.uk/)

Nova Leisure Group is a fictional company. The source datasets are synthetic. Data cleaning, financial analysis, model comparison and strategic evaluation presented here were developed as a personal FP&A portfolio project.

Forecasts and strategy results are illustrative, not actual corporate financial guidance.
