
# 🚌 FlixBus Pricing Intelligence System

End-to-End Data Analytics Project | Mobility & Transport Pricing Optimization

---

## 📊 Project Overview

FlixBus Pricing Intelligence System is an end-to-end analytics solution designed to identify **pricing inefficiencies in bus listings** by benchmarking FlixBus prices against comparable market options.

In highly competitive travel platforms, pricing plays a critical role in **conversion, occupancy (load), and revenue optimization**. This system detects when FlixBus listings are **underpriced (revenue leakage)** or **overpriced (demand loss)** and quantifies the deviation.

The project builds a scalable framework that combines **peer comparison, statistical benchmarking, and rule-based flagging** to generate actionable pricing insights.

---

## 🎯 Business Problem

FlixBus operates in a dynamic pricing environment where competitors frequently adjust prices based on demand, timing, and service quality.

However:

* Pricing decisions lack **real-time benchmarking**
* Underpricing leads to **revenue loss**
* Overpricing leads to **lower occupancy and conversions**
* No system exists to **quantify deviation from market prices**

---

## ✅ What This Project Delivers

| Deliverable           | Description                                                       |
| --------------------- | ----------------------------------------------------------------- |
| Similar Bus Engine    | Identifies comparable buses using route, time, type, and duration |
| Pricing Benchmark     | Uses median price of peer buses as market reference               |
| Price Flagging System | Flags listings as TOO HIGH / TOO LOW / OK                         |
| Deviation Analysis    | Calculates absolute and % price difference                        |
| Fallback Logic        | Handles sparse data scenarios robustly                            |
| Excel Dashboard       | Structured output for business teams                              |
| Automation Plan       | Scalable MVP design using Python/SQL                              |

---

## 🔍 Key Logic & Methodology

### 1. Similar Bus Identification

Buses are considered comparable based on:

* **Date of Journey (DOJ)** → Same-day comparison
* **Bus Type** → Seater / Sleeper / Mixed
* **A/C vs Non-A/C** → Different pricing tiers
* **Departure Time** → Within ±2 hours
* **Journey Duration** → Within ±60 minutes

### Fallback Logic

* If < 2 peers found:

  * Relax duration constraint
  * Then expand group

---

### 2. Pricing Benchmark

* **Weighted Average Price (WAP)** used for FlixBus listings
* **Median Price of Peers** used as benchmark

👉 Median is chosen because:

* Robust to outliers
* Reflects realistic market price

---

### 3. Price Flagging Logic

| Condition             | Flag        |
| --------------------- | ----------- |
| Price > Median × 1.10 | 🔴 TOO HIGH |
| Price < Median × 0.90 | 🟡 TOO LOW  |
| Within ±10%           | ✅ OK        |

---

## 📈 Sample Output Insights

* Majority of listings flagged as **TOO LOW**
* Average underpricing: **~35–40% below market median**
* Maximum deviation observed: **~49%**

👉 Indicates **systematic underpricing and revenue leakage**

---

## 💡 Key Insights

* FlixBus is consistently priced below competitors
* Potential revenue loss due to aggressive pricing
* Pricing variation driven by:

  * Departure time
  * Bus type
  * Market competition

---

## 💰 Business Impact

| Metric                   | Value                                             |
| ------------------------ | ------------------------------------------------- |
| Pricing Issue Identified | Systematic underpricing                           |
| Avg Price Gap            | ~35–40% below market                              |
| Risk                     | Revenue leakage                                   |
| Opportunity              | Price optimization without losing competitiveness |

---

## 🧠 Assumptions

* Customers compare buses based on **time, type, and price**
* Pricing snapshot is taken at a single point in time
* Ratings and brand value are not included
* Dynamic pricing changes during the day are not considered

---

## ⚙️ Automation Plan (MVP)

### Workflow

```text
Data Source → Data Cleaning → Peer Matching → Price Benchmark → Flagging → Output/Dashboard
```

### Steps

1. **Data Ingestion**

   * Fetch data via API / CSV / database

2. **Data Processing**

   * Create time buckets
   * Standardize duration & categories

3. **Peer Matching**

   * Apply similarity filters

4. **Price Comparison**

   * Compute median benchmark
   * Calculate deviation

5. **Flagging System**

   * Apply ±10% rule

6. **Output Generation**

   * Export to Excel / dashboard

7. **Alerts (Optional)**

   * Notify pricing team via email/Slack

---

## 🛠 Tech Stack

| Category             | Tools Used              |
| -------------------- | ----------------------- |
| Language             | Python                  |
| Data Processing      | Pandas, NumPy           |
| Analysis             | Excel                   |
| Visualization        | Power BI (optional)     |
| Logic Implementation | Excel formulas / Python |
| Automation           | Cron / Scheduling tools |

---

## 📁 Project Structure

```
flixbus-pricing-analysis/
│
├── Data/
│   ├── Raw/
│   └── Processed/
│
├── Excel/
│   └── Pricing_Flagging_Output.xlsx
│
├── Scripts/
│   └── pricing_analysis.py
│
├── Reports/
│   └── Pricing_Insights_Report.pdf
│
└── README.md
```

---

## 📊 Output Fields

* DOJ
* Route
* FlixBus Price (WAP)
* Peer Median Price
* Price Difference (%)
* Flag (TOO HIGH / TOO LOW / OK)
* Comparable Bus Count

---

## 🚀 Future Improvements

* Add **load factor (seat occupancy)** for demand-based pricing
* Incorporate **ratings & brand value**
* Build **ML-based price recommendation system**
* Enable **real-time pricing updates**
* Use **IQR for robust anomaly detection**

---

## 🧾 Conclusion

This system provides a **data-driven pricing intelligence layer** that enables FlixBus to:

* Detect pricing inefficiencies
* Improve competitiveness
* Optimize revenue

👉 By aligning prices with market benchmarks, the platform can achieve **better conversion rates and higher profitability**.

---

## 👩‍💻 Author

**Priyanka Panda**
Data Analyst | Python · SQL · Power BI

---


