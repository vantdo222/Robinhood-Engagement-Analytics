# 📊 Robinhood Engagement Analytics: What Drives Retail Investor Behavior?

## 🧩 Overview  
This project analyzes **what drives user engagement on Robinhood** by linking user holdings data with stock performance metrics.

The core question:
> Do product characteristics (returns, volatility, momentum) drive user engagement — or does user behavior move independently?

Using a structured feature engineering and regression framework, this project identifies **causal drivers of engagement** and translates them into **actionable product insights**.

---

## 📏 Measuring Engagement (RobinTrack Data)

User engagement is proxied using Robinhood holdings data, capturing both **level and change in user behavior**:

- **Holdings Volume**  
  Number of users holding a stock on a given day  
  → Baseline measure of user engagement

- **Change in Holdings (Δ Holdings)**  
  Day-over-day change in number of users  
  → Primary dependent variable capturing user inflows/outflows

- **Holdings Growth Rate**  
  Percentage change in holdings over time  
  → Normalized measure of engagement trends

- **Attention Spikes**  
  Days where growth exceeds rolling thresholds (2σ above mean)  
  → Captures sudden surges in user interest (e.g., news, volatility events)

---

## 📈 Measuring Product Characteristics (Stock Data)

Stock features are engineered from daily returns to represent **product attributes that may drive engagement**:

- **Daily Returns**  
  Primary measure of stock performance

- **Volatility (20-day rolling)**  
  Standard deviation of returns (annualized)  
  → Proxy for risk, uncertainty, and “excitement”

- **Momentum (5-day & 30-day)**  
  Cumulative returns over short and medium horizons  
  → Captures trend-following behavior

- **Drawdowns (90-day)**  
  Decline from recent peak price  
  → Identifies “dip-buying” opportunities

---

## ⚙️ Methodology  

### 1. Data Engineering
- Merged Robinhood holdings data with market price data (yfinance)  
- Built a panel dataset across 6 stocks + SPY benchmark  

### 2. Feature Engineering
- Constructed engagement and product metrics as defined above  
- Created lagged variables to capture behavioral persistence  
- Winsorized data to reduce impact of outliers  

### 3. Exploratory Data Analysis
- Visualized holdings vs. returns using dual-axis plots  
- Generated correlation heatmaps and regression scatter plots  
- Tested behavioral persistence using autocorrelation (ACF)  

---

## 📊 Key Findings  

- **Volatility is the strongest driver of engagement**  
  → Users respond more to magnitude of movement than direction  

- **Retail investors exhibit dip-buying behavior**  
  → Negative returns in volatile stocks increase user participation  

- **Behavioral inertia is significant**  
  → Prior-day engagement strongly predicts future engagement  

- **Stock-specific effects dominate market-wide movements**  
  → Engagement is driven more by individual stock behavior than overall market trends  

---

## 💡 Product Implications  

- 📲 Trigger **volatility-based notifications** (“This stock moved X% today”)  
- 🔍 Surface **high-volatility or drawdown stocks** in discovery feeds  
- 🤖 Use **lagged engagement signals** for personalization  
- 🎯 Tailor UX for **high-volatility vs. stable stocks**  

---

## 🛠️ Tech Stack  
- Python (Pandas, NumPy, Statsmodels, Seaborn, Matplotlib)  
- Time-series analysis & regression modeling  
- Feature engineering & causal inference  

---

## 📁 Project Structure  
