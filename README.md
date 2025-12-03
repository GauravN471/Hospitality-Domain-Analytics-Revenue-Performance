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


