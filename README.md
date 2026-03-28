# 🏨 Hotel Reservation Analytics Dashboard

![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoft&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Data Model](https://img.shields.io/badge/Data%20Model-Star%20Schema-green?style=for-the-badge)
![Kaggle](https://img.shields.io/badge/Data-Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)

> A comprehensive **Microsoft Excel** analytics solution for hotel reservation data — built entirely in Excel using **Power Query (M)**, **Data Modeling (Star Schema)**, and **DAX measures**. Covers revenue performance, cancellation behavior, customer insights, channel analysis, and seasonality trends.

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Dashboard Pages](#-dashboard-pages)
- [Data Model (Schema)](#-data-model-schema)
- [Data Cleaning](#-data-cleaning)
- [DAX Measures](#-dax-measures)
- [M Language (Power Query)](#-m-language-power-query)
- [Key Insights](#-key-insights)
- [Data Source](#-data-source)
- [How to Use](#-how-to-use)
- [Author](#-author)

---

## 📊 Project Overview

This project analyzes hotel reservation data sourced from **Kaggle**, fully built inside **Microsoft Excel** — no Power BI, no Python. The entire pipeline from raw data to interactive dashboards lives in a single `.xlsx` file:

| Layer | Tool Used |
|-------|-----------|
| 🔄 Data Ingestion & Cleaning | Power Query (M Language) |
| 🗄️ Data Modeling | Excel Data Model — Star Schema (Power Pivot) |
| 📐 Calculations | DAX Measures |
| 📊 Visualization | Excel Pivot Charts & Slicers |

**Five dashboard pages cover:**

| Page | Focus |
|------|-------|
| 💰 Revenue & Pricing | Actual vs expected revenue, room pricing trends |
| ❌ Cancellation Analysis | Cancellation rates, patterns, and revenue lost |
| 👤 Customer Behavior | Guest loyalty, meal plans, stay patterns |
| 📡 Channel Types | Booking channel performance and profitability |
| 🍃 Seasonality | Monthly and seasonal demand fluctuations |

**Key Numbers at a Glance:**

| Metric | Value |
|--------|-------|
| Raw Records | 36,275 |
| Clean Records (after data cleaning) | 36,238 |
| Total Actual Revenue | $7,042,183 |
| Total Expected Revenue | $11,336,104 |
| Total Lost Revenue | $4,293,921 |
| Cancellation Rate | 32.8% |
| Average Room Price | $104 |
| Total Guests | 70,683 |
| Average Length of Stay | 3 Nights |
| Average Lead Time | 85 Days |

---

## 🖥️ Dashboard Pages

### 1. 💰 Revenue & Pricing Analysis
> Tracks actual vs expected revenue, room type pricing, and channel revenue contributions.

<img width="1697" height="783" alt="Revenue   Pricing" src="https://github.com/user-attachments/assets/913f0705-78ac-4979-96f4-87994e36f921" />


**Highlights:**
- Online channel dominates with **$8.2M** in revenue (64% of total)
- Room Type 6 commands the highest average price at **$182/night**
- Revenue peaks in **October ($1.6M)** and dips in **January ($211K)**
- 38% of expected revenue is lost to cancellations

---

### 2. ❌ Cancellation Analysis
> Deep-dives into cancellation rates by channel, room type, guest type, and lead time.

<img width="1723" height="782" alt="Cancellation" src="https://github.com/user-attachments/assets/32302830-8bb5-4c57-9d6d-89324c014b81" />


**Highlights:**
- Overall cancellation rate: **32.8%** — costing **$4.29M** in lost revenue
- **Online channel** has the highest cancellation rate at **37%**
- **Corporate channel** shows the lowest at just **11%**
- July peaks at **45%** cancellation rate — the worst month
- Longer lead times strongly correlate with higher cancellation rates
- Guests with **0 special requests** cancel at **43.2%** vs **14.6%** for 2 requests

---

### 3. 👤 Customer Behavior
> Explores guest loyalty, stay durations, meal plan choices, and parking needs.

<img width="1722" height="783" alt="Customer Behaiviowr" src="https://github.com/user-attachments/assets/270ad6b6-3b27-491b-99d3-77b63bf3c2a0" />


**Highlights:**
- Only **2.6%** of guests are repeat customers — loyalty is a major opportunity
- **Meal Plan 1** is overwhelmingly popular with **27,802** selections
- Room Type 1 accounts for **28,105 bookings** — by far the most popular
- **Offline channel** guests book furthest in advance (**123 days** average lead time)
- Room Type 7 has the highest repeat guest rate at **13.3%**

---

### 4. 📡 Channel Types Analysis
> Compares booking channels across volume, pricing, lead time, and cancellation behavior.

<img width="1726" height="782" alt="Channels" src="https://github.com/user-attachments/assets/bc102f7a-ccf6-4e84-9142-228b84465871" />


**Highlights:**
- **Online** dominates with **23,194 bookings** (64% of total)
- **Complementary** channel has the highest repeat guest rate at **32.3%**
- **Corporate** guests have the best cancellation behavior (only 11% rate)
- **Online** rooms average **$112/night** — highest among all channels
- Aviation channel books with only **5 days** average lead time

---

### 5. 🍃 Seasonality Analysis
> Reveals booking and revenue patterns across months and seasons.

<img width="1721" height="782" alt="Seasonality" src="https://github.com/user-attachments/assets/99442a68-cfd0-4e70-a388-4cf2b51bd8cf" />


**Highlights:**
- **Autumn** is the busiest season with **12,908 bookings**
- **Winter** is the slowest with only **5,702 bookings**
- **Weekend nights (29,370)** far outnumber weekday bookings
- October has both peak revenue **($1.6M)** and high booking volume **(5,317)**
- Cancellation rate drops sharply in **December (13.3%)** — the lowest month

---

## 🗄️ Data Model (Schema)

> Star schema built natively inside the **Excel Data Model (Power Pivot)** — one Fact table surrounded by five Dimension tables, all connected via surrogate keys.

<img width="987" height="783" alt="Schema" src="https://github.com/user-attachments/assets/812dfdac-7ec8-4055-bca1-54b337964031" />


### Tables

#### 🔵 Fact Table — `Fact_Hotel_Reservations`
| Column | Type | Description |
|--------|------|-------------|
| Booking_ID | Text | Unique booking identifier |
| Adults | Number | Number of adults |
| Children | Number | Number of children |
| Weekend_nights | Number | Weekend nights booked |
| Week_nights | Number | Weekday nights booked |
| Need_parking | Number | Parking required (1/0) |
| Arrival_date | Date | Date of arrival |
| lead_time | Number | Days between booking and arrival |
| Repeated_guest | Number | Repeat visitor flag (1/0) |
| Previous_cancellations | Number | Number of past cancellations |
| Bookings_not_canceled | Number | Count of non-canceled bookings |
| avg_price_per_room | Number | Average room price |
| Special_requests | Number | Number of special requests made |
| Meal_Plan_Key | Number | FK → Dim_Meal_Plan |
| Room_type_Key | Number | FK → Dim_Room_Type |
| Channel_type_Key | Number | FK → Dim_Channel_Type |
| Date_Key | Number | FK → Dim_Date |
| Booking_Status_Key | Number | FK → Dim_Booking_status |

#### 🟢 Dimension Tables

| Table | Columns |
|-------|---------|
| `Dim_Room_Type` | Room_type, Room_type_Key |
| `Dim_Meal_Plan` | Meal_plan, Meal_Plan_Key |
| `Dim_Channel_Type` | Channel_type, Channel_type_Key |
| `Dim_Booking_status` | Booking_Status, Booking_Status_Key |
| `Dim_Date` | DateKey, Date, Year, MonthNumber, MonthName, Quarter, DayNumber, DayName, WeekNumber, IsWeekend, YearMonth |

All relationships are **one-to-many** from each dimension to the fact table, managed in the **Excel Data Model Diagram View**.

---

## 🧹 Data Cleaning

All cleaning was performed in **Power Query** before loading into the data model.

| # | Issue Found | Action Taken | Records Affected |
|---|-------------|--------------|-----------------|
| 1 | **Invalid dates — February 29** in non-leap years | Filtered out rows where Arrival_date = Feb 29 | **37 records removed** |
| 2 | Null values in `Special_requests` | Replaced with `0` | Multiple records |
| 3 | Null values in `Children` | Replaced with `0` | Multiple records |
| 4 | Duplicate `Booking_ID` values | Removed duplicates | Verified clean |

> **Raw dataset:** 36,275 records → **After cleaning:** 36,238 records (**37 rows removed**)

The February 29 removal step in Power Query:
```m
// Remove invalid Feb 29 arrival dates
FilterOutFeb29 = Table.SelectRows(Source,
    each not (Date.Month([Arrival_date]) = 2
              and Date.Day([Arrival_date]) = 29))
```

---

## 📐 DAX Measures

All measures are listed in a fact table inside.

```dax
-- ─────────────────────────────────────────
-- BOOKING METRICS
-- ─────────────────────────────────────────

Total Bookings =
COUNTROWS(Fact_Hotel_Reservations)

Total Guests =
SUM(Fact_Hotel_Reservations[Adults])
    + SUM(Fact_Hotel_Reservations[Children])

Count of Repeated Guest =
CALCULATE(
    COUNTROWS(Fact_Hotel_Reservations),
    Fact_Hotel_Reservations[Repeated_guest] = 1
)

Repeated Guest % =
DIVIDE(
    [Count of Repeated Guest],
    [Total Bookings],
    0
)

-- ─────────────────────────────────────────
-- STAY METRICS
-- ─────────────────────────────────────────

Length of Stay =
SUM(Fact_Hotel_Reservations[Weekend_nights])
    + SUM(Fact_Hotel_Reservations[Week_nights])

Avg Length of Stay =
DIVIDE(
    [Length of Stay],
    [Total Bookings],
    0
)

Avg Week Nights =
AVERAGE(Fact_Hotel_Reservations[Week_nights])

Avg Weekend Nights =
AVERAGE(Fact_Hotel_Reservations[Weekend_nights])

-- ─────────────────────────────────────────
-- CANCELLATION METRICS
-- ─────────────────────────────────────────

Cancellation Rate =
DIVIDE(
    [Number of Bookings Canceled],
    [Total Bookings],
    0
)

-- ─────────────────────────────────────────
-- LEAD TIME
-- ─────────────────────────────────────────

Avg Lead Time =
AVERAGE(Fact_Hotel_Reservations[lead_time])
```

---

## ⚙️ M Language (Power Query)

### Dim_Date — Generated Entirely in Power Query
```m
let
    Source = Fact_Hotel_Reservations,
    MinDate = Date.From(List.Min(Source[Arrival_date])),
    MaxDate = Date.From(List.Max(Source[Arrival_date])),

    DateList = List.Dates(
        MinDate,
        Duration.Days(MaxDate - MinDate) + 1,
        #duration(1,0,0,0)
    ),

    ConvertToTable = Table.FromList(DateList, Splitter.SplitByNothing(), {"Date"}),

    AddDateKey = Table.AddColumn(ConvertToTable, "DateKey",
        each Date.Year([Date]) * 10000 +
             Date.Month([Date]) * 100 +
             Date.Day([Date]),
        Int64.Type
    ),

    AddYear = Table.AddColumn(AddDateKey, "Year", each Date.Year([Date]), Int64.Type),

    AddMonthNumber = Table.AddColumn(AddYear, "MonthNumber", each Date.Month([Date]), Int64.Type),

    AddMonthName = Table.AddColumn(AddMonthNumber, "MonthName", each Date.MonthName([Date])),

    AddQuarter = Table.AddColumn(AddMonthName, "Quarter", each "Q" & Number.ToText(Date.QuarterOfYear([Date]))),

    AddDayMonth = Table.AddColumn(AddQuarter, "DayOfMonth", each Date.Day([Date]), Int64.Type),

    AddDayNumber = Table.AddColumn(AddDayMonth, "DayNumber", each Date.DayOfWeek([Date],Day.Saturday), Int64.Type),

    AddDayName = Table.AddColumn(AddDayNumber, "DayName", each Date.DayOfWeekName([Date])),

    AddWeekNumber = Table.AddColumn(AddDayName, "WeekNumber", each Date.WeekOfYear([Date]), Int64.Type),

    AddIsWeekend = Table.AddColumn(AddWeekNumber, "IsWeekend", each Date.DayOfWeek([Date], Day.Monday) >= 5),

    AddYearMonth = Table.AddColumn(AddIsWeekend, "YearMonth", each Date.ToText([Date], "yyyy-MM")),
    #"Changed Type" = Table.TransformColumnTypes(AddYearMonth,{{"Date", type date}})

in
    #"Changed Type"
```

---

## 💡 Key Insights

### 🔴 Problems Identified
1. **High cancellation rate (32.8%)** — wiping out **$4.29M** in potential revenue
2. **Very low repeat guest rate (2.6%)** — almost no loyalty program impact
3. **Online channel cancellations (37%)** — highest volume + highest churn = biggest risk
4. **Long lead times drive cancellations** — strong positive correlation observed

### 🟢 Opportunities
1. **Corporate channel** books low volume (2,011) but cancels only **11%** — worth growing
2. **Guests with 2+ special requests** cancel at only **14.6%** — engage guests early
3. **Autumn season** is peak demand — optimize pricing dynamically
4. **Room Type 7** has the highest repeat guest rate **(13.3%)** — replicate what works

### 📋 Recommendations
- Implement a **loyalty program** targeting Room Type 7 guests and Corporate channel visitors
- Introduce **non-refundable rate tiers** for Online bookings with long lead times
- Apply **dynamic pricing** during Oct–Nov (peak revenue window)
- Proactively collect special requests at booking — proven to lower cancellation risk significantly

---

## 📁 Repository Structure

```
Hotel-Reservation-Analytics-Dashboard/
│
├── 📊 Hotel_Reservation_Dashboard.xlsx     ← Main Excel file (Data Model + Dashboards)
├── 📋 Hotel_Reservations_Raw.xlsx          ← Source data from Kaggle (36,275 records)
│
├── screenshots/
│   ├── Revenue_&_Pricing.png
│   ├── Cancellation.png
│   ├── Customer_Behaiviowr.png
│   ├── Channels.png
│   ├── Seasonality.png
│   └── Schema.png
│
├── DAX_Measures.dax                        ← All DAX measure code
├── PowerQuery_M_Transformations.m          ← All Power Query M code
├── Repository_Structure
└── README.md
```

---

## 📦 Data Source

- **Platform:** [Kaggle](https://www.kaggle.com/)
- **File Format:** Excel (.xlsx)
- **Raw Records:** 36,275 | **After Cleaning:** 36,238
- **Period Covered:** 2017 – 2018
- **Notable Cleaning:** 37 records removed due to invalid **February 29** arrival dates

---

## 🚀 How to Use

1. **Download** `Hotel_Reservation_Dashboard.xlsx` from this repository
2. **Open in Microsoft Excel** (Excel 2016 or later — requires Power Pivot)
3. **Enable Power Pivot** if prompted:
   `File → Options → Add-ins → COM Add-ins → ✅ Microsoft Power Pivot for Excel`
4. Navigate between the **5 dashboard tabs** at the bottom of the workbook
5. Use the **Year / Quarter slicers** on the left panel to filter

> ⚠️ Requires **Power Pivot** — available in Excel 2016+, Microsoft 365 (Windows). Some features may not work on Excel for Mac.

---

## 👤 Author

**Mohamed Sayed Taha**  
Data Analyst | Excel | Power BI |  SQL | Python | Power Query | DAX |

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/YOUR_LINKEDIN_USERNAME)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:YOUR_EMAIL@gmail.com)

---

> ⭐ If you found this project useful, please consider giving it a star!
