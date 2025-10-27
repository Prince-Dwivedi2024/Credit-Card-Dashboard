# Credit Card Dashboard

## 📊 Project Overview

The **Credit Card Dashboard** is an interactive business intelligence solution developed using **Power BI** and **SQL** to analyze customer spending patterns, card usage behavior, and revenue distribution.
It provides actionable insights into **monthly, quarterly, and yearly spending trends**, helping financial analysts and decision-makers identify seasonal variations and optimize business strategies.

---

## 🧠 Objectives

* **Track total spending** over time (monthly, quarterly, yearly) to detect seasonal peaks and behavioral shifts.
* **Visualize revenue breakdown** by expenditure category, card type, and customer segment.
* **Analyze shifts in spending patterns** across categories to support strategic financial decisions.
* **Enable data-driven decision making** through intuitive and dynamic Power BI dashboards.

---

## 🧩 Tech Stack

| Tool                         | Purpose                                               |
| ---------------------------- | ----------------------------------------------------- |
| **SQL (MySQL / PostgreSQL)** | Data extraction, cleaning, transformation             |
| **Power BI**                 | Dashboard creation and interactive data visualization |
| **Excel / CSVs**             | Data import, preprocessing, and validation            |

---

## 🗂️ Project Structure

```
Credit-Card-Dashboard/
│
├── data/
│   ├── customer.csv
│   ├── credit_card.csv
│   ├── cc_add.csv
│   ├── cust_add.csv
│
├── reports/
│   ├── creditcard_CustomerReport.pdf
│   ├── creditcard_TransactionReport.pdf
│
├── sql/
│   ├── create_tables.sql
│   ├── data_cleaning_queries.sql
│   ├── analysis_queries.sql
│
└── README.md
```

---

## 🧮 Data Model

The dashboard integrates **four key datasets**, connected via the `Client_Num` primary key:

| Table               | Description                                   | Key Columns                                                            |
| ------------------- | --------------------------------------------- | ---------------------------------------------------------------------- |
| **customer.csv**    | Customer demographic data                     | `Client_Num`, `Gender`, `Age`, `Income`, `State`, `Satisfaction_Score` |
| **credit_card.csv** | Card-level information                        | `Client_Num`, `Card_Category`, `Credit_Limit`, `Avg_Utilization_Ratio` |
| **cc_add.csv**      | Transaction-level metrics (weekly aggregates) | `Client_Num`, `Total_Trans_Amt`, `Total_Revolving_Bal`                 |
| **cust_add.csv**    | Address and geographic details                | `Client_Num`, `State`, `Zipcode`                                       |

**Relationships:**

```
customer (1) —— (1) credit_card
customer (1) —— (1) cc_add
customer (1) —— (1) cust_add
```

---

## 📈 Dashboard Insights

Below are the key insights visualized and analyzed in Power BI:

### 1. Spending Trends Over Time

* Total spending visualized **monthly, quarterly, and yearly**.
* Clear **seasonal peaks** observed during festive months.
* Year-over-year growth tracked to identify **customer activity trends**.

### 2. Spending Breakdown by Category

* Revenue segmented by:

  * **Expenditure Type** (Travel, Groceries, Bills, etc.)
  * **Card Type** (Blue, Silver, Gold, Platinum)
  * **Customer Level** (Standard, Premium, Corporate)
* Helps identify which categories contribute most to total spending and profit.

### 3. Customer Behavior Analysis

* Average **income and age distribution** by card category.
* **Gender-based insights** show purchasing preference differences.
* **Customer Satisfaction Score** visualized against spending volume and card type.

### 4. Transaction Performance

* Monitored **Total Transaction Amount (TTA)**, **Total Revolving Balance**, and **Utilization Ratio**.
* KPI cards and trend lines for:

  * Average transaction size
  * Active customer ratio
  * Top performing states by spending

---

## 🧑‍💻 SQL Query Highlights

Example analytical queries used for data processing:

```sql
-- Monthly spending by card type
SELECT
    DATE_FORMAT(Transaction_Date, '%Y-%m') AS Month,
    Card_Category,
    SUM(Transaction_Amount) AS Total_Spending
FROM credit_card_transactions
GROUP BY Month, Card_Category
ORDER BY Month;

-- Revenue by expenditure type
SELECT
    Expenditure_Type,
    SUM(Transaction_Amount) AS Revenue
FROM credit_card_transactions
GROUP BY Expenditure_Type
ORDER BY Revenue DESC;
```

---

## 💡 Business Impact

* Enabled **data-driven budgeting** and **marketing strategies**.
* Helped identify **high-spending customer segments**.
* Provided visibility into **seasonal spending cycles** and category-level profitability.
* Supported executive decision-making with **real-time visualization and drill-through analytics**.

---

## ⚙️ Future Enhancements

* Integrate **real-time SQL connections** for live dashboard refresh.
* Add **predictive analytics layer** (Power BI + Python) for forecasting spending trends.
* Include **customer churn prediction** metrics.
* Deploy dashboard on **Power BI Service** with role-based access.

---

## 🧾 Reports

* **Customer Report:** creditcard_CustomerReport.pdf
  → Contains demographic and satisfaction insights.
* **Transaction Report:** creditcard_TransactionReport.pdf
  → Displays transaction volumes, revenue, and utilization KPIs.

---

## 🧑‍🏫 Author

**Prince Dwivedi**
📍 National Institute of Technology, Rourkela
📧 [dwivediprince313@gmail.com](mailto:dwivediprince313@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/aayushmaan07) | [LeetCode](https://leetcode.com/)

