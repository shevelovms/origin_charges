# 🧩 Origin Fees Analysis — Excel (Power Query + Cost Optimization)

> **Disclaimer:**  
> This project was originally conducted for one of **Canada’s largest retail companies**.  
> Due to the confidentiality and sensitivity of the original data, all values, entity names, and identifiers have been **replaced with synthetic placeholders**.  
> Numerical figures have been **modified for demonstration purposes**, while maintaining the original **structure, logic, and proportional relationships** of the analysis.  
> No real company, carrier, or client data is included in this repository.


---

## 📘 Overview
This project analyzes **origin fees** — including *Terminal Handling Charges (THC)*, *Booking Fees*, and *Documentation Handling Fees* — across multiple carriers and company divisions to uncover potential **cost optimization opportunities** in international logistics.

Originally developed during my time at **Company X**, this anonymized version focuses on methodology, structure, and analytical reasoning — all derived from **synthetic and non-confidential examples**.

---

## 🎯 Stakeholder Questions
The analysis was guided by the following business questions:  

1. **Carrier Spend Overview:**  
   Which carriers represent the highest total spend across the top three origin fee types — *Terminal Handling (THC)*, *Booking*, and *Documentation Handling*?  

2. **Port Spend Distribution by Carrier:**  
   For each top carrier, which origin ports drive the highest total spend across these fee categories?  

3. **Negotiation Focus:**  
   Where do high per-container pricing and elevated THC costs overlap, indicating priority lanes and carriers for upcoming RFQ negotiations?  

---

## 🧰 Tools & Techniques
- **Microsoft Excel / Power Query** — data cleaning, transformation, and consolidation  
- **PivotTables & Charts** — aggregation, visualization, and cost benchmarking  
- **Formulas & Functions:** `XLOOKUP`, `FILTER`, `IF`, `INDEX/MATCH`, `TEXTSPLIT`, `UNIQUE`, `CONCATENATE`, `SUBSTITUTE`, and dynamic arrays  
- **Currency Conversion:** Excel Currency Data Type module + lookup table for USD normalization  
- **Presentation:** PowerPoint summarizing findings and negotiation priorities  

---

## 🗂️ Repository Structure
origin-fees-analysis/
│
├── presentation/
│ └── Origin_Fees_Analysis_Presentation.pdf
│
└── README.md

---

## ⚙️ Technical Process

### 1. **Data Sources**
Four primary raw datasets were used:  

1. **Historical Container Movement Data** —  
   Three workbooks (one per subsidiary), each containing 15–20 columns and 20–35K rows of YTD 2025 container movement records.  

2. **Carrier KPI Data** —  
   Three workbooks (one per subsidiary) with 15–20 columns and 10–25K rows of operational KPIs, port data, and carrier metrics.  

3. **FOB Mapping File** —  
   A workbook mapping port names to 5–8-digit codes for name standardization.  

4. **Origin Fee Rates** —  
   A workbook containing ~2–3K rows of fee data (port, container type, fee type, value in local currency).

---

### 2. **Data Cleaning & Standardization**
Performed primarily in **Power Query**, supported by Excel formulas:

- Appended subsidiary files and standardized headers.  
- Removed blanks, normalized field names, and fixed inconsistent casing.  
- Unpivoted wide fee tables into long format for analysis.  
- Replaced blanks with “NaN” for visibility, later filtered out.  
- Unified country and port names (e.g., *Great Britain → UK; Burma → Myanmar*).  
- Built helper columns for consistent `"FOB [PORT]"` formatting.  
- Converted all currency values to USD using Excel’s currency data type and custom lookups.

---

### 3. **Data Integration**
- Connected all four datasets via Power Query in a master analysis workbook.  
- Created unique lookup keys (e.g., *Container + Voyage Number*) to ensure accurate aggregation.  
- Normalized port names and codes using nested `IF` + `ISNUMBER` + `XLOOKUP` logic.  
- Achieved >95 % mapping accuracy across port identifiers.  

---

### 4. **Handling Missing Fee Data**
- Identified missing rates through lookup-key matching (`Carrier + Port + Container Size + Fee Type`).  
- Auto-generated rate-request templates using `UNIQUE`, `CONCATENATE`, and `TEXTSPLIT`.  
- Integrated returned rates, re-unpivoted data, and refreshed Power Query connections.  
- Dropped remaining nulls prior to final analysis.

---

### 5. **Analysis & Calculation**
- Pulled fee values in USD via `XLOOKUP` for each fee category (THC, Booking, Documentation).  
- Calculated **total spend** per carrier, port, and container type using conditional logic.  
- Built **PivotTables** for cost benchmarking and variance detection.

---

### 6. **Visualization & Reporting**
Key deliverables included:

- **Top Carriers by Total Spend** (THC / Booking / Documentation)  
- **Top 5 Ports per Top 5 Carriers — Total Origin Spend (2025 YTD)**  
- **High Unit Cost × High THC Overlap — Negotiation Targets**  

All visuals and key takeaways were presented in the accompanying anonymized presentation.

---

## 💡 Key Insights (Anonymized)
- **Carrier Concentration:** Carrier A + Carrier B together account for **~41 %** of total origin spend.  
  In contrast, **Carrier J** accounts for only **~1.4 %**.  

- **Spend Distribution:** Carrier B ranks lower overall but emerges as a **top spender within its top 5 ports**,  
  whereas **Carrier A drops from rank 1 to 3**, showing its volume is **more evenly distributed** across ports.  

- **High-Cost Lane:** The **Port of Busan with Carrier A** is the **most overpriced THC FOB overall** —  
  total THC spend ≈ **$123 807**, avg THC ≈ **$236 / TEU** (~55 % above the port median).  

---

## 📈 Outcome / Recommendations
❗ **Negotiation Priorities:**  
Focus upcoming RFQ negotiations on:  
- **Carrier A / FOB Busan**  
- **Carrier D / FOB Yantian**  
- **Carrier C / FOB Yantian**

**Additional Recommendations:**  
- Target THC variance thresholds within ±15 % of port medians.  
- De-prioritize low-volume FOBs (< $50 K YTD).  
- Implement standardized origin-fee templates and quarterly cost-tracking dashboards.

---

## 🔐 Data Privacy & Ethics
All underlying data used in the original project was **confidential and proprietary** to Company X and its partners.  
No real data, PII, or corporate identifiers appear here.  
All names (carriers, ports, subsidiaries, etc.) are **synthetic placeholders**.  
This anonymized version is released solely for educational and portfolio demonstration purposes.

---

## 🧭 Lessons Learned
- Data normalization is essential when consolidating decentralized cost data.  
- Power Query ensures transparency and reproducibility in Excel analytics.  
- Modular file design improves performance and auditability.  
- Upholding confidentiality and ethics enhances professional credibility.

---

## 🪄 About Me
Logistics specialist turned data analyst — building projects in **Excel, Python, and SQL** to uncover insights and drive operational improvement.  