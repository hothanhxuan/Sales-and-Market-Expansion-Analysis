# 🌍 Project 2: Global Superstore Sales Performance & Market Expansion Dashboard (PowerBI)


**Domain:**  
Sales Analytics (Sales Strategy Department)

![Image](https://github.com/user-attachments/assets/af75f445-54fb-4dbe-8967-082ceaf9d210)

Author: Susan Ho  
Date: 2025-12-10  
Tools Used: Power BI  

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [⚒️ Main Process](#️-main-process)  
5. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
6. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview
The goal of this project is to build an **analytic dashboard** using Power BI.  
Through this project, we will practice:
- Understanding stakeholder reporting needs.  
- Designing dashboard layout, structure, and color themes.  
- Building interactions within reports.  
- Creating structured content with clear messaging.  
- Reviewing and continuously improving dashboards.
  
### 👤 Project Audience
This project is built for:
- **Senior Managers & Business Leaders** who need a clear, data-driven view of business performance to support market expansion and product strategy
- **Data Analysts / Business Analysts** as a demonstration of end-to-end analytical thinking, from business understanding to insight-driven recommendations
- **Recruiters & Hiring Managers** evaluating skills in data modeling, KPI design, Power BI storytelling, and strategic analysis

### 🏢 Business Context and ❓Question 
Superstore is a global retail company operating across multiple markets worldwide. 
As the company experiences rapid growth, senior management requires consolidated insights to answer three critical business questions: 
  1. What is the current overall business performance? 
  2. Which markets should be prioritized for expansion? 
  3. Which product categories and SKUs drive profit — and which erode it?
 
This project transforms raw transactional data into a decision-support Power BI dashboard, enabling leadership to shift from high-level reporting to actionable, strategy-focused insights. 

### 🎯Project Outcome:
- **Revenue increased significantly, but profit margins remained broadly flat**, confirming a scale-driven growth pattern rather than efficiency-led improvement. Total revenue reached **$12.64M**, while overall margin held at **11.61%**. In 2014 alone, revenue grew **+26.25% YoY**, but margin declined slightly by **0.23 pp**, indicating rising cost pressure and discount-driven growth.

- the United States continues to dominate total revenue and profit, but **Canada** stands out as as **a high-margin niche market** (~28%) despite modest sales volume, indicating pricing power or lower fulfillment costs.
  
- **Africa (+23.56% YoY)** and **EMEA (+47.42% YoY)**  recorded the fastest year-over-year growth, highlighting clear expansion potential, although margin volatility suggests the need for tighter cost and logistics control before scaling further.
  
- New customer acquisition remained structurally weak, with only 15 new customers in 2014 (0.99%). However, **Oceania and Africa attracted a disproportionately higher share of new customers**, while **99.01% of total revenue continued to come from loyal, returning buyers**. Repeat purchase behavior strengthened, with the repeat-customer rate rising from 82.03% (2013) to 87.62% (2014).
  
- **Technology led both revenue growth and profitability**, generating $4.74M in sales and $663.8K in profit (13.99% margin), accounting for the largest share of total profit. However, return rates in selected technology SKUs—notably printers and advanced equipment—materially diluted margins, as evidenced by loss-making products with margins as low as -80%.
  
- **Copiers delivered the highest profit per unit**, with margins reaching 17.13% and flagship SKUs such as *Canon imageCLASS 2200* achieving 40.91% margin. Conversely, **low-performing items such as Tables (-8.47% margin)** and specific Furniture and Machinery SKUs destroyed value, collectively dragging Furniture category margin down to 6.94%, less than half that of Technology or Office Supplies.


---

## 📂 Dataset Description & Data Structure
### 🔍 Data source Overview
- **Source**: Kaggle
- **Size**: The Orders table contains 51,290 records.
- **Format**: CSV
  
The analysis is based on three datasets: 

| Dataset | Description                                                  | Records  |
|--------|---------------------------------------------------------------|----------|
| Orders | Contains detailed transaction and customer information        | 51,290  |
| People | Sales representatives by region                               | 13       |
| Returns| Returned order records                                        | 1,100   |

Together, these datasets provide visibility into sales performance, people contribution, and operational risk through returns.

### 📊 Data structure 
- 🛒 **Table 1: Orders**
  
| Column Name       | Data Type   | Description                              |
|------------------|------------|------------------------------------------|
| `Order ID`      | `VARCHAR`   | Unique identifier for each order.       |
| `Order Date`    | `DATE`      | Date when the order was placed.         |
| `Ship Date`     | `DATE`      | Date when the order was shipped.        |
| `Ship Mode`     | `VARCHAR`   | Shipping method used for delivery.      |
| `Customer ID`   | `VARCHAR`   | Unique identifier for each customer.    |
| `Customer Name` | `VARCHAR`   | Full name of the customer.              |
| `Segment`       | `VARCHAR`   | Customer segment (e.g., Consumer, Corporate). |
| `City`         | `VARCHAR`   | City where the order was placed.        |
| `State`        | `VARCHAR`   | State where the order was placed.       |
| `Country`      | `VARCHAR`   | Country where the order was placed.     |
| `Postal Code`  | `VARCHAR`   | Postal code of the shipping address.    |
| `Market`       | `VARCHAR`   | Market region (e.g., APAC, EMEA).       |
| `Region`       | `VARCHAR`   | Geographical region of the order.       |
| `Product ID`   | `VARCHAR`   | Unique identifier for each product.     |
| `Category`     | `VARCHAR`   | Product category (e.g., Furniture, Office Supplies). |
| `Sub-Category` | `VARCHAR`   | Sub-category of the product.            |
| `Product Name` | `VARCHAR`   | Name of the product ordered.            |
| `Sales`        | `DECIMAL`   | Revenue generated from the order.       |
| `Quantity`     | `INT`       | Number of items ordered.                |
| `Profit`       | `DECIMAL`   | Profit earned from the order.           |


- 🔄 **Table 2: Returns**
  
| Column Name  | Data Type | Description |
|--------------|-----------|-------------|
| `Returned`   | `VARCHAR` | Indicates whether the order was returned (e.g., 'Yes' or 'No'). |
| `Order ID`   | `VARCHAR` | Unique identifier for each order. |

  
- 👥 **Table 3: People**
  
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Person`    | `VARCHAR` | Name of the salesperson. |
| `Region`    | `VARCHAR` | Geographic region where the salesperson operates. |


### 🔗 Data Relationships & Model Design
The Power BI data model follows a **fact–dimension structure** to support efficient analysis and reporting.

#### Data Model Structure
- **Orders** → Central **fact table**
- **People** and **Returns** → supporting dimension table 

#### Table Relationships
![Image](https://github.com/user-attachments/assets/17a70658-b5c5-44d1-bd94-d745a4ce61c1)

| From Table | To Table | Join Key  | Relationship Type |
|-----------|----------|-----------|-------------------|
| Orders    | People   | Region    | Many-to-One (multiple orders belong to one region) |
| Orders    | Returns  | Order ID  | One-to-One or Left Join (not all orders are returned) |

#### ✅ Analytical Capabilities
This data model enables flexible slicing and filtering across:
- Time
- Market
- Region
- Category
- Product
- Salesperson

#### 🛠️ Workflow
1. Review the project brief and dataset.  
2. Complete the **Empathy** section in the Design Thinking file.  
3. Explore reference dashboards (Power BI, Tableau, Maven).  
4. Work on **Point of View** and **Ideate**.  
5. Learn about color theory and select a theme.  
6. Build **Version 1** dashboard.  
7. Continuously refine by **switching perspective as a stakeholder**.  
8. Build **Version 2** and validate against Design Thinking iterations.  
9. Finalize **Version 3**.  

#### 🎨 Resources
- **Color & Themes**  
  - [ColorSpace](https://mycolor.space/)  
  - [Coolors](https://coolors.co/)  
  - [Data Viz Color Palette Generator](https://learnui.design/tools/data-color-picker.html)  
- **Tutorial Videos**  
  - [How to Choose Colors](https://www.youtube.com/watch?v=JDs7IP4cAxE)  
  - [Importing Themes in Power BI](https://www.youtube.com/watch?v=3JDs7IP4cAxE)  
  - [Bar Chart Customization](https://www.youtube.com/watch?v=8h2r8ZrYvK4)  
- **Reference Dashboards**  
  - [Power BI Theme Gallery](https://community.fabric.microsoft.com/t5/Themes-Gallery/bd-p/ThemesGallery)  

---

## 🧠 Design Thinking Process

---

## ⚒️ Main Process

---

## 📊 Key Insights & Visualizations
### I. Dashboard Executive Summary
![Image](https://github.com/user-attachments/assets/d4807d75-1c5a-4130-9c11-21025e704e46)


### II. Dashboad Market Analysis
![Image](https://github.com/user-attachments/assets/4c4125f4-6d3a-4200-be24-d8d3a688ba5f)


### III. Dashboard Product Analysis 
![Image](https://github.com/user-attachments/assets/9f264013-a195-4f8f-a788-b299aac015c6)
![Image](https://github.com/user-attachments/assets/e6f0eecb-ddef-4f62-bdf2-8eb88cad85c6)


---

## 🔎 Final Conclusion & Recommendations
📌 Final Note
> *“This project is an opportunity to create a professional portfolio dashboard.  
> Always put yourself in the stakeholder’s shoes, and deliver reports that are clear, visually appealing, and rich with insights.”*  
