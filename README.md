# SQL-Progress-Journal-day-16

# 💾 SQL Journey – Day 16: Task 7 Deep Dive

Today was all about solidifying my understanding of grouping and aggregation in SQL!

## 🧠 What I Learned

- ✅ The golden rule: **"What I want calculated, I aggregate. What I want calculated for, I group."**
- ✅ Difference between `JOIN` (to combine data) and `GROUP BY` (to summarize data)
- ✅ Used `AVG()`, `ROUND()`, and `GROUP BY` to explore salary averages by team and year
- ✅ Debugged why `GROUP BY` without aggregation can cause inconsistencies
- ✅ Learned to avoid unnecessary `GROUP BY` unless paired with aggregate functions

## 🛠 Commands I Practiced

```sql
SELECT teams.name, ROUND(AVG(salaries.salary), 2) AS "average salary"
FROM teams
JOIN salaries ON teams.id = salaries.team_id
WHERE salaries.year = 2000
GROUP BY teams.name
ORDER BY "average salary" DESC
LIMIT 5;

SELECT players.first_name, players.last_name
FROM players
JOIN salaries ON players.id = salaries.player_id
WHERE salaries.salary > 6000000 AND salaries.year IN (1999, 2000)
GROUP BY players.id
HAVING COUNT(DISTINCT salaries.year) = 2;

🎯 Reflection
I really locked in the logic behind grouping vs aggregating today — no more confusing when to use GROUP BY. Felt tired by the end of the day, but proud of the breakthroughs. Pacing matters!

📌 Onwards to Task 8 after some well-earned rest!
