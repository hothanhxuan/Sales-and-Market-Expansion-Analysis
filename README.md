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

### 🏢 Business Context and Question 
Superstore is a global retail company operating across multiple markets worldwide. 
As the company experiences rapid growth, senior management requires consolidated insights to answer three critical business questions: 
  1. What is the current overall business performance? 
  2. Which markets should be prioritized for expansion? 
  3. Which product categories and SKUs drive profit — and which erode it? 
This project transforms raw transactional data into a decision-support Power BI dashboard, enabling leadership to shift from high-level reporting to actionable, strategy-focused insights. 

### 🎯Project Outcome:
---

## 📂 Dataset Description & Data Structure
### 🔍 Data source Overview
- **Source**: Kaggle
- **Size**: The Orders table contains 51,290 records.
- **Format**: CSV 
The analysis is based on three datasets: 
| Dataset | Description                                                  | Records  |
|--------|---------------------------------------------------------------|----------|
| Orders | Contains detailed transaction and customer information        | ~51,290  |
| People | Sales representatives by region                               | 13       |
| Returns| Returned order records                                        | ~1,100   |
Together, these datasets provide visibility into sales performance, people contribution, and operational risk through returns.

### 📊 Data structure 
- 🛒 **Orders**
<details>
<summary> <strong>Table 1: Orders</strong></summary>

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

- 🔄 **Returns** 
<details>
<summary> <strong>Table 2: Returns</strong></summary>

| Column Name  | Data Type | Description |
|--------------|-----------|-------------|
| `Returned`   | `VARCHAR` | Indicates whether the order was returned (e.g., 'Yes' or 'No'). |
| `Order ID`   | `VARCHAR` | Unique identifier for each order. |

</details>
  
- 👥 **People** 
<details>
<summary> <strong>Table 3: People</strong></summary>

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

#### ✅ Analytical Capabilities
This data model enables flexible slicing and filtering across:
- Time
- Market
- Region
- Category
- Product
- Salesperson






---

## 🛠️ Workflow
1. Review the project brief and dataset.  
2. Complete the **Empathy** section in the Design Thinking file.  
3. Explore reference dashboards (Power BI, Tableau, Maven).  
4. Work on **Point of View** and **Ideate**.  
5. Learn about color theory and select a theme.  
6. Build **Version 1** dashboard.  
7. Continuously refine by **switching perspective as a stakeholder**.  
8. Build **Version 2** and validate against Design Thinking iterations.  
9. Finalize **Version 3**.  

⚠️ **Note**: A professional dashboard must combine **layout, colors, and meaningful insights**. Since this project can be part of your **portfolio for job applications**, ensure high-quality output.  

---

## 🎨 Resources
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

## 📌 Final Note
> *“This project is an opportunity to create a professional portfolio dashboard.  
> Always put yourself in the stakeholder’s shoes, and deliver reports that are clear, visually appealing, and rich with insights.”*  
