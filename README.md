# 📊 AI-Powered Customer Churn Analytics Dashboard

An interactive Power BI dashboard that analyzes telecom customer data to identify **which customers are likely to churn**, understand **why**, and highlight the **highest-risk, highest-value accounts** so the business can act before losing them.

---

## 📌 Overview

Customer churn — when a subscriber stops using a service — is one of the biggest revenue risks for subscription-based businesses. This project turns raw customer data into a churn probability score and risk category, then visualizes it in Power BI so that patterns (which contract types churn most, which services are riskiest, which customers to save first) are easy to spot at a glance instead of buried in a spreadsheet.

**File:** `project_1.pbix`

---

## 🎯 Objective

- Identify customers with a high probability of churning.
- Understand which factors (contract type, internet service, tenure, monthly charges, gender) are associated with higher churn.
- Give the business a prioritized, ready-to-act list of top at-risk customers instead of raw data.

---

## 📁 Dataset

The dashboard runs on a customer table (`powerbi_churn_data`) with the following fields:

| Column | Description |
|---|---|
| `customerID` | Unique identifier for each customer |
| `gender` | Customer's gender |
| `Contract` | Contract type (e.g., Month-to-month, One year, Two year) |
| `InternetService` | Type of internet service subscribed |
| `tenure` | Number of months the customer has stayed with the company |
| `MonthlyCharges` | Amount billed to the customer monthly |
| `Churn` | Whether the customer has already churned (Yes/No) |
| `ChurnProbability` | Model-predicted probability that the customer will churn |
| `RiskCategory` | Risk bucket derived from `ChurnProbability` (e.g., Low / Medium / High) |

> 📝 **To fill in:** add the original source of this dataset here (e.g., link to the Kaggle/IBM Telco Customer Churn dataset if that's what was used), and briefly describe how `ChurnProbability` and `RiskCategory` were generated — for example, "Predicted using a logistic regression / random forest model trained in Python on historical churn data, then imported into Power BI" or "Calculated using DAX logic based on tenure and contract type." This is the one part only you know the details of.

---

## 📊 Dashboard Pages

### 1. Executive Summary
A quick, top-level view for anyone opening the report for the first time:
- **KPI cards:** Total Customers, Churned Customers, Churn Rate, High Risk Customers
- **Donut chart:** Customer split by Risk Category
- **100% stacked column chart:** Churn outcome by Contract type

### 2. Churn Analysis
A deeper look at *why* customers churn:
- **Slicers:** Contract, Churn, Gender, Internet Service, Risk Category (to filter the whole page)
- **100% stacked column charts:** Churn by Gender, Churn by Contract type
- **Donut chart:** Customer split by Internet Service type
- **Clustered column chart:** Customer count by Contract and Churn status
- **100% stacked column chart:** Monthly Charges distribution by Churn status

### 3. Top Customers Likely to Churn
An action-ready view for the retention/sales team:
- **Table:** Customers ranked by Churn Probability, showing Customer ID, Risk Category, Monthly Charges, Tenure, Contract, and Internet Service
- **Donut & column charts:** Risk Category breakdown, and average Churn Probability by Contract type and Internet Service type
- **Slicers:** Contract, Internet Service, Risk Category — to drill into a specific segment of at-risk customers

---

## 🧮 Key Measures (DAX)

| Measure | What it shows |
|---|---|
| `Total Customers` | Total count of customers in the dataset |
| `Churned Customers` | Count of customers where `Churn = Yes` |
| `Churn Rate` | Churned Customers ÷ Total Customers |
| `High Risk Customers` | Count of customers flagged as high risk |

---

## 🛠️ Tech Stack

- **Power BI Desktop** — data modeling, DAX measures, and report visuals
- **DAX** — for the KPI measures above
- *(Add here if used: Python/Excel for generating `ChurnProbability`, and the data source system)*

---

## 🚀 How to Use

1. Clone this repository:
   ```bash
   git clone <your-repo-url>
   ```
2. Open `project_1.pbix` in **Power BI Desktop** (free download from Microsoft).
3. If the data source needs refreshing, go to **Home → Refresh**.
4. Use the **page tabs** at the bottom (Executive Summary / Churn Analysis / Top Customers Likely to Churn) to navigate.
5. Use the **slicers** on each page to filter by Contract, Internet Service, Gender, or Risk Category.

---

## 📂 Repository Structure

```
├── project_1.pbix     # Power BI report file
└── README.md          # Project documentation (this file)
```

---

## 📸 Screenshots

> Add a few screenshots of each page here once exported from Power BI (File → Export → Export to Image, or a simple screen capture), so the dashboard is visible directly on GitHub without needing to open the file:
>
> ```markdown
> ![Executive Summary](screenshots/executive-summary.png)
> ![Churn Analysis](screenshots/churn-analysis.png)
> ![Top Customers Likely to Churn](screenshots/top-customers.png)
> ```

---

## 🔮 Future Enhancements

- Connect to a live/refreshable data source instead of a static import.
- Publish the report to the Power BI Service and embed it, or share a live link.
- Add a "reason for churn risk" explanation per customer (e.g., top contributing factors).
- Set up automated alerts when a high-value customer crosses into the High Risk category.

---

## 🙋 Author

*(Add your name, course/program, and college here — e.g., "Amrita Vishwa Vidyapeetham")*
