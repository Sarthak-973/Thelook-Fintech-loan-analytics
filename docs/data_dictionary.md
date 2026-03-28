# 📊 Data Dictionary

This document describes the datasets and schemas used in this project.  
All tables are created and analyzed using Google BigQuery.

---

## 🔹 Table: `fintech.loan`

Stores loan-level information.

| Field Name | Type | Description |
|-----------|------|------------|
| loan_id | INTEGER | Unique loan identifier |
| customer_id | BYTES | Customer identifier |
| loan_status | STRING | Status of loan (Current, Charged Off, etc.) |
| loan_amount | NUMERIC | Total loan amount |
| state | STRING | Borrower's state |
| funded_amount | NUMERIC | Funded loan amount |
| term | STRING | Loan duration |
| int_rate | FLOAT | Interest rate |
| installment | FLOAT | Monthly installment |
| grade | STRING | Loan grade |
| issue_d | STRING | Issue date (raw format) |
| issue_date | STRING | Processed issue date |
| issue_year | NUMERIC | Year of loan issuance |
| pymnt_plan | BOOLEAN | Payment plan indicator |
| application | RECORD | Nested application details |

### 📌 Nested Fields
| Field | Description |
|------|------------|
| application.type | Loan type |
| application.purpose | Loan purpose |
| application.description | Description |
| application.notes | Additional notes |

---

## 🔹 Table: `fintech.customers`

Contains borrower details.

| Field Name | Type | Description |
|-----------|------|------------|
| customer_id | BYTES | Unique customer ID |
| emp_title | STRING | Job title |
| emp_length | STRING | Employment duration |
| home_ownership | STRING | Ownership status |
| annual_inc | FLOAT | Annual income |
| annual_inc_joint | FLOAT | Joint income |
| verification_status | STRING | Income verification status |
| zip_code | STRING | ZIP code |
| addr_state | STRING | State |
| avg_cur_bal | NUMERIC | Average current balance |
| tot_cur_bal | NUMERIC | Total current balance |

---

## 🔹 Table: `fintech.state_region`

Mapping table for states and regions.

| Field Name | Type | Description |
|-----------|------|------------|
| state | STRING | State code |
| subregion | STRING | Subregion |
| region | STRING | Region |

---

## 🔹 Table: `fintech.loan_with_region`

Derived table combining loan data with region.

| Field Name | Type | Description |
|-----------|------|------------|
| loan_id | INTEGER | Loan identifier |
| loan_amount | NUMERIC | Loan amount |
| region | STRING | Region mapped from state |

📌 Created by joining:
- `loan.state = state_region.state`

---

## 🔹 Table: `fintech.loan_count_by_year`

Aggregated table for yearly loan counts.

| Field Name | Type | Description |
|-----------|------|------------|
| issue_year | NUMERIC | Year of loan |
| loan_count | INTEGER | Total loans issued |

---

## 🔹 Table: `fintech.loan_purposes`

Stores distinct loan purposes.

| Field Name | Type | Description |
|-----------|------|------------|
| purpose | STRING | Loan purpose |

---

## 🧠 Notes

- Nested fields were accessed using dot notation (e.g., `application.purpose`)
- Data transformations were done using SQL (CTAS queries)
- Aggregations used `GROUP BY`, `COUNT`, and filtering
- Joins were used to enrich loan data with region information
