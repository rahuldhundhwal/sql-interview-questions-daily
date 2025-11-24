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

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium 

```sql
MySQL Solution: 

```
## 🧩 Question 5

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium 

```sql
MySQL Solution:
 
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
