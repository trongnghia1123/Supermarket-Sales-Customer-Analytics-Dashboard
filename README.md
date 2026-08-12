# Supermarket-Sales-Customer-Analytics-Dashboard

> **Data Analyst Portfolio Project — Sales & Business Performance Analysis**

An end-to-end **Data Analyst project** focused on analyzing retail sales performance, customer behavior, product performance, transaction patterns, and customer satisfaction using **Excel, Power Query, Power BI, and a Star Schema data model**.

The project demonstrates the complete analytical workflow from **data exploration and transformation to dashboard development, insight generation, and business recommendations**.

---

## 🎯 Project Overview

This project analyzes a retail sales dataset covering **1,000 transactions across 3 cities during the first three months of 2019**.

The main objective is to answer key business questions such as:

* How is sales performance changing over time?
* Which cities and product categories contribute most to sales?
* When are the peak purchasing periods?
* How do customer types and demographics differ across locations?
* Which product categories or locations have lower customer ratings?
* What business actions could be considered based on the observed patterns?

Rather than focusing only on visualization, the project follows a structured **EDA → ETL → Data Modeling → KPI → Analysis → Insight → Recommendation** workflow.

---

## 📌 Key Results

| Metric                   |             Result |
| ------------------------ | -----------------: |
| 💰 Total Sales           |      **~$322,967** |
| 📦 Transactions          |          **1,000** |
| 🧾 Average Invoice Value |       **~$322.97** |
| 📈 Gross Income          |       **~$15,379** |
| ⭐ Average Rating         |      **6.97 / 10** |
| 🏙️ Cities               |              **3** |
| 🛍️ Product Lines        |              **6** |
| 📅 Analysis Period       | **Jan – Mar 2019** |

### Key findings

* **January** recorded the highest sales, while **February** had the lowest sales before recovering in March.
* **19:00** was the strongest sales hour, followed by **13:00**.
* **Food and Beverages** generated the highest overall sales at approximately **$56K**.
* Product performance was relatively balanced, with the difference between the highest- and lowest-performing product lines being relatively small.
* Product preferences varied across cities, suggesting that customer demand is not completely homogeneous across locations.
* **Da Nang** recorded the lowest average customer rating among the three cities.
* **Home and Lifestyle** showed a relatively high concentration of lower ratings and therefore warrants further investigation.

> **Note:** Some findings represent signals or hypotheses that require additional historical, product-level, or operational data for further validation. The analysis intentionally avoids treating correlations as confirmed causal relationships.

---

# 🔎 Analytical Approach

The project follows five main stages.

### 1. Exploratory Data Analysis — EDA

The original CSV dataset was reviewed and a separate Excel copy was used for initial exploration.

The EDA process included:

* Understanding the meaning and relationships between fields
* Reviewing the dataset structure
* Checking data types and formats
* Identifying missing values
* Checking potential duplicate records
* Understanding the expected grain of the transaction table
* Reviewing business metrics and possible analytical dimensions

---

### 2. Data Transformation & ETL

**Power Query** was used to perform the ETL process.

The main fact table was transformed and supported by three dimension tables:

```text
                    ┌─────────────┐
                    │  Dim Date   │
                    └──────┬──────┘
                           │
                           │
┌─────────────┐     ┌──────▼──────┐     ┌─────────────┐
│  Dim Time   │────▶│  Fact Sales │◀────│ Dim Rating  │
└─────────────┘     └─────────────┘     └─────────────┘
```

Transformations included:

* Data type standardization
* Duplicate validation and removal where appropriate
* Creation of time-related attributes
* Creation of date/month attributes
* Rating grouping
* Correct chronological sorting of month names
* Correct ordering of time-of-day categories

---

### 3. Data Modeling

A **Star Schema** was implemented in Power BI.

The model consists of:

* **Fact Sales** — transaction-level business data
* **Dim Date** — date and month attributes
* **Dim Time** — hour and time-of-day attributes
* **Dim Rating** — rating categories

This structure allows the dashboard to perform flexible slicing and aggregation across different business dimensions while keeping the model organized and scalable.

---

### 4. KPI & Business Questions

Core KPIs were defined before dashboard development:

* Total Sales
* Gross Income
* Number of Invoices
* Average Invoice Value
* Average Customer Rating

The dashboard was then designed around specific analytical questions rather than simply creating visuals from available fields.

Examples:

> Which month generates the highest sales?

> Which product lines perform best?

> Which cities have the highest transaction volume?

> What are the peak purchasing hours?

> Are lower customer ratings concentrated in particular products, cities, or time periods?

---

### 5. Visualization, Insight & Recommendation

Power BI was used to transform the analytical results into an interactive sales dashboard.

The analysis covers:

* Monthly sales performance
* Sales by city
* Customer type
* Gender
* Payment method
* Product line
* Time of day
* Customer ratings
* City-level performance

The final stage connects observed patterns with potential business actions while distinguishing between **data-supported findings and hypotheses requiring further validation**.

---

# 📊 Dashboard

The Power BI dashboard provides an interactive overview of retail sales performance.

### Main dashboard sections

**Executive KPIs**

* Total Sales
* Gross Income
* Invoice Count
* Average Invoice
* Average Rating

**Sales Analysis**

* Monthly sales and invoice trends
* Sales by city
* Sales by product line
* Sales by time of day

**Customer Analysis**

* Customer type
* Gender
* Payment method
* Customer ratings

**Performance Detail**

* City-level sales
* Invoice volume
* Gross income
* Average rating

The dashboard can be filtered dynamically by dimensions such as:

