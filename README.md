# 🏨 Hospitality Analytics Dashboard – Power BI Project

This repository contains my complete end-to-end **Hospitality Domain Analytics Dashboard** built in **Power BI**, inspired by the AtliQ Grands revenue management case study from the **Codebasics Power BI Course**.

The goal of this project was to analyze revenue decline, understand operational KPIs, and deliver actionable insights for strategic decision-making in the hospitality business.

🔗 **Live Dashboard:**  
[Click to View](https://app.powerbi.com/view?r=eyJrIjoiMTViZjdlNDAtM2M3NS00NmZhLTg0MTctYzBlYjliOWI0M2E2IiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)

---

## 📘 Project Overview

AtliQ Grands, a chain of luxury hotels across India, was losing market share due to competitive pressure and poor decision-making.  
This dashboard provides:

- Hotel performance visibility  
- Trend analysis  
- KPI monitoring  
- Property-level benchmarking  
- Actionable insights for revenue recovery  

---

## 🛠 Tech Stack

- **Power BI Desktop**
- **Power Query**
- **DAX (Data Analysis Expressions)**
- **Star Schema Data Modeling**

---

## 🧱 Data Model (Star Schema)

**Tables Used:**
- `dim_date`
- `dim_hotels`
- `dim_rooms`
- `fact_bookings`
- `fact_aggregated_bookings`

> The model follows a **clean star-schema**, ensuring optimized performance and easy DAX calculations.

---

## 📊 Key KPIs Implemented

- **Revenue**
- **RevPAR** (Revenue per available room)
- **ADR** (Average daily rate)
- **Occupancy %**
- **Realisation %**
- **DSRN / DBRN / DURN**
- **Cancellation %**
- **No-show %**
- **Booking % by Platform**
- **Booking % by Room Class**
- **WoW Change % for all major KPIs**

---

## 📐 Important DAX Measures

Some highlighted DAX measures:

```DAX
Revenue WoW change % =
VAR WeekNo = SELECTEDVALUE(dim_date[week no])
VAR Curr = CALCULATE([Revenue], FILTER(ALL(dim_date), dim_date[week no] = WeekNo))
VAR Prev = CALCULATE([Revenue], FILTER(ALL(dim_date), dim_date[week no] = WeekNo - 1))
RETURN DIVIDE(Curr - Prev, Prev)
RevPAR = DIVIDE([Revenue], [Total Capacity])
Occupancy % = DIVIDE([DBRN], [DSRN])
Realisation % = DIVIDE([DURN], [DBRN])
```

## 📘 What I Learned — Skills & Outcomes

### 🔹 1. End-to-End Power BI Development
- Imported, cleaned, and transformed data using Power Query  
- Built a clean star-schema data model  
- Developed DAX measures for operational and financial KPIs  
- Designed an interactive, user-friendly dashboard  

### 🔹 2. Hospitality Domain Understanding
- Learned industry KPIs such as RevPAR, ADR, DSRN, DBRN, DURN  
- Understood occupancy trends, realisation %, and cancellation patterns  
- Analyzed booking behavior across platforms and room categories  

### 🔹 3. Advanced DAX Skills
- WoW% change calculations  
- KPI ratio measures  
- Time intelligence functions  
- Context transition and filter manipulation  
- Dynamic and reusable DAX patterns  

### 🔹 4. Data Storytelling & Insights
- Identified trends across weeks, cities, properties, and platforms  
- Converted raw data into actionable insights  
- Presented clear business recommendations supported by metrics  

### 🔹 5. Dashboard UI/UX Design
- Built a premium gold–black luxury theme using JSON  
- Created modern KPI cards with Card (New) visuals  
- Designed clean layouts, consistent spacing, and readable visuals  
- Added tooltip pages for deeper exploration  
- Used conditional formatting for better interpretation  

### 🔹 6. Analytical Thinking
- Improved problem-solving skills by connecting data to business outcomes  
- Understood the business impact of cancellations, occupancy, and ADR  
- Learned how to evaluate property-level performance  



---

These learnings strengthened my skills as a **Data Analyst**, especially in DAX, data modeling, and business domain understanding.

