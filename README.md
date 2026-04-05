# 🌍 Project 2: Sales Performance & Market Expansion in Retail (Global Superstore) Dashboard | Power BI 

**Domain:**  
Sales Analytics in Retail (a multi-category retail business)

![Image](https://github.com/user-attachments/assets/af75f445-54fb-4dbe-8967-082ceaf9d210)

Author: Susan Ho  
Date: 2025-12-10  
Tools Used: Power BI  

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)
6. [💡 Deep dive into Canada Insights for EMEA Market Expansion](#deep-dive-into-canada-insights-for-emea-market-expansion)  
7. [✨ More information](#-more-information)

---

## 📌 Background & Overview
The goal of this project is to build an **analytic dashboard** using Power BI.  
Through this project, we:
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

This dataset provides detailed information about **international order transactions**. The business operates across multiple global markets, including **Asia-Pacific, Europe, and the Americas**. It allows for the analysis of business performance and consumer trends during the period from 2011 to 2014.

The data focuses on key elements such as **customer information, shipping times, and the geographic location of each order**. Products are clearly categorized into **technology, furniture, and office supplies**, featuring well-known brands such as Apple, Samsung, and Canon.

In addition, the dataset includes important financial indicators, such as sales revenue, costs, and overall profit, which support a deeper evaluation of business performance.

Together, these datasets provide visibility into sales performance, people contribution, and operational risk through returns.

### 📊 Data structure 
The analysis is based on three datasets:

- 🛒 **Table 1: Orders**. Contains detailed transaction and customer information, with 51,290 records.
<details>
  <summary>See details </summary>
  
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

</details>

- 🔄 **Table 2: Returns**. Sales representatives by region, with 13 records.
<details>
  <summary>See details </summary>
  
| Column Name  | Data Type | Description |
|--------------|-----------|-------------|
| `Returned`   | `VARCHAR` | Indicates whether the order was returned (e.g., 'Yes' or 'No'). |
| `Order ID`   | `VARCHAR` | Unique identifier for each order. |

</details>
    
- 👥 **Table 3: People**. Returned order records, with 1,100 records.
<details>
  <summary>See details </summary>
  
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Person`    | `VARCHAR` | Name of the salesperson. |
| `Region`    | `VARCHAR` | Geographic region where the salesperson operates. |

</details>

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

---

## 🧠 Design Thinking Process

---

## 📊 Key Insights & Visualizations
### I. Dashboard Executive Summary
![Image](https://github.com/user-attachments/assets/d4807d75-1c5a-4130-9c11-21025e704e46)
Based on the Dashboard Overview, Superstore’s business is showing strong and steady growth.

- Financial highlights: Total revenue reached $12.64 million, up 51.5% compared to last year. Profit also increased by 52.3%, reaching $1.5 million.
- Operational efficiency: The total number of orders reached 25,000, a 51.7% increase. The profit margin remained stable at 11.61%.
- Quality management: The return rate slightly decreased from 4.75% to 4.68%, indicating improvements in product quality or delivery service.
- Growth trend: Trend charts show that both revenue and profit have been increasing consistently from 2011 to 2014, with profit margin peaking at 11.95% in 2013 before a slight adjustment in 2014.

### II. Dashboad Market Analysis
![Image](https://github.com/user-attachments/assets/4c4125f4-6d3a-4200-be24-d8d3a688ba5f)
Markets to Prioritize for Expansion

- High-growth potential markets (New expansion):
    - EMEA and Africa: These regions show the highest year-on-year revenue growth, 59.8% and 53.38%, respectively.
    - Canada: Although current revenue is not high, Canada has an exceptionally strong profit margin of 26.62%, the highest across all markets.
- Key markets to maintain (Retention focus):
    - APAC and EU: These are the top contributors to profit, with $436K from APAC and $373K from EU. Within APAC, North Asia contributed the most ($165K), followed by Central Asia ($132K).
    - Key personnel: Anna Andreadi leads EU sales with $2.9 million, showing that the sales model there is very effective and could be replicated elsewhere.

### III. Dashboard Product Analysis 
![Image](https://github.com/user-attachments/assets/603545ec-94de-471f-b091-b9053eec56aa)
![Image](https://github.com/user-attachments/assets/cffe80e8-756e-466d-b8c9-f4f5b2d5a9f2)
Analysis from the Dashboard Product Analysis shows a clear distinction between profit drivers and eroders:

- Profit Drivers:
    - Technology: The leading category in terms of profit margin (13.99%).
    - Office Supplies: Strong profit margin (13.69%) with high order volume.
    - Top-performing sub-categories: According to the Pareto chart, Copiers, Phones, and Bookcases contribute most to profit. For example, Binders alone generated $72,000 profit with a 15.7% margin.
- Profit Eroders:
    - Furniture: Very low profit margin at only 6.94%, despite high revenue.
    - Tables: The main problem area. Although they generate significant revenue ($757,042, 33% of Furniture revenue), they caused a net loss of $64,083.
- Specific SKUs:
    - High-revenue SKU: “Hon Executive Leather Armchair…” generated about $58,190.
    - Loss-making SKU: Some orders, such as the Ibico EPK-21 bookbinding system in Chicago, caused losses of over $2,900 per transaction. Some Sharp copiers also recorded losses in certain markets.

---

## 🔎 Final Conclusion & Recommendations

1️⃣ Overall Business Performance   
Superstore is showing strong and steady growth across all key financial metrics:
- Top-line Growth: Total revenue reached $12.64M, up 51.5% year-over-year (YoY).
- Bottom-line Profitability: Total profit reached $1.5M (+52.3%), with a stable net profit margin of 11.61%.
- Operational Efficiency: Order volume increased by 51.7%, while the return rate improved slightly to 4.68%, reflecting better product quality and delivery service.

2️⃣ Strategic Recommendations by Market 
- Priority 1 – Profit Optimization (High-Efficiency Model - Canada): Canada is not the largest market by revenue but achieves a record profit margin of 26.62%. Best practices in operations and product mix (Technology and Office Supplies) should be studied and applied to other regions [2, Orders.pdf].
- Priority 2 – Scale Growth (High-Growth Market - EMEA & Africa): These are the fastest-growing markets (>50% YoY). Investment in infrastructure and sales teams should be increased to capture market share quickly.
- Priority 3 – Maintain Position (Cash Cow Markets - APAC & EU): These markets contribute over $800K in total profit. Key personnel like Anna Andreadi (responsible for $2.9M revenue in EU) should be retained to maintain performance.

3️⃣ Product & SKU Recommendations
- Boost “Star” Categories: Technology (Margin 13.99%) and Office Supplies (Margin 13.69%) are the main profit pillars. Sub-categories like Copiers and Phones should be prioritized in marketing campaigns.
- Restructure “Margin Eroders”: Tables are causing a net loss of $64,083 globally.
  - Action: Discontinue or significantly increase prices for loss-making SKUs such as Chromcraft Bull-Nose Wood Oval Conference Tables (previous losses >$1,800 per order).
  - Regional Focus: In US Central (Chicago), logistics costs for bulky Furniture and Appliances should be reviewed, as these SKUs often record negative local profitability. 

4️⃣ Operational & Customer Recommendations
- Return Control: Although the return rate has decreased, certain SKUs (e.g., ES-2013-2638509, IN-2014-47848) are frequently returned. Investigate technical or delivery issues to reduce hidden costs.
- High-Value Customer Focus: Develop loyalty programs for top customers with stable, high spending, such as Justin Ritter and Tom Ashbrook.

*To conclude: Superstore should shift from a “growth-at-all-costs” strategy to a performance-driven growth approach. Reducing loss-making SKUs in the Tables category and replicating Canada’s high-margin model can help achieve a net profit margin above 15% next year.* 

---
## 💡 Deep dive into Canada Insights for EMEA Market Expansion 
#### ❔ Why Canada Has the Highest Profit Margin
<details>
  <summary>See details </summary>
Canada has the highest profit margin in the system (26.62%), more than double the company-wide average of 11.61%, thanks to several strategic factors:
1. Optimized Product Mix
Canada focuses revenue on high-margin categories while limiting low-margin items:
  - Technology (39.29% of revenue) and Office Supplies (44.88% of revenue): These two categories have the best margins in the system (13.99% and 13.69%, respectively).
  - Furniture (15.83% of revenue): Canada minimizes low-margin Furniture, which has the lowest margin in the system (6.94%) and often causes large losses in other markets, e.g., Tables causing a $64,083 loss globally.
2. Highly Profitable Transactions
Order-level data shows that Canada executes many transactions with impressive margins:
  - Technology Products: A copier order in Guelph, Ontario generated $2,270.34 revenue with $1,112.40 profit (~49% margin). Other products like Samsung printers or Logitech accessories also consistently deliver strong margins.
  - Selective Furniture: Unlike other markets, Canadian furniture orders remain profitable. For example, a bookcase in North York generated $743.58 revenue with $371.70 profit (50% margin), and an office chair in Kitchener earned $270.72 profit.
  - High-Value Office Supplies: Many small office supply orders deliver excellent margins, e.g., Acme scissors in London, Ontario made $93.36 profit on $198.72 revenue (~47%).
3. Focused and Efficient Customer Base
  - Smaller, high-quality customer pool: Canada has the fewest customers (153) compared to APAC or EU (thousands).
  - High-value orders: The market focuses on high-value transactions with low operational and management costs, maintaining record-high net margins without being eroded by small or loss-making orders.

*Conclusion: Canada achieves the highest profit margin by selling the right, high-margin products (Technology & Office Supplies), avoiding loss-making items (bulky Furniture or deep-discounted products), and executing individual transactions with outstanding profitability.*
<details>

#### 🌍 EMEA Market Expansion Plan & Applying Canada’s Best Practices
<details>
  <summary>See details </summary>
Superstore’s EMEA region (Europe, Middle East & Africa) is growing rapidly (59.80% YoY), but its profit margin is low (5.45%). To turn EMEA into a high-margin market, the expansion plan should focus on selective growth and profitability, using lessons from Canada’s success.
1. Growth Targets & Leadership
- Revenue Growth: Maintain and accelerate high YoY growth (59.80%), the highest among all markets.
- Leadership: Larry Hughes, head of EMEA, will lead the expansion strategy across Middle East and Africa.
2. Product Mix Optimization (Applying Canada’s Best Practice)
Focus on Profit Drivers:
- Technology (margin 13.99%) and Office Supplies (margin 13.69%) should be prioritized.
- Promote high-margin SKUs like Copiers (successful in Riyadh, Baghdad, Budapest) and Phones (Samsung, Cisco in Iran, Israel, Belarus).
Reduce Margin Detractors:
- Limit low-margin Furniture (6.94%) and expensive items like Tables and Bookcases.
- Apply stricter discount policies and review pricing for bulky items to prevent losses.
Canada Example: Canada achieves a 26.62% profit margin by focusing on high-margin Technology and Office Supplies (83% of revenue combined) while keeping Furniture minimal (15.83%).
3. Customer Strategy (Volume → Quality)
- Focus on High-Value Customers: Prioritize corporate and home-office clients requiring high-tech products instead of low-margin furniture buyers.
- Customer Base Optimization: EMEA has 723 returning customers and 403 new customers; channel efforts into segments with high order value and profitability.
- Canada Insight: A small, focused customer base (153 clients) delivers consistently high-margin orders. EMEA should replicate this approach.
4. Cross-Region Collaboration
Facilitate knowledge-sharing between Nicole Hansen (Canada) and Larry Hughes (EMEA) on:
- Product mix strategy
- High-margin SKU selection
- Logistics cost management for bulky items
- Use Canada’s proven model to improve EMEA’s operating efficiency and profit per transaction.

*Conclusion: The EMEA expansion is not just about revenue growth but “selective, profit-focused growth.” By prioritizing high-margin Technology and Office Supplies, minimizing loss-making Furniture, focusing on profitable customer segments, and leveraging Canada’s best practices, EMEA has the potential to become a new high-margin engine for Superstore rather than a low-margin revenue market.*
<details>

#### ⚠️ Strategic Risks
<details>
  <summary>See details </summary>
Applying Canada’s high-margin, selective-order model to EMEA (high growth, low margin) brings opportunities but also strategic risks:
1. Growth vs. Profitability

EMEA is currently the system’s fastest-growing market (YoY Growth 59.8%).
-> Risk: Strictly filtering orders or focusing only on Technology & Office Supplies to boost margin may lose market share and slow revenue growth.
2. Logistics & Geographic Complexity

Canada is a single-country market; EMEA spans Europe, Middle East, Africa with different operating costs.
-> Risk: Ignoring shipping, customs, and cross-border costs (e.g., chairs in Beykoz lost $1,842) could erase margin gains.
3. Local Market Demand Differences

In Canada, Furniture is only 15.83% of revenue.
-> Risk: In regions like Eastern Europe or Middle East, Furniture may drive larger tech sales. Cutting these SKUs could backfire and push corporate clients to competitors who provide full-package solutions.
4. Operational Pressure on Management

EMEA serves ~1,100 customers, far more than Canada (153).
-> Risk: Maintaining Canada-level margin control (SKU-level monitoring, discount policies) at high order volume may overload Larry Hughes’ team without automation.
5. Return Rate Risks
Average system Return Rate: 4.68%.

-> Risk: High-value orders (Copiers, Phones) can result in large negative impact if returned. Focusing on high-margin products without improving quality & delivery may erode profits faster than selling small office supplies.
✅ Recommendation
Apply Canada’s model via localized optimization:
- Start with loss-making SKUs (Margin Detractors) in Turkey & Kazakhstan.
- Gradually tighten product mix across EMEA once logistics, demand, and operations are under control.
<details>

---
## ✨ More information 
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



📌 Final Note
> *“This project is an opportunity to create a professional portfolio dashboard.  
> Always put yourself in the stakeholder’s shoes, and deliver reports that are clear, visually appealing, and rich with insights.
> BELIEVE YOU CAN DO 10X BETTER THAN FIRST VERSION”*  
