# 🍕 Pizza Sales Analysis Dashboard

### 📘 Project Overview
This Power BI project analyzes pizza sales to understand revenue trends, product performance, and customer purchase behavior.  
The dashboard visualizes sales by category, size, and pizza type, helping stakeholders make data-driven decisions.

---

### 🎯 Objectives
- Track **total revenue**, **total quantity sold**, and **average order value**
- Identify **top-selling pizzas**, **categories**, and **size performance**
- Understand **monthly revenue trends** and seasonal patterns
- Provide insights to improve product mix and marketing strategy

---

### 🧰 Tools & Technologies
- **Power BI** – Data modeling, DAX, reports
- **Power Query** – Data transformation (ETL)
- **Excel / CSV** – Raw data

---

### 🧩 Dataset Description
- **Source:** Store sales dataset (CSV)
- **Records:** ~21,000 rows

---

#### Key Fields
| Field | Description |
|-------|-------------|
| pizza_id | Pizza identifier |
| pizza_name | Product name |
| pizza_category | Category (Classic, Supreme, etc.) |
| pizza_size | Small / Medium / Large |
| quantity | Units sold |
| unit_price | Price per item |
| order_date | Date of purchase |
| order_time | Time of purchase |
| total_amount | unit_price × quantity |

---

#### Data Cleaning
✅ Date & time formatting  
✅ Created Month & Month Name  
✅ Created Order Period (Morning / Afternoon / Evening / Night)  
✅ Computed Total Amount  
✅ Removed duplicates & nulls  

---


### ⚙️ Data Modeling & DAX Measures

```DAX
-- Total Revenue
Total Revenue = SUM('Pizza'[total_amount])

-- Total Quantity Sold
Total Quantity = SUM('Pizza'[quantity])

-- Average Order Value
Average Order Value =
DIVIDE(
    [Total Revenue],
    DISTINCTCOUNT('Pizza'[order_id])
)

---


### Key Insights
- Total Revenue: ₹3,53,504+  
- Total Quantity Sold: 21,581+  
- Average Order Value: ₹17  

- Large pizzas contribute ~45% of total revenue, making them the most preferred and high-value product  
- Medium pizzas contribute ~31%, while Small account for ~24%  
- Chicken category generates the highest revenue (~₹110K), followed by Classic (~₹97K), Supreme, and Veggie  
- Barbecue Chicken Pizza is the top performer (~₹41K), followed by California Chicken Pizza and Classic Deluxe Pizza  
- July is the highest-revenue month; October is the lowest, suggesting promotion opportunities  
- Sales peak during Evening & Afternoon, ideal for combos and promo campaigns  
- Revenue is concentrated among a few top pizzas → top 5 contribute a major portion → prioritize inventory  
- Veggie pizzas contribute less → opportunity for new recipes, discount offers, or marketing  
- Customers prefer premium & large products → higher revenue per order

---


###  🖼️ Dashboard Preview
C:\Users\Koteswarao\OneDrive\Pictures\Screenshots\Pizza Sales dashboard pic

---


###  🧠 What I Learned

- Creating DAX measures for KPIs
- Developing star-schema relationships
- Time-based analysis & modeling
- Designing business-ready dashboards
- Converting raw data → usable insights

---


### 📈 Business Impact

- Identified top products & categories driving revenue
- Seasonal performance uncovered → aids inventory planning
- Prioritized profitable SKUs → strengthens menu strategy
- Recommended marketing focus based on demand timing

---


###  🧩 Repository Structure
Pizza_Sales_Analysis/
│
├── data/
│   └── pizza_sales.csv
├── dashboard/
│   └── pizza_sales.pbix
├── images/
│   └── pizza_dashboard.png
└── README.md

---


###  📬 Contact
Koteswara Rao Mallela
📧 kotimallela0415@gmail.com

🔗 LinkedIn: https://www.linkedin.com/in/koti2018

🔗 GitHub: https://github.com/KoteswaraRao-Mallela
