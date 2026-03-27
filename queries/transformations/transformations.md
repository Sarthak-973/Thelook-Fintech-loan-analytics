# 🔄 Transformation Queries

## 🔹 Purpose
These queries are used to clean, join, and transform raw data into structured datasets for analysis.

---

## 🔹 Queries

###🔹 1. Create State-Region Table
```sql
CREATE OR REPLACE TABLE fintech.state_region (
  state STRING,
  region STRING
);
```
🔹2. Join Loan Data with Region (Preview)
```sql
SELECT 
  l.loan_id,
  l.loan_amount,
  l.addr_state,
  s.region
FROM fintech.loan l
JOIN fintech.state_region s
ON l.addr_state = s.state;
```
🔹3. Create Enriched Table (loan_with_region)
```sql
CREATE TABLE fintech.loan_with_region AS
SELECT 
  l.loan_id,
  l.loan_amount,
  l.addr_state,
  s.region
FROM fintech.loan l
JOIN fintech.state_region s
ON l.addr_state = s.state;
```
