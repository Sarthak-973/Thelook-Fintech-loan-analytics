# 📊 Exploratory Queries

## 🔹 Purpose
These queries are used for initial data exploration and understanding of the dataset.

---
🔹 1. Explore Loan Table
```sql
SELECT *
FROM fintech.loan
LIMIT 100;
```
🔹 2. Explore Customers Table
```sql
SELECT *
FROM fintech.customers
LIMIT 100;
```
🔹 3. Loan Status Distribution
```sql
SELECT 
  loan_status, 
  COUNT(*) AS total_loans
FROM fintech.loan
GROUP BY loan_status
ORDER BY total_loans DESC;
```
🔹 4. Nested Field Exploration
```sql
SELECT 
  loan_id,
  application.purpose AS purpose
FROM fintech.loan
LIMIT 100;
```
