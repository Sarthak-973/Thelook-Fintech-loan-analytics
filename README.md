# 📊 TheLook Fintech Loan Analytics
> End-to-end cloud data analytics project to analyze loan data and build an interactive dashboard for better decision-making.

---

## ⚙️ Project Type

- [x] SQL Analysis / Querying
- [x] Dashboard / Data Visualization
- [x] Data Cleaning / Wrangling
- [x] End-to-End (multiple of the above)

---

## Table of Contents
1. [Project Overview](#1-project-overview)
2. [Objectives](#2-objectives)
3. [Project Scope & Tools](#3-project-scope--tools)
4. [Repository Structure](#4-repository-structure)
5. [Data Workflow](#5-data-workflow)
6. [Analysis & Metrics](#8-analysis--metrics)
7. [Key Insights](#9-key-insights)
8. [Recommendations](#10-recommendations)
9. [Assumptions & Limitations](#11-assumptions--limitations)
10. [Future Enhancements](#12-future-enhancements)
11. [Deliverables](#13-deliverables)
12. [Author](#14-author)
 

---

## 1. Project Overview

**Context:**  
This project was completed as part of the Google Cloud Data Analytics Capstone, simulating a real-world business scenario at TheLook Fintech.

**Problem Statement:**  
The Treasury team needed a way to track loan performance, understand borrower behavior, and monitor key metrics like loan distribution and outstanding amounts.

**Approach:**  
Used BigQuery for data exploration and transformation, and Looker to build an interactive dashboard for visualization.

**Outcome:**  
Developed SQL-based datasets and a dashboard that provides insights into loan trends, borrower distribution, and loan health.

---

## 2. Objectives

- **Primary Objective:**  
  Analyze loan data to track trends and key metrics such as loan count and outstanding amounts.

- **Secondary Objective 1:**  
  Extract and clean loan purpose data from nested fields.

- **Secondary Objective 2:**  
  Join external region data to understand geographic distribution.

- **Secondary Objective 3:**  
  Build an interactive dashboard for business insights.

---

## 3. Project Scope & Tools

### Scope

| Dimension | Details |
|-----------|--------|
| **In Scope** | Loan dataset analysis, SQL transformations, dashboard creation |
| **Time Period** | 2012 – 2019 |
| **Granularity** | Loan-level data |

---

### Tools & Technologies

| Category | Tool(s) Used |
|----------|-------------|
| Data Storage | Google BigQuery |
| Data Processing | SQL |
| Analysis | BigQuery SQL |
| Visualization | Looker |
| Version Control | GitHub |
| Documentation | Markdown |

---

## 4. Repository Structure
```
├── data/
│ ├── raw/
│ └── processed/
│
├── queries/
│ ├── exploratory/
│ ├── transformations/
│ └── final/
│
├── reports/
│ ├── final_report.md
│ └── final_report.pdf
│
├── visuals/
│ ├── dashboard_walkthrough.md
│ └── images/
│
├── docs/
├── README.md
```

---

## 5. Data Workflow
```
BigQuery Dataset
↓
SQL Exploration
↓
Data Cleaning & Transformation
↓
Analysis Queries
↓
Looker Dashboard
```

1. **Source:** Loan dataset in BigQuery  
2. **Ingestion:** Direct query access via BigQuery  
3. **Cleaning:** Removed duplicates, handled nested fields  
4. **Transformation:** Created tables using JOIN and CTAS  
5. **Analysis:** Aggregations (COUNT, GROUP BY)  
6. **Output:** Dashboard + report  

---

## 6. Analysis & Metrics

### Key Metrics

| Metric | Definition | Purpose |
|--------|-----------|--------|
| Loan Count | Total number of loans | Track growth |
| Outstanding Loan Amount | Total unpaid loan value | Measure exposure |
| Loan Purpose | Reason for loan | Understand behavior |
| Loan Distribution by State | Loans grouped by state | Geographic insights |

---

## 7. Key Insights

**Insight 1: Loan Growth Over Time**  
Loan counts increased across years, indicating business expansion.

**Insight 2: Geographic Concentration**  
Certain states contribute more loans, showing regional demand differences.

**Insight 3: Loan Purpose Patterns**  
Some loan purposes appear more frequently, indicating common borrower needs.

**Insight 4: Loan Status Distribution**  
Most loans are active/current, reflecting ongoing financial activity.

---

## 8. Recommendations

| Priority | Recommendation | Based On | Owner |
|----------|--------------|---------|------|
| High | Monitor high loan exposure regularly | Loan amount KPI | Treasury |
| Medium | Focus on high-loan states for growth | Regional analysis | Business team |
| Low | Analyze borrower segments further | Loan purpose patterns | Analytics |

---

## 9. Assumptions & Limitations

### Assumptions
- Dataset is complete and accurate  
- Loan status values are consistent  

### Limitations
- No customer demographic data  
- No predictive modeling  
- Limited to available dataset  

---

## 10. Future Enhancements

- [ ] Add borrower segmentation  
- [ ] Improve dashboard interactivity  
- [ ] Automate data updates  
- [ ] Expand dataset  

---

## 11. Deliverables

| Deliverable | Description | Location |
|-------------|------------|----------|
| SQL Queries | Exploration, transformation, final queries | `/queries/` |
| Dashboard | Loan insights dashboard | `/visuals/` |
| Report | Final analysis report | `/reports/` |

---

## 12. Author

**Sarthak D**  
Aspiring Data Analyst  

- 🔗 LinkedIn: https://www.linkedin.com/in/sarthak-deshmukh-066559356/
- 💼 GitHub: https://github.com/Sarthak-973  

---

*Last updated: 2026*
