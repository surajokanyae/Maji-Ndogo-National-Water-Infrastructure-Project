# 🌊 Maji Ndogo Water Infrastructure Project: End-to-End Analysis & Strategy

## 📌 Project Overview
Maji Ndogo is a nation of 27 million people facing a critical water crisis. This project represents a comprehensive, two-phase data solution:
1.  **Phase 1 (Analysis):** Identifying the root causes of water scarcity, gender-based queue inequality, and contamination patterns.
2.  **Phase 2 (Implementation):** Designing a $147M national budget, prioritizing high-risk provinces, and tracking a 4-year infrastructure rollout (2023–2027).

---

## 🛠️ Technical Stack
* **Tool:** Power BI Desktop
* **Data Modeling:** Star Schema (Fact and Dimension tables)
* **DAX (Data Analysis Expressions):**
    * Dynamic Budgeting Logic (Applying 30% rural premiums)
    * Population Impact Metrics (Access to basic water services)
    * Time-Intelligence (Tracking progress across a 4-year timeline)
* **Visual Communication:** Drill-through actions, Conditional Formatting, and Visual Hierarchy.

---

## 📂 Project Structure
* `Maji_Ndogo_1.pbix`: Exploratory Data Analysis (EDA) focusing on demographics, source types, and social impacts.
* `Maji_Ndogo_2.pbix`: Strategic Planning focusing on budgeting, vendor performance, and project completion tracking.

---

## 📊 Key Findings & Strategic Actions

### 1. The Demographic Challenge
* **Finding:** 69% of the population resides in rural areas, yet they have the least access to infrastructure.
* **Action:** Prioritized rural well-drilling in the budget to reach the most vulnerable citizens.



### 2. Contamination & Filtration
* **Finding:** **Akatsi** has the highest chemical contamination, while **Sokoto** suffers from biological river contamination.
* **Action:** Allocated specialized funding for RO (Reverse Osmosis) filters in Akatsi and new wells in Sokoto.

### 3. Financial Strategy & Budgeting
* **Calculated Budget:** $110.7M specifically for the high-priority provinces of **Sokoto** and **Kilimani**.
* **Cost Management:** Identified **TUS835** as the most cost-efficient team for urban filter installations, recommending them for future scaling.



## 🚀 Impact & Outcomes
* **Project Completion:** Successfully tracked the upgrade of **23,689 water sources** by the end of 2027.
* **Population Impact:** Facilitated access to new wells for **735,000 citizens** in Sokoto alone during the 2025 peak phase.
* **Efficiency:** Used **Drill-Through** functionality to allow stakeholders to move from National KPIs to specific Town-level audit details in a single click.



---

## 🧠 DAX Showcase: The Rural Budget Adjustment
To account for the logistical difficulty of rural upgrades in Sokoto, I implemented a 30% cost adjustment using the following logic:

```dax
Sokoto_Adjusted_Budget = 
CALCULATE(
    SUM(infrastructure_cost[Unit_Cost]) * 1.3,
    'Location'[Province] = "Sokoto",
    'Location'[Type] = "Rural"
)
