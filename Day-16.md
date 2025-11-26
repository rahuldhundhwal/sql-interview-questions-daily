# 🗓️Day 16 — SQL Practice Journal

**Date:** 25/11/2025  
**Platform(s):** [Newton School]  
**Total Questions Solved:** 10  

---

## 🧠 Overview


---

## 🧩 Question 1

**Title:** Business Trips
   
**Link:** [🔗 Click to Open Problem](https://my.newtonschool.co/playground/database/8uyfjrzwpi3p)    
**Difficulty:** Medium  

```sql
MySQL Solution:
with helper as(
    select
        purpose,
        round(sum(miles) over(partition by purpose order by purpose),1) as total_miles
    from trip_data
    order by round(sum(miles) over(partition by purpose),1) desc
)
select 
    purpose,
    total_miles
from helper
group by purpose,total_miles
order by total_miles desc
limit 3
```
## 🧩 Question 2

**Title:**    
**Link:** [🔗 Click to Open Problem]()    
**Difficulty:** Medium  

```sql
MySQL Solution: 
```
## 🧩 Question 3

**Title:** 
   
**Link:** [🔗 Click to Open Problem]()  
**Difficulty:** Medium  

```sql
MySQL Solution:
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
