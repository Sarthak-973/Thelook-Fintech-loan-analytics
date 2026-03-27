# 📈 Final Business Queries

## 🔹 Purpose
These queries generate business-ready datasets and insights for reporting and dashboarding.

---

🔹 1. Unique Loan Purposes
```sql
CREATE TABLE fintech.loan_purposes AS
SELECT DISTINCT application.purpose AS purpose
FROM fintech.loan;
```
🔹2. Loan Count by Year
```sql
CREATE TABLE fintech.loan_count_by_year AS
SELECT 
  issue_year,
  COUNT(loan_id) AS loan_count
FROM fintech.loan
GROUP BY issue_year
ORDER BY issue_year;
```
🔹3. Top 10 States by Loan Count
```sql
SELECT 
  addr_state,
  COUNT(loan_id) AS total_loans
FROM fintech.loan
GROUP BY addr_state
ORDER BY total_loans DESC
LIMIT 10;
```
