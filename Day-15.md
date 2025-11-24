# 🗓️Day 15 — SQL Practice Journal

**Date:** 22/11/2025  
**Platform(s):** [Newton School]  
**Total Questions Solved:** 10  

---

## 🧠 Overview


---

## 🧩 Question 1

**Title:** SQL - Delhi Metro-1
   
**Link:** [🔗 Click to Open Problem](https://my.newtonschool.co/playground/database/co6cbg4s0yym)    
**Difficulty:** Medium  

```sql
MySQL Solution:
select 
    station_name 
from 
Stations 
where line_name ="Violet Line" and 
station_name not in (
    select station_name
    from Stations
    where line_name="Red Line"
)
```
## 🧩 Question 2

**Title:** Salary brackets
   
**Link:** [🔗 Click to Open Problem](https://my.newtonschool.co/playground/database/nl97h4pc71yz)    
**Difficulty:** Medium  

```sql
MySQL Solution:
with helper1 as (
    select 
        emp_id,
        sum(amount) as amount,
        department_name
    from payments
    group by emp_id,department_name 
),helper as(
    select 
        department_name,
        sum(case when amount<5000 then 1 else 0 end) as low,
        sum(case when amount>=5000 and amount<=7000 then 1 else 0 end) as average,
        sum(case when amount>7000 then 1 else 0 end) as high,
        count(emp_id) as total_emp
    from helper1
    group by department_name
)
select 
    department_name,
    round(low*100/total_emp,2) as low_paid_percentage,
    round(average*100/total_emp,2) as average_paid_percentage,
    round(high*100/total_emp,2) as high_paid_percentage
from helper
order by department_name asc
```
## 🧩 Question 3

**Title:** Employees who have salary less then the average salary
   
**Link:** [🔗 Click to Open Problem](https://my.newtonschool.co/playground/database/2enz3f18u49w)  
**Difficulty:** Medium  

```sql
MySQL Solution:
with helper1 as(
    select 
        avg(salary) as avg_sal
    from employees
),
helper2 as(
    select 
        department,
        avg(salary) as dep_sal
    from employees
    group by department
    having avg(salary) >50000
)
select 
    employee_name,
    department
from employees e
where salary < (
    select 
    avg_sal from helper1
) and department in (select department from helper2)
order by employee_name
```
## 🧩 Question 4

**Title:** In app purchases!! 
   
**Link:** [🔗 Click to Open Problem](https://my.newtonschool.co/playground/database/a3qluk6aq33c)  
**Difficulty:** Medium 

```sql
MySQL Solution: 
WITH first_purchase AS (
    SELECT
        user_id,
        min(created_at) AS start_date
    FROM marketing_campaign
    GROUP BY user_id
),
initial_products AS (
    SELECT DISTINCT
        mc.user_id,
        mc.product_id
    FROM marketing_campaign mc
    JOIN first_purchase fp 
    ON mc.user_id = fp.user_id 
    AND mc.created_at = fp.start_date
),
subsequent_purchases AS (
    SELECT
        mc.user_id,
        mc.product_id
    from marketing_campaign mc
    JOIN first_purchase fp 
    ON mc.user_id = fp.user_id
    WHERE mc.created_at > fp.start_date
)

SELECT 
    count(distinct sp.user_id) as 'count(distinct user_id)'
FROM subsequent_purchases sp
left JOIN initial_products ip 
ON sp.user_id = ip.user_id 
AND sp.product_id = ip.product_id
WHERE ip.product_id IS NULL
```
## 🧩 Question 5

**Title:** Viewer but Streamer
   
**Link:** [🔗 Click to Open Problem](https://my.newtonschool.co/playground/database/0ext6olpamcu)  
**Difficulty:** Medium 

```sql
MySQL Solution:
with first_start as(
    select 
        user_id,
        min(session_start) as start_date
    from sessions
    group by user_id
),
viewers_start as(
    select 
        s.user_id
    from sessions s
    join first_start fs
    on s.session_start =fs.start_date
    and session_type='viewer'
)
select 
    s.user_id,
    sum(case when session_type ='streamer' then 1 else 0 end ) as streamer_sessions
from sessions s
where s.user_id in (
    select
     v.user_id
    from viewers_start v
)
group by s.user_id
order by streamer_sessions desc,s.user_id asc 
```
## 🧩 Question 6

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium 

```sql
MySQL Solution:
 
```
## 🧩 Question 7

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium 

```sql
MySQL Solution:
 
```
## 🧩 Question 8

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium 

```sql
MySQL Solution:
 
```
## 🧩 Question 9

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium 

```sql
MySQL Solution:
 
```
## 🧩 Question 10

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium 

```sql
MySQL Solution:
 
```
---
“Behind every dataset lies a decision — and every query is the key to unlocking it.”
----
