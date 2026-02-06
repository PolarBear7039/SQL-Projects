# 🧠 Analyzing Students' Mental Health in SQL

## 📌 Project Overview
Does going to university in a different country affect your mental health? A Japanese international university conducted a survey in 2018 to answer this question. The study suggests that international students might face higher risks of mental health difficulties.

This project utilizes **SQL (PostgreSQL)** to explore the relationship between **Length of Stay** and the average mental health diagnostic scores of international students.

The analysis focuses on three key tests:
* **PHQ-9:** Patient Health Questionnaire (Depression Test).
* **SCS:** Social Connectedness Scale.
* **ASISS:** Acculturative Stress Scale.

## 🛠️ Tools & Technologies
* **SQL (PostgreSQL):** Used for Data Aggregation, Filtering, and Grouping.
* **Data Analysis:** Investigating trends in mental health scores over time.
* **Data Visualization:** Creating Combo Charts to compare sample size vs. average scores.

## 🔍 The Analysis Code
To analyze the impact of the length of stay on international students (`inter_dom = 'Inter'`), I executed the following SQL query:

```sql
SELECT 
	stay,
	count(*) AS count_int,
	round(AVG(todep), 2) AS average_phq, 
	Round(AVG(tosc), 2) AS average_scs,
	round(Avg(toas), 2) AS average_as                                        
FROM students   
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
