# 🌫️ India Air Quality Analysis (2015–2020)

## 📌 Overview
This project presents a **multi-granular analysis of India’s air quality** using five years (2015–2020) of daily and hourly data from **230+ monitoring stations across 26 cities**.

* It was developed as a submission to Impact Metrics(Jagriti'26, IIT BHU) by Team TBD(The Breath Deficits).

We combine:
- Robust **data preprocessing & imputation**
- **Hotspot detection & seasonal analysis**
- **Pollutant correlation & source attribution**
- **Sensor reliability auditing**
- **Public health risk metrics**

The final output is a **policy-oriented analytical framework** supported by an interactive dashboard.

---

## 📂 Dataset

### Data Includes:
- Pollutants: PM2.5, PM10, NO, NO₂, NOx, SO₂, CO, O₃, NH₃, Benzene, Toluene, Xylene  
- AQI values + AQI Buckets (CPCB standards)  
- Station-level & city-level data  
- Hourly and daily observations  

---

## ⚙️ Data Preprocessing

Due to **high missingness and inconsistencies**, we implemented a **gap-aware imputation pipeline**.

### Key Strategies:
- **Short gaps:** Forward/Backward fill  
- **Medium gaps:** Station/City monthly medians  
- **Fallback:** Seasonal medians  
- **Long gaps:** Flagged (not imputed)
---

## 🔍 Key Analyses

### 1. 🗺️ Pollution Hotspots
- Identified **station-level and city-level hotspots**
- Detected **sensor anomalies** (e.g., CO in Ahmedabad)
- Recomputed AQI after removing faulty pollutant influence

### 2. 🌦️ Seasonal Trends
- Additive decomposition of AQI revealed:
  - **Peak Pollution:** January (+70 AQI deviation)
  - **Lowest Pollution:** August (-66 AQI deviation)

### 3. 🎆 Event-Based Spike Analysis
Compared pollution spikes during:
- **Diwali 2019**
- **New Year 2019**

---

## 🔗 Pollutant Relationships

### Correlation Insights:
- Strong correlation:
  - **PM2.5 ↔ PM10 (0.846)**
- Negative relationship:
  - **SO₂ ↔ NH₃** (chemical reactivity)

---

## 🧠 Source Attribution

We designed **rule-based scoring** to infer pollution sources:

| Source Type | Indicators |
|------------|-----------|
| Industrial | High SO₂ + NOx |
| Vehicular | High NO₂ + CO |
| Winter     | High PM2.5 |
| Summer     | High PM10 / O₃ |
| Monsoon    | Elevated SO₂ |
| Post-Monsoon | High PM2.5 |

---

## 🧩 Clustering Cities

- Applied **K-Means clustering**
- Features: statistical summaries of 6 pollutants
- Optimal clusters: **K = 11**
- Result: cities grouped by **pollution signatures**

---

## 🏭 Station Performance Audit

We evaluated monitoring stations using:

### 📊 Metrics:
- **Completeness** = Available data / Expected data  
- **Validity** = Valid readings / Total readings  
- **Uptime** = Operational duration  
- **Reliability Score** = Weighted (0.4, 0.4, 0.2)

### 🚨 Key Findings:
- Average reliability ≈ **80%**
- Severe data gaps in:
  - NH₃, Toluene, Xylene (~20% completeness)
- Monsoon → most accurate but least uptime
- Some stations showed **long outages or dormancy**

---

## 📈 Public Health Impact Metrics

We designed **WHO-aligned risk metrics**:

### Definitions:
- **Intensity** = Annual avg concentration  
- **Exposure** = Exceedance days / total days  
- **Risk Score** = Intensity × (1 + Exposure)  
- **R (YoY Change)** = % change in risk  

### 👥 Vulnerable Groups:
- Children & infants  
- Elderly (65+)  
- Pregnant women  
- Respiratory & cardiac patients  
- Outdoor workers  

---

## 📊 Key Insights

- PM2.5 dominates pollution in **11 cities**
- PM10 dominates in **15 cities**
- Fireworks cause **consistent short-term pollution spikes**
- Data quality is a **major bottleneck**
- Sensor anomalies can **distort policy decisions**

---

## 🛠️ Recommendations

### Monitoring Improvements:
- Better **power infrastructure** (reduce downtime)
- **Sensor upgrades** (NH₃, VOCs coverage)
- Regular **calibration checks**
- Improved **data pipelines**

### Policy Suggestions:
- Focus on **PM2.5 reduction strategies**
- Strengthen monitoring in **low-performing states**
- Expand coverage in **under-monitored regions**

---

## 📊 Dashboard
An interactive dashboard was developed to:
- Visualize AQI trends
- Compare cities
- Track pollution sources
- Monitor station reliability

---

## 🧑‍💻 Tech Stack
- Python (Pandas, NumPy, Matplotlib, Scikit-learn)
- Time Series Analysis
- Statistical Modeling
- Microsoft Excel

---

## 🧑‍💻 Team
- Aayush Agarwal
- Akshara Jain
- [Vanshika Kataria](https://github.com/Vk2008)

---