* Month
* City
* Gender
* Product Line
* Customer Type
* Rating

---

# 💡 Business Insights & Recommendations

Several findings were identified during the analysis.

### 1. Monthly Sales

January generated the highest sales at approximately **$116K**, while February recorded the lowest at approximately **$97K**.

Although February showed a decline, the overall variation across the three months was not extreme.

**Potential action:**
Monitor historically weaker periods and consider targeted promotional campaigns to stimulate demand.

> The dataset covers only three months, so additional historical data would be required to confirm whether the February decline is driven by seasonality.

---

### 2. Peak Sales Hours

Sales were concentrated around **13:00 and 19:00**, with 19:00 generating approximately **$40K** in sales.

**Potential action:**
Consider aligning promotional activities, staffing levels, and operational capacity with peak purchasing periods.

---

### 3. Product Line Performance

**Food and Beverages** generated the highest overall sales at approximately **$56K**, followed closely by **Sports and Travel**.

However, the difference between the highest- and lowest-performing product lines was relatively small, suggesting that sales were distributed fairly evenly across categories.

**Potential action:**
Avoid relying solely on overall sales ranking. Further analysis of margin, quantity, SKU-level performance, and customer segments could identify more meaningful opportunities.

---

### 4. Geographic Differences

The leading product category differs across cities.

For example:

* **Ho Chi Minh City:** Home and Lifestyle
* **Da Nang:** Sports and Travel

This suggests that product preferences may vary by location.

**Potential action:**
Consider localized product and marketing strategies rather than applying the same category strategy across all markets.

> Additional customer demographic and historical data would be useful to validate the underlying reasons for these differences.

---

### 5. Customer Rating

The overall average rating was approximately **6.97/10**, with **Da Nang** recording the lowest city-level average rating at approximately **6.82**.

Home and Lifestyle also showed a relatively high concentration of lower ratings.

**Potential action:**
Prioritize further investigation into customer feedback, product quality, service experience, and branch-level operations in these areas.

---

# 📁 Repository Structure

```text
Retail-Sales-Performance-Analysis/
│
├── 📊 Retail Sales Performance Analysis.pbix
│   └── Interactive Power BI dashboard and data model
│
├── 📄 Summary document.docx
│   └── Detailed analysis, key insights and business recommendations
│
├── 📝 Additional notes.docx
│   └── Additional project methodology, analytical notes and supporting information
│
├── 📋 sale_data.csv
│   └── Original retail transaction dataset
│
└── 📖 README.md
    └── Project overview and documentation
```

---

# 📚 Project Documentation

The README provides a concise overview of the project.

For a deeper understanding of the analytical process and findings, please refer to the supporting documents included in this repository:

### 📄 [Summary document.docx](./Summary%20document.docx)

Contains the **detailed analytical summary**, including:

* Overall business performance
* Key findings by month
* Time-of-day analysis
* Product line analysis
* City-level analysis
* Customer rating analysis
* Business observations
* Recommendations based on the findings

### 📝 [Additional notes.docx](./Additional%20notes.docx)

Contains **additional project notes and supporting analysis**, providing more context behind the methodology and analytical decisions used throughout the project.

> **Recommended reading order:**
> **README → Summary document → Additional notes → Power BI dashboard**

---

# 🛠️ Tools & Technologies

| Tool            | Purpose                                                     |
| --------------- | ----------------------------------------------------------- |
| **Excel**       | Initial data exploration and validation                     |
| **Power Query** | Data transformation and ETL                                 |
| **Power BI**    | Data modeling, DAX, visualization and dashboard development |
| **CSV**         | Source transaction data                                     |
| **Star Schema** | Analytical data modeling                                    |

---

# 📈 Skills Demonstrated

This project demonstrates the following Data Analyst capabilities:

### Data Preparation

* Exploratory Data Analysis
* Data quality checking
* Data type validation
* Duplicate handling
* Data transformation
* ETL using Power Query

### Data Modeling

* Fact and dimension table design
* Star Schema
* Relationships between tables
* Time-based analytical modeling

### Business Analysis

* KPI definition
* Business question formulation
* Sales performance analysis
* Customer segmentation
* Product analysis
* Geographic analysis
* Time-based analysis
* Customer satisfaction analysis

### Data Visualization

* Interactive Power BI dashboard
* KPI cards
* Trend analysis
* Comparative analysis
* Drill-down analysis
* Slicers and dynamic filtering

### Analytical Thinking

* Identifying patterns and anomalies
* Translating data into business insights
* Distinguishing observations from hypotheses
* Developing data-driven recommendations

---

# 🎯 Key Takeaway

This project demonstrates an end-to-end approach to solving a business analytics problem:

```text
Raw Data
   ↓
EDA
   ↓
Data Cleaning & Transformation
   ↓
Data Modeling
   ↓
KPI Definition
   ↓
Business Questions
   ↓
Data Visualization
   ↓
Insight
   ↓
Business Recommendation
```

The goal is not simply to build a visually appealing dashboard, but to demonstrate how a Data Analyst can transform raw transaction data into **structured information, actionable insights, and potential business decisions**.

---

## 👤 Project Type

**Data Analyst Portfolio Project**

**Domain:** Retail / Sales / Business Performance
**Dataset:** Retail Transaction Data
**Analysis Period:** January – March 2019
**Primary Tool:** Microsoft Power BI

---

⭐ **If you are reviewing this project, I recommend opening the `.pbix` file together with the `Summary document.docx` to see both the interactive dashboard and the analytical reasoning behind it.**
