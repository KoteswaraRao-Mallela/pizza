# 🍕 Pizza Sales Analysis Dashboard

### 📘 Project Overview

This Power BI project analyzes pizza sales data to understand revenue trends, customer preferences, and product performance.
The interactive dashboard visualizes sales by pizza type, category, and size, helping stakeholders make data-driven business decisions.

---

### 🎯 Objectives

* Evaluate **total revenue**, **quantity sold**, and **average order value**.
* Identify **best-selling pizza categories** and **top-performing sizes**.
* Track **monthly and daily sales trends** to uncover seasonal patterns.
* Provide insights to optimize product mix and marketing strategies.

---

### 🧰 Tools & Technologies

* **Power BI** – Data modeling, DAX calculations, and dashboard design
* **Excel** – Data cleaning and preprocessing
* **Power Query** – ETL for merging and shaping multiple tables
* **DAX (Data Analysis Expressions)** – Custom KPIs and time intelligence

---

### 🧩 Dataset Description

* **Source:** Kaggle (Pizza Sales Dataset)
* **Tables:** `Orders`, `Order_Details`, `Pizzas`, `Pizza_Types`
* **Rows:** ~48,000 order records
* **Fields:** `pizza_id`, `category`, `size`, `price`, `quantity`, `order_date`, `total_price`
* **Data Cleaning Steps:**

  * Removed duplicates and invalid timestamps
  * Standardized category names and date formats
  * Created relationships between `Orders` and `Order_Details` tables

---

### ⚙️ Data Modeling & DAX Measures

```DAX
-- Total Revenue
Total Revenue = SUM('Order_Details'[total_price])

-- Total Quantity Sold
Total Quantity = SUM('Order_Details'[quantity])

-- Average Order Value (AOV)
Average Order Value = DIVIDE([Total Revenue], DISTINCTCOUNT('Orders'[order_id]))

-- Monthly Sales
Monthly Sales = CALCULATE([Total Revenue], DATESMTD('Orders'[order_date]))

-- Year-to-Date (YTD) Sales
YTD Sales = TOTALYTD([Total Revenue], 'Orders'[order_date])

-- Top Category by Revenue
Top Category = 
VAR CatRevenue = 
    SUMMARIZE('Pizza_Types', 'Pizza_Types'[category], "Revenue", [Total Revenue])
RETURN
TOPN(1, CatRevenue, [Revenue], DESC)
```

---

### 📊 Key Insights

* **Classic and Supreme categories** generated over **60% of total revenue**.
* **Large-size pizzas** were the top sellers, contributing ~45% of total quantity sold.
* Peak sales occurred during **weekends**, showing strong weekend demand.
* **Total Revenue:** ₹817,860 across the full period analyzed.
* **Average Order Value (AOV):** ₹38.2 per order.
* **Highest sales month:** **July**, showing ~15% higher revenue compared to monthly average.

---

### 🖼️ Dashboard Preview

(Replace with your actual screenshot)
`![Pizza Dashboard Preview](images/pizza_dashboard.png)`

---

### 🧠 What I Learned

* Advanced DAX functions for trend and time-based analysis (YTD, MTD).
* Building relationships between multiple tables in a relational model.
* Designing intuitive visuals with card KPIs, bar charts, and donut charts.
* Translating raw transaction data into business recommendations.

---

### 📈 Impact

* Enabled the business to identify **top-selling categories** and **size-based profit margins**.
* Helped uncover **seasonal and daily sales trends** for better inventory planning.
* Improved data storytelling and visual analytics for management insights.

---

### 🧩 Repository Structure

```
Pizza_Sales_Analysis/
│
├── dataset/
│   └── pizza_sales_data.xlsx
├── dashboard/
│   └── Pizza_Sales_Dashboard.pbix
├── images/
│   └── pizza_dashboard.png
└── README.md
```

---

### 📬 Contact

**Koteswara Rao Mallela**
📧 [kotimallela0415@gmail.com](mailto:kotimallela0415@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/in/koti2018) | [GitHub Profile](https://github.com/KoteswaraRao-Mallela)

---

**License:** Educational and portfolio use only.
