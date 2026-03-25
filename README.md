# 📊 Robinhood Engagement Analytics: What Drives Retail Investor Behavior?

## 🧩 Situation  
Retail trading platforms like Robinhood experience rapid spikes in user activity, but it is unclear **what actually drives user engagement**. Is engagement driven by stock performance (returns), or do users respond more strongly to volatility, momentum, or behavioral patterns?

---

## 🎯 Task  
Build an end-to-end data analysis pipeline to:
- Quantify **user engagement** using Robinhood holdings data  
- Engineer **stock-level product features** (returns, volatility, momentum, drawdowns)  
- Determine **which characteristics causally drive changes in user holdings**  
- Translate findings into **actionable product recommendations**

---

## ⚙️ Action  

### Data Engineering
- Merged Robinhood holdings data with market price data (yfinance)  
- Constructed a panel dataset across 6 stocks + SPY benchmark  

### Feature Engineering
- Built engagement metrics:
  - Day-over-day change in holdings (primary dependent variable)
  - Growth rates and attention spikes  
- Engineered product characteristics:
  - Daily returns  
  - 20-day rolling volatility (annualized)  
  - 5-day and 30-day momentum  
  - 90-day drawdowns  

### Exploratory Data Analysis
- Visualized holdings vs. returns using dual-axis time series plots  
- Generated correlation heatmaps and regression scatter plots  
- Tested behavioral persistence using autocorrelation (ACF)  

### Modeling
- Implemented 4 regression models with increasing rigor:
  1. Naive OLS (returns only)  
  2. Multi-factor model (volatility, momentum, drawdown)  
  3. Lagged controls (behavioral inertia + delayed reactions)  
  4. Full causal specification (market controls + day-of-week effects)  
- Evaluated models using R², AIC, and statistical significance  

### Analysis & Interpretation
- Extracted and ranked key drivers of engagement across all stocks  
- Compared effects across volatile vs. stable equities  

---

## 📈 Results  
- **Volatility is the strongest driver of engagement**  
  → Users respond more to “excitement” than direction  

- **Retail investors exhibit dip-buying behavior**  
  → Negative returns in volatile stocks (e.g., AAL, F) are associated with increased holdings  

- **Behavioral inertia is significant**  
  → Prior-day engagement strongly predicts future engagement  

- **Stock-specific effects dominate market-wide movements**  
  → Even after controlling for SPY returns, individual stock characteristics remain significant  

---

## 💡 Business Impact  
This analysis suggests clear product opportunities for Robinhood:

- 📲 Trigger **volatility-based notifications** (“This stock moved X% today”)  
- 🔍 Surface **high-volatility or drawdown stocks** in discovery feeds  
- 🤖 Use **lagged engagement signals** to personalize recommendations  
- 🎯 Differentiate UX for **high-volatility vs. stable stocks**

---

## 🛠️ Tech Stack  
- Python (Pandas, NumPy, Statsmodels, Seaborn, Matplotlib)  
- Time-series analysis & regression modeling  
- Feature engineering & causal inference frameworks  
