# 📊 HR Analytics: Employee Presence Insights Dashboard

## 🎯 Project Overview

This project focuses on building a robust **HR Analytics Dashboard** in **Power BI** to analyze employee presence data, work-from-home (WFH) preferences, and sick leave (SL) patterns across the organization.

The goal was to transform raw, multi-sheet attendance data into actionable **Presence Insights** for strategic decision-making related to capacity planning, team activities, and employee well-being, as requested by the HR manager, Pinali, and company stakeholders.

---

## 💾 Data Source and Files

The analysis uses real-life, but anonymized, employee attendance data.

| File Name | Description | Role in Project |
| :--- | :--- | :--- |
| **`Attendance-Sheet-2022-2023.xlsx`** | Raw attendance data spread across multiple sheets (April, May, June), with dates stored as column headers. | Source of all presence data. |
| **`HR Analytics.pbix`** | The final **Power BI** desktop file containing the data model, Power Query transformations, and the visualization dashboard. | Final deliverable. |

---

## 💡 Key Business Requirements (Client Queries)

The dashboard was specifically designed to address the following strategic questions:

1.  **Work Preference Analysis:** Understand WFH patterns, especially identifying any preference for Mondays or Fridays.
2.  **Daily Presence Monitoring:** Track the percentage of employee presence on a given week or month (Attendance Rate).
3.  **Sick Leave (SL) Pattern Detection:** Identify spikes or clustering of sick leave on specific days, which could indicate seasonal health issues (e.g., flu, Dengue) or other underlying causes.
4.  **Capacity Planning:** Provide insights to optimize office capacity and schedule team events during periods of high employee presence.

---

## ⚙️ Data Transformation Challenge (Power Query)

The primary technical challenge was converting the Excel file's non-standard structure (dates as column headers across multiple sheets) into a usable relational format.

### Solution Steps (Implemented in Power Query):
1.  **Consolidated Sheets:** The individual monthly sheets were aggregated.
2.  **Dynamic Unpivot:** A crucial step involving creating a **reusable Power Query function** and a **parameter** to dynamically apply transformations to every sheet. This involved:
    * **Unpivoting** the date columns to create a single `Date` column and a single `Value` (Attendance Status) column.
    * Implementing a robust method to **clean future data** by converting the `Date` column and dynamically removing text errors (like 'Holiday', 'Off') to ensure the solution scales automatically.
3.  **Data Cleaning:** Renaming columns and ensuring proper data types were set.

---

## 📈 Dashboard Insights & Visualizations

The **Presence Insights** dashboard provides dynamic filtering by Month and Day of the Week, featuring the following key components:

### 1. High-Level KPIs
* **Present %** (e.g., 167.45%)
* **WFH %** (e.g., 9.08%)
* **SL %** (e.g., 0.88%)

### 2. Time-Series Analysis
* Line graphs tracking **Present % by Date**, **WFH % by Date**, and **SL % by Date** to visualize trends and anomalies over the three-month period (April, May, June).

### 3. Weekly Preference Analysis
* Tables showing **Present %**, **WFH %**, and **SL %** broken down by the **Day of the Week** (Mon-Fri) to confirm preferences (e.g., identifying if WFH is highest on Mondays or Fridays).

### 4. Employee Detail
* A table summarizing individual employee presence rates, WFH usage, and sick leave usage for detailed HR review.
