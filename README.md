# Time Series Web Search & Economic Indicators Analysis

## **Overview**
This project analyzes how public interest (measured through Google Trends search data) relates to real‑world indicators such as unemployment rates, Bitcoin prices, and Tesla stock prices.  
The workflow includes data cleaning, datetime normalization, resampling, merging datasets, descriptive statistics, and dual‑axis visualizations.

---

## **Datasets Used**
### **Portugal — Unemployment**
- Monthly search interest for *“subsídio de desemprego”*.
- Annual unemployment rate (UNRATE_PT).

### **Bitcoin**
- Monthly search interest for Bitcoin.
- Daily Bitcoin price and volume.

### **Tesla**
- Monthly search interest for Tesla.
- Monthly Tesla stock price.

---

## **Data Processing**
### **Unemployment (Portugal)**
- Convert `Time` to datetime → extract `YEAR`.
- Rename search column to `UE_BENEFITS_WEB_SEARCH_PT`.
- Aggregate search interest by year.
- Merge annual search interest with unemployment rate.

### **Bitcoin**
- Convert monthly search dates to `MONTH` periods.
- Convert daily price timestamps to `DATE`.
- Select and rename relevant columns (`CLOSE`, `VOLUME`).
- Identify daily periodicity (28–31 days).

### **Tesla**
- Convert search dates to `MONTH`.
- Clean stock price column (remove `$`, convert to float).
- Aggregate monthly average price.
- Merge monthly search interest with monthly price.

---

## **Descriptive Statistics**
### **Tesla**
- Search interest: avg ≈ 45, range 20–100.  
- Price: avg ≈ \$183, range \$14–\$462.  
- Higher search interest aligns with higher prices.

### **Portugal Unemployment**
- Search interest: avg ≈ 30, range 0–65.  
- Unemployment rate: avg ≈ 9.3%, range 6–17.2%.  
- Higher search interest corresponds to higher unemployment.

### **Bitcoin Search**
- Search interest: avg ≈ 22, range 0–100.  
- Strong spikes during major BTC events.

### **Bitcoin Price**
- Price: avg ≈ \$101,325, range \$76,272–\$124,753.  
- Volume highly volatile (≈ \$9.8B–\$181.7B).

---

## **Key Insights**
### **Tesla — Price vs Search Volume**
- 2018–2019: Low price, moderate search interest.  
- 2020: Sharp rise in both — start of major growth.  
- 2021–2025: Trends move together; public interest aligns with price peaks.  
- Positive correlation.

### **Bitcoin — Price vs Search Volume**
- Early 2025: Both high, then fall.  
- Mid‑2025: Price rebounds; searches stay low.  
- Late 2025: Search spike followed by price drop.  
- Loose positive correlation.

### **Portugal — Unemployment Benefits Search vs Unemployment Rate**
- 2008–2013: Both peak during financial crisis.  
- 2020: COVID‑19 spike.  
- After 2021: Stabilization.  
- No strong seasonality; searches respond to economic shocks.
