# 🔄 Transformation Queries

## 🔹 Purpose
These queries are used to clean, join, and transform raw data into structured datasets for analysis.

---

🔹 1. Create State-Region Table by CSV Import
```sql
LOAD DATA OVERWRITE fintech.state_region
(
state string,
subregion string,
region string
)
FROM FILES (
format = 'CSV',
uris = ['data/state_region.csv']); -- Source: data/state_region.csv (local project file)
```
🔹2. Join Loan Data with Region (Preview)
```sql
SELECT
lo.loan_id,
lo.loan_amount,
sr.region
FROM fintech.loan lo
INNER JOIN fintech.state_region sr
ON lo.state = sr.state;
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
