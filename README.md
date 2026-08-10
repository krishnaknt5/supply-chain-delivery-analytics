# 📦 Supply Chain Delivery Performance & Profitability Analytics

An end-to-end Python data analytics project that diagnoses **why orders are delivered late**, quantifies the **financial impact of delays**, and builds a **machine learning model** to predict late-delivery risk — using the DataCo Global Supply Chain dataset.

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458)
![Scikit--learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📌 Project Overview

Late deliveries quietly damage e-commerce and logistics businesses in three ways: they erode customer trust, shrink order-level profitability through recovery costs, and make it impossible to set reliable delivery-date promises. This project builds a **complete, reproducible analytics pipeline** in Python to measure, explain, and predict this problem.

The analysis moves through four layers of maturity:

| Layer | Question Answered | Techniques Used |
|---|---|---|
| **Descriptive** | What happened? | KPI dashboards, profitability breakdown |
| **Diagnostic** | Why did it happen? | Bottleneck detection, root-cause analysis |
| **Temporal** | When does it happen? | Monthly / weekly / hourly delay trends |
| **Predictive** | What will happen next? | Random Forest classifier for late-delivery risk |

---

## 🎯 Objectives

- Quantify the scale of the late-delivery problem with clear KPIs
- Break down order profitability into Profit / Loss / Breakeven segments
- Identify the regions, shipping modes, order types, and departments driving delay
- Uncover time-based delay patterns (month, day of week, hour)
- Train and evaluate a machine learning model to flag high-risk orders
- Translate every finding into actionable business recommendations

---

## 🗂️ Dataset

**DataCo Global Supply Chain Dataset** — a real-world, order-level dataset covering:
- Order & shipping dates, scheduled shipment windows
- Shipping mode, customer segment, order region, order status
- Product category & department, payment type
- Order-level profit

> Dataset source: [Kaggle – DataCo Supply Chain Dataset](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)

---

## 🛠️ Tech Stack

- **Language:** Python 3.12
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** Scikit-learn (Random Forest Classifier)
- **Class Imbalance Handling:** imbalanced-learn (SMOTE)
- **Environment:** Jupyter Notebook

---

## 🔄 Workflow

1. **Data Cleaning** — dropped PII and redundant columns, removed cancelled shipments, converted date fields
2. **Feature Engineering** — computed `Order Processing Time`, `Delay`, `Is_Delayed`, `order_month`, `order_day`, `order_hour`, `Profitability Flag`
3. **KPI Calculation** — on-time %, late %, 90th-percentile delay, total profit, delay-linked loss
4. **Exploratory Data Analysis** — profitability distribution, delay distribution, delay % across 6 business dimensions
5. **Root Cause Analysis** — top delay drivers per region (shipping mode, order status, department, etc.)
6. **Time-Based Analysis** — delay trends by month, day of week, and hour
7. **Machine Learning** — frequency encoding → train/test split → SMOTE balancing → Random Forest → evaluation

---

## 📊 Key Insights

- **First Class** shipments are late **100%** of the time; **Second Class** ~80%, vs. only ~40% for Standard Class
- **Central Africa, Southeast Asia, and Eastern Europe** are the most delay-prone regions
- **~81%** of orders are profitable, but **~19%** operate at a loss — losses concentrate among delayed orders
- Delay peaks on **Mondays** and around **midday/evening** order windows
- A **Random Forest classifier** predicts late-delivery risk with **~74% accuracy**

---

## 🤖 Machine Learning Model

| Metric | Score |
|---|---|
| Accuracy | ~0.74 |
| Precision | ~0.73 |
| Recall | ~0.75 |
| F1-Score | ~0.74 |

**Features used:** Order Type, Days for Shipment (scheduled), Category Name, Customer Segment, Department Name, Order Region, Shipping Mode, Order Month, Order Hour
**Balancing:** SMOTE oversampling on the training set
**Model:** RandomForestClassifier (scikit-learn,`random_state=42`)

---

## 📁 Repository Structure

```
supply-chain-delivery-analytics/
│
├── data/
│   └── DataCoSupplyChainDataset.csv
│
├── notebook/
│   └── supply_chain_analysis.ipynb
│
├── reports/
│   └── Supply_Chain_Analytics_Report.docx
│
├── images/
│   └── (exported charts/screenshots)
│
├── README.md
└── requirements.txt
```

---

## ⚙️ Installation & Usage

```bash
# Clone the repository
git clone https://github.com/krishnaknt5/supply-chain-delivery-analytics.git
cd supply-chain-delivery-analytics

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook notebook/supply_chain_analysis.ipynb
```

**requirements.txt**
```
pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
jupyter
```

---

## 📈 Strategic Recommendations

1. **Renegotiate First/Second Class carrier SLAs** — the single highest-leverage fix
2. **Automate order-status workflows** (PAYMENT_REVIEW, PENDING, ON_HOLD escalation)
3. **Align staffing with peak-delay windows** (Monday mornings, midday/evening)
4. **Invest in regional fulfillment capacity** for Central Africa, Southeast Asia, Eastern Europe
5. **Deploy the ML model operationally** as a real-time risk score at checkout
6. **Add profitability guardrails** for high-risk-shipping + low-margin order combinations

---

## 👤 Author

**Krishna Kanta Das**
B.E. Information Science Engineering | Expected Graduation: May 2027
Aspiring Data Analyst

---

## 📄 License

This project is open-sourced for educational and portfolio purposes.
