# 🚕 Uber Supply–Demand Gap Analytics
> **End-to-End Data Analytics Solution for Ride Availability & Operational Efficiency**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Excel](https://img.shields.io/badge/Excel-Data%20Cleaning-green.svg)]()
[![SQL](https://img.shields.io/badge/SQL-Analysis-orange.svg)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

![Uber Dashboard](assets/dashboard_preview.png)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Business Problem](#business-problem)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [Project Architecture](#project-architecture)
- [Installation & Setup](#installation--setup)
- [Data Pipeline](#data-pipeline)
- [Dashboard Preview](#dashboard-preview)
- [Key Insights](#key-insights)
- [Project Structure](#project-structure)
- [Usage Guide](#usage-guide)
- [Performance Metrics](#performance-metrics)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🎯 Overview

**Uber Supply–Demand Gap Analytics** is a data-driven initiative designed to identify and quantify operational inefficiencies across Uber ride availability. Using **Excel, SQL, and Python**, this project uncovers patterns related to supply shortages, driver cancellations, and unmet rider demand across time slots—especially along the **Airport ↔ City** route.

Insights are derived from documented analysis and visual evidence including supply gaps, cancellation patterns, and time-slot trends.

---

## 🛑 Business Problem

Uber faces recurring operational challenges:

- 🌙 **Night-time cab unavailability**
- 🌅 **Driver cancellations during Early Morning & Morning**
- 📉 Poor fulfilment rates in high-demand slots
- 🛫 **Airport → City route most affected**
- 🚫 Frequent “No cabs available” windows

These factors negatively impact customer experience and revenue potential.

---

## ⚡ Key Features

### 📊 Data Processing
- Excel cleaning & formatting
- Python-based EDA (Pandas, NumPy)
- Time-slot segmentation
- Outlier and missing-value management

### 🗄️ SQL Analytics
- Supply vs demand time-slot metrics
- Driver cancellation analysis
- Route-level ride distribution
- KPI generation (availability, cancellation %, fulfilment %)

### 📈 Interactive Dashboards
- Excel dashboard with pivot tables
- Cancellation heatmaps
- Time-slot demand–supply charts
- Route-specific visuals

### 🔍 Business Intelligence
- Operational bottleneck identification
- Driver behavior insights
- Demand forecasting foundations
- Incentive-based solution strategies

---

## 🛠️ Technology Stack

### Data Engineering
| Technology | Purpose |
|-----------|---------|
| **Excel** | Data cleaning, pivot tables |
| **Python** | EDA & metrics |
| **Pandas, NumPy** | Data processing |
| **Matplotlib/Seaborn** | Visual insights |

### Database & Querying
| Technology | Purpose |
|-----------|---------|
| **SQL (MySQL)** | Aggregations & analysis |

### Development Tools
| Tool | Purpose |
|------|---------|
| Jupyter | Notebook execution |
| Git | Version control |
| VS Code | IDE |

---

## 🏗️ Project Architecture

```
┌──────────────────────────────────────────────┐
│                 DATA SOURCES                │
│      Raw Uber Ride Logs (Excel/CSV)         │
└──────────────────────────────┬──────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────┐
│              EXCEL DATA CLEANING             │
│  • Format timestamps                          │
│  • Remove duplicates                          │
│  • Fix missing values                          │
└──────────────────────────────┬──────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────┐
│            PYTHON EDA & METRICS              │
│  • Demand vs Supply                           │
│  • Driver cancellations                        │
│  • Time-slot segmentation                      │
└──────────────────────────────┬──────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────┐
│                 SQL ANALYSIS                 │
│  • Aggregations                                │
│  • KPI calculations                            │
│  • Route-specific analysis                     │
└──────────────────────────────┬──────────────┘
                               │
                               ▼
┌──────────────────────────────────────────────┐
│                 DASHBOARD (EXCEL)            │
│  • KPIs                                       │
│  • Heatmaps                                   │
│  • Trend charts                                │
└──────────────────────────────────────────────┘
```

---

## 🚀 Installation & Setup

### Prerequisites
```bash
Python 3.8+
Excel 2016+
MySQL 8.0+
pip install pandas numpy matplotlib seaborn
```

### Clone Repository
```bash
git clone https://github.com/yourusername/uber-supply-demand-gap.git
cd uber-supply-demand-gap
```

### Run Python EDA
```bash
jupyter notebook Uber_Supply_Demand_EDA.ipynb
```

### Review Dashboard
Open Excel file:
```
Excel/Uber_Supply_Demand_Dashboard.xlsx
```

---

## 🔄 Data Pipeline

### Phase 1: Data Exploration
- Verified row counts
- Checked dataset quality
- Segmented ride timestamps

### Phase 2: Data Cleaning
- Removed incorrect entries
- Standardized columns
- Fixed inconsistent time formats

### Phase 3: Data Transformation
- Computed core metrics:
  * Ride Requests
  * Cancellations
  * Availability
  * Completion Rate
- Time-slot extraction

### Phase 4: SQL Insights
- Supply–demand ratio queries
- Cancellation trend analysis
- Airport route patterns

---

## 📊 Dashboard Preview

### Page 1: Supply–Demand Overview
- Hourly demand vs supply chart
- Successful vs cancelled rides
- Time-slot fulfilment summary

### Page 2: Cancellation Analysis
- Heatmap of driver cancellations
- Trendline of cancellation %
- Route-wise issue breakdown

### Page 3: Airport Route Insights
- High-demand windows
- Zero-availability periods
- Completion probability analyses

### Page 4: Shift Comparison View
- Night vs Morning supply patterns
- Behaviour analysis
- Performance metrics

---

## 💡 Key Insights

### 🌙 Night Slot (Major Supply Shortage)
- Very few drivers available
- High “No cabs available” cases
- Airport → City route most affected

### 🌅 Early Morning & Morning (High Cancellations)
- Most driver cancellations occur here
- High fulfilment failures
- Severe rider dissatisfaction risk

### 🛫 Airport Route Dominates Issue Zone
- Highest demand but lowest supply
- Shown in Figures 1.1, 1.2, 1.3 (PDF)

### 📉 Operational Risks
- Revenue loss
- Longer wait times
- Poor service reliability

---

## 🧭 Recommendations

### ✔ Rush-Hour Incentive Pricing
- Increase driver payouts for Morning & Early Morning

### ✔ Dedicated Night Shifts
- Ensure driver pool availability at night

### Additional Recommendations
- Cancellation penalties
- Zone-based incentive boosts
- Predictive driver assignment
- Time-slot based surge optimization

---

## 📂 Project Structure
```
Uber-Supply-Demand-Analytics/
│
├── Data/
│   ├── raw_source.xlsx
│   ├── cleaned_dataset.xlsx
│   └── time_slot_data.csv
│
├── Python/
│   ├── Uber_Supply_Demand_EDA.ipynb
│   └── utils.py
│
├── SQL/
│   ├── supply_demand_queries.sql
│   └── cancellation_analysis.sql
│
├── Excel/
│   └── Uber_Supply_Demand_Dashboard.xlsx
│
├── Insights/
│   └── Uber_Supply_Demand_Gap_Insights.pdf
│
└── README.md
```

---

## 📖 Usage Guide

### For Business Users
- Open Excel dashboard  
- Review KPIs, trends, heatmaps  
- Filter by route, time slot, date  

### For Analysts
- Use SQL scripts for custom queries  
- Run EDA notebook for extended research  

### For Developers
- Modify Python scripts to add new metrics  
- Integrate Power BI or real-time APIs  

---

## ⚡ Performance Metrics

| Metric | Value |
|--------|--------|
| Data Cleaning | 2 minutes |
| Python EDA Runtime | < 10 seconds |
| SQL Query Time | < 0.3 seconds |
| Dashboard Refresh | Instant |

---

## 🚀 Future Enhancements

- Predictive demand forecasting  
- Machine learning cancellation model  
- Driver-shift optimization engine  
- Real-time monitoring dashboard  
- Power BI integration  
- API-based live ride tracking  

---

## 🤝 Contributing

1. Fork the repo  
2. Create a feature branch  
3. Commit changes  
4. Open a Pull Request  

---

## 📄 License
This project is licensed under the MIT License.

---

## 📞 Contact

**Your Name**  
Email: your.email@example.com  
LinkedIn: https://linkedin.com/in/yourprofile  
GitHub: https://github.com/yourusername  

---

<div align="center">

**⭐ If you find this project insightful, please consider starring the repository! ⭐**

Made with ❤️ by *Sanket*

</div>
