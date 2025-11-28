# 🚖 Uber Supply-Demand Gap Analysis  
**End-to-End Data Analytics Solution for Ride-Hailing Operations**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-orange.svg)](https://www.mysql.com/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-green.svg)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.0+-red.svg)](https://matplotlib.org/)

![Uber Analysis Dashboard](assets/supply_demand_gap.png)

---

## 📋 Table of Contents
- [Overview](#overview)
- [Key Findings](#key-findings)
- [Technology Stack](#technology-stack)
- [Project Architecture](#project-architecture)
- [Installation & Setup](#installation--setup)
- [Data Analysis Pipeline](#data-analysis-pipeline)
- [Visualizations](#visualizations)
- [Business Insights](#business-insights)
- [Recommendations](#recommendations)
- [Project Structure](#project-structure)
- [Usage Guide](#usage-guide)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Project Stats](#project-stats)

---

## 🎯 Overview
The **Uber Supply-Demand Gap Analysis** project identifies critical operational imbalances in Uber's ride-hailing system.  
This analysis uncovers driver shortages, peak demand windows, and cancellation patterns through full-stack data analytics.

### Business Challenges
- High cancellation rates during early mornings  
- Driver shortages during night hours  
- Severe imbalance on Airport ↔ City routes  
- Lost revenue due to unmet demand  
- Missing time-slot–specific driver allocation strategy  

### Key Outcomes
- Identified **peak demand hours** (5–11 AM & 5–9 PM)  
- Quantified **3,500+ unmet requests** (~48% demand)  
- Found **Airport ↔ City** as the most problematic corridor  
- Mapped **driver cancellation patterns** (highest at 5–9 AM)  
- Provided **actionable strategies** to reduce gap by 30–40%  

---

## 💡 Key Findings

### 1. Night & Early Morning Supply Crisis
- **Night (8 PM - 4 AM)**  
  - 877 unfulfilled Airport requests  
  - 648 unfulfilled City requests  
- **Early Morning (5–9 AM)**  
  - 1,457 Airport cancellations  
  - 436 City cancellations  
- **Impact:** 40% of requests go unserved  

### 2. Route-Specific Imbalances
- **City → Airport:** 3,507 unmet requests  
- **Airport → City:** 3,256 unmet requests  
- **Morning Peak:** 1,952 City requests  

### 3. Driver Cancellation Behavior
- 5–9 AM = **170+ cancellations/hour**  
- 5–9 PM = **35 cancellations/hour**  
- Drivers avoid long airport trips → high cancellations  

### 4. Time Slot Trends
| Time Slot | Requests | Completion Rate | Gap |
|----------|-----------|-----------------|------|
| Morning (5–11 AM) | 1,893 | 23% | High |
| Evening (5–8 PM) | 1,457 | 30% | High |
| Afternoon (12–4 PM) | 810 | 45% | Low |
| Night (9 PM–4 AM) | 1,525 | 43% | Medium |

---

## 🛠️ Technology Stack

### Data Processing & Analysis
| Technology | Purpose |
|-----------|---------|
| Python 3.8+ | Core analysis |
| Pandas | Data manipulation |
| NumPy | Numerical ops |
| Matplotlib & Seaborn | Visualization |

### Database
| Technology | Purpose |
|-----------|---------|
| MySQL 8.0 | Database |
| SQLAlchemy | Python-MySQL bridge |
| MySQL Workbench | DB admin |

### Tools
- Jupyter Notebook  
- VS Code  
- Git & GitHub  

---

## 🏗️ Project Architecture

```
DATA SOURCE → PYTHON EDA → MYSQL ANALYTICS → VISUALIZATIONS → INSIGHTS REPORT
```

### Data Processing Flow
```
Uber.csv (6,745 records)
    ↓
Load & Explore → Clean & Validate → Feature Engineering → Aggregation → Visualization
```

---

## 🚀 Installation & Setup

### 1. Clone Repository
```bash
git clone https://github.com/yourusername/uber-supply-demand-analysis.git
cd uber-supply-demand-analysis
```

### 2. Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate       # Mac/Linux
venv\Scripts\activate          # Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Setup MySQL Database
```sql
CREATE DATABASE uber;
USE uber;
SOURCE sql/UBER_By_SQL.sql;
```

### 5. Configure Environment
Create `.env`:
```
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=your_password
MYSQL_DATABASE=uber
```

### 6. Place Dataset
```
data/
└── Uber.csv
```

### 7. Run Analysis
```bash
python uber_eda.py
```

---

## 📊 Data Analysis Pipeline

### Phase 1 — Load & Explore
- Dataset shape: **6,745 × 12**
- Missing values handled
- Datatypes standardized  

### Phase 2 — Data Cleaning
- Standardized dates/times  
- Cleaned invalid values  
- Normalized categories  

### Phase 3 — Feature Engineering
- Created `Time_Slot`  
- Added binary flags  
- Derived timestamps  

### Phase 4 — Aggregations
- Hourly demand  
- Pickup point comparison  
- Time-slot segmentation  
- Day-wise status analysis  

### Phase 5 — Visualization
- Demand gap chart  
- Pickup point comparison  
- Heatmap  
- Stacked bar chart  
- Hourly demand  

---

## 📈 Visualizations

### Supply-Demand Gap by Hour
![Demand Gap](plots/demand_gap_by_hour.png)

### Pickup Point Gap
![Pickup Gap](plots/demand_gap_pickup.png)

### Heatmap
![Heatmap](plots/heatmap_time_pickup.png)

### Hourly Demand
![Hourly Demand](plots/hourly_demand.png)

### Stacked Status Chart
![Stacked](plots/hourly_stacked_status.png)

---

## 💼 Business Insights

### Peak Hours
- **5–9 AM & 5–9 PM** dominate unmatched demand  
- Night shortages due to low driver availability  

### Route-Based Insights
- City → Airport gap: **3,507**
- Airport → City gap: **3,256**

### Financial Impact
- Daily loss: **$47,800–$59,750**  
- Annual opportunity: **$17M–$22M**  

---

## 🎯 Recommendations

### 1. Rush Hour Incentives
- Reduce cancellations by 40–50%  
- Increase morning supply  

### 2. Night Shift Driver Program
- Fill 60–70% of night gaps  

### 3. Route-Based Dynamic Pricing
- Improve driver willingness  
- Balance City ↔ Airport demand  

### 4. Driver Performance Dashboard
- Tiered ratings  
- Automated penalties  

### 5. Predictive Supply Allocation
- Pre-position drivers  
- ML-based demand forecasting  

---

## 📂 Project Structure

```
Uber-Supply-Demand-Analysis/
│
├── data/
│   └── Uber.csv
├── outputs/
│   ├── summary CSV files
│   ├── uber_summary.xlsx
│   └── Uber_Supply_Demand_Insights.pdf
├── plots/
├── sql/
│   └── UBER_By_SQL.sql
├── notebooks/
│   └── Sample_EDA_Submission_Template.ipynb
├── docs/
├── assets/
│   ├── supply_demand_gap.png
│   ├── architecture_diagram.png
│   └── flow_diagram.png
├── uber_eda.py
├── requirements.txt
└── LICENSE
```

---

## 📖 Usage Guide

### For Analysts
```bash
python uber_eda.py
open outputs/Uber_Supply_Demand_Insights.pdf
```

### For Data Scientists
```python
df = pd.read_csv('data/Uber.csv')
hourly = pd.read_csv('outputs/hourly_gap_summary.csv')
```

### For DBAs
```sql
SELECT COUNT(*) FROM uber_requests;
```

---

## 🚀 Future Enhancements

### Phase 2 — Advanced Analytics
- Cancellation prediction ML model  
- Supply optimization algorithm  
- Geospatial clustering  

### Phase 3 — Interactive Dashboards
- Streamlit/Dash web app  
- Real-time KPIs  
- Slack/Teams alerts  

### Phase 4 — Cloud Deployment
- AWS/Azure migration  
- Docker + CI/CD  
- Distributed processing  

---

## 🤝 Contributing

### How to Contribute
```bash
git checkout -b feature/YourFeature
git commit -m "Add: Your feature"
git push origin feature/YourFeature
```

### Guidelines
- Follow PEP 8  
- Add tests  
- Update documentation  

---

## 📄 License

```
MIT License

Copyright (c) 2024 [Your Name]

Permission is hereby granted...
```

---

## 📞 Contact
**Your Name**  
- Email: your.email@example.com  
- LinkedIn: https://linkedin.com/in/yourprofile  
- GitHub: https://github.com/yourusername  
- Portfolio: https://yourportfolio.com  

---

## 📊 Project Stats

| Metric | Value |
|--------|--------|
| Total Requests | 6,745 |
| Gap | 3,914 (58%) |
| Peak Hour | 6 PM |
| Highest Gap Hour | 6 PM |
| Completion Rate | 42% |
| Cancellation Rate | 18.7% |
| Annual Opportunity | $17M–$22M |

---

<div align="center">


### 🚖 Empowering Urban Mobility Through Data

</div>

---
