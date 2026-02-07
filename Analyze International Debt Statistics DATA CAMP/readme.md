# 🌍 World Bank International Debt Analysis

**Tools Used:** SQL (PostgreSQL)  
**Project Status:** Completed ✅

## 📖 Project Overview
This project analyzes the World Bank's international debt data to answer critical questions regarding the debt burden of developing nations. The goal is to extract specific insights using SQL queries.

---

## 🔍 Analysis & Solutions

### 1. Total Distinct Countries
**Question:** What is the number of distinct countries present in the database?

```sql
SELECT Count(Distinct country_name ) AS total_distinct_countries
From public.international_debt;
Result: The total number of distinct countries is [124].
--
2. Highest Debt Country
Question: What country has the highest amount of debt?


SELECT Country_Name , sum(debt) AS total_debt
from public.international_debt
Group by country_name
order by total_debt DESC
limit 1;

Result: [China] has the highest total debt, amounting to $285,793,494,734.2.  

--

3. Lowest Principal Repayment
Question: What country has the lowest amount of principal repayments (Indicator: "DT.AMT.DLXF.CD")?

SELECT country_name , indicator_name , debt AS lowest_repayment
FROM public.international_debt
where indicator_code = 'DT.AMT.DLXF.CD'
order by debt ASC
limit 1;

Result: [Timor-Laste] recorded the lowest principal repayment of $825,000.
