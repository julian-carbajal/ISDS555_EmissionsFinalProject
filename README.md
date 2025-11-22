# ISDS 555 – World Development Indicators Project  
### Team 4 – Environmental & Economic Dynamics Across Countries

---

## 📌 Project Overview

This repository contains the complete workflow, SQL scripts, Quarto report, and supporting assets for **Team 4’s ISDS 555 World Development Indicators Project**.  
Our research examines **how economic development, technological adoption, and energy usage interact with environmental impact and price stability across countries** using World Bank WDI data.

The project follows all ISDS 555 rules and constraints:

- All **data transformations, joins, cleaning, and analyses** are performed *exclusively in PostgreSQL*.
- **No Python, Excel, R, or external tools** were used for transformation or analysis.
- Helper **views** are used (allowed).  
- **No helper tables** beyond temporary import staging tables.
- Final output tables match the SQL view results exactly (per project requirements).

---

## 📁 Repository Structure

```

isds555-team4/
│
├── report/
│   ├── final_report.qmd
│   ├── final_report.pdf
│   ├── images/
│   │   ├── erd.png
│   │   ├── m_results/
│   │   ├── a_results/
│   │   └── charts/ (optional)
│
├── sql/
│   ├── 01_schema_and_reference_tables.sql
│   ├── 02_indicator_definitions.sql
│   ├── 03_data_import_and_cleaning.sql
│   ├── 04_views_M1_M9.sql
│   ├── 05_views_A1_A5.sql
│   └── 06_final_validation.sql
│
├── data/
│   ├── raw/ (CSV files downloaded from WDI)
│   └── processed/ (if needed)
│
├── README.md
└── .gitignore

````

---

## 📊 Project Objectives

1. Build a **complete PostgreSQL database** including:
   - Countries, Continents, Indicators, and WDI data.
2. Execute **Mandatory Analyses (M1–M9)** as SQL views.
3. Produce **Additional Analyses (A1–A5)** that tell a coherent story:
   - Economic growth  
   - Technology adoption  
   - Energy consumption  
   - Environmental impact  
   - Price stability
4. Deliver a **professional Quarto Report (PDF)** containing:
   - Executive summary  
   - Physical ERD  
   - All mandatory and additional analyses  
   - Interpretations and conclusions  
   - Appendix with full SQL code  

---

## 🗄️ Database Architecture

The database schema consists of:

- **continent**
- **country**
- **continent_country** (mapping table)
- **indicator**
- **data**
- **temp_import** (used only during CSV loading)

A complete **Physical ERD** is included inside `/report/images/erd.png`.

---

## 🧩 Data Source

Data originates from the **World Bank World Development Indicators (WDI)** dataset.  
This project uses **8 selected indicators**:

| Code               | Description                                      |
|-------------------|--------------------------------------------------|
| EN_ATM_CO2E_GF_KT | CO₂ from gaseous fuel (kt)                       |
| EN_ATM_CO2E_KT    | Total CO₂ emissions (kt)                         |
| EN_ATM_CO2E_LF_KT | CO₂ from liquid fuel (kt)                        |
| EN_ATM_CO2E_PC    | CO₂ emissions per capita                         |
| EN_ATM_CO2E_SF_KT | CO₂ from solid fuel (kt)                         |
| FP_CPI_TOTL_ZG    | Inflation (CPI annual %)                         |
| IT_NET_USER_P2    | Internet users (per 100 people)                  |
| NY_GDP_PCAP_CD    | GDP per capita (current US$)                     |

Only these indicators were used, in accordance with assignment requirements.

---

## 🧪 Analyses Included

### ✔ Mandatory Analyses (M1–M9)

- M1 – Countries missing indicator coverage  
- M2 – Countries with all indicators  
- M3 – Indicators ranked by country availability  
- M4 – Top 10 countries by most recent GDP per capita  
- M5 – Continent-level CO₂ per capita comparison  
- M6 – USA indicator table (wide format)  
- M7 – Average GDP per capita growth since 2010  
- M8 – Countries with any 2011 data  
- M9 – Countries with all 2011 data  

### ✔ Additional Analyses (A1–A5)

Designed to tell a cohesive story:

- A1 – Development vs Technology Adoption  
- A2 – Technology Adoption vs CO₂ Emissions  
- A3 – Economic Growth vs CO₂ Growth (post-2010)  
- A4 – Inflation vs Economic Level  
- A5 – Energy Mix vs GDP Levels  

All views are defined using SQL and stored in `/sql/`.

---

## 🚀 How to Run This Project

### 1️⃣ Create Database
```sql
CREATE DATABASE world_indicators;
````

### 2️⃣ Run Schema + Reference Data

Execute:

```
sql/01_schema_and_reference_tables.sql
```

### 3️⃣ Import CSVs into `temp_import`

Use pgAdmin → Import Tool
Repeat for all CSVs.

### 4️⃣ Run Transformation Script

```
sql/03_data_import_and_cleaning.sql
```

This populates the master `data` table.

### 5️⃣ Create All Views

Run:

* `04_views_M1_M9.sql`
* `05_views_A1_A5.sql`

### 6️⃣ Render Final Report

```
quarto render final_report.qmd --to pdf
```

---

## 📘 Final Deliverables

Included in `/report/`:

* **final_report.qmd** – full Quarto source
* **final_report.pdf** – polished professional report
* **erd.png** – physical database ERD
* Screenshots and tables for all analyses

---

## 👥 Team 4 Members



---

## 📄 License (optional)



---

## ⭐ Acknowledgements

Special thanks to:

* The World Bank Open Data Initiative
* ISDS faculty for guidance
* Team 4 collaboration and peer review efforts



