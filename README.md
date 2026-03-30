
## 📘 HAVING vs WHERE

This project demonstrates the difference between the **WHERE** clause and the **HAVING** clause in SQL using practical examples.

---

## 🔍 Key Concepts

### WHERE Clause

* Filters rows **before** grouping
* Cannot be used with aggregate functions like `AVG()`, `SUM()`, etc.
* Commonly used to limit raw data

### HAVING Clause

* Filters data **after aggregation**
* Works with aggregate functions like:

  * `AVG()`
  * `SUM()`
  * `COUNT()`
* Used together with `GROUP BY`

---

## 📊 Examples Included

### 1. HAVING with GROUP BY

Filters grouped results based on aggregated values.

```sql
SELECT gender, AVG(age)
FROM employee_demographics
GROUP BY gender
HAVING AVG(age) > 40;
```
<img width="1747" height="936" alt="image" src="https://github.com/user-attachments/assets/f259403b-c1d8-46d0-9e18-472b5f0468d0" />

---

### 2. GROUP BY Only

Groups data and calculates averages.

```sql
SELECT occupation, AVG(salary)
FROM employee_salary
GROUP BY occupation;
```
<img width="1576" height="820" alt="image" src="https://github.com/user-attachments/assets/6b9cebdf-589a-49ba-9ded-877d1f543877" />

---

### 3. WHERE with GROUP BY

Filters rows before grouping.

```sql
SELECT occupation, AVG(salary)
FROM employee_salary
WHERE occupation LIKE '%manager%'
GROUP BY occupation;
```
<img width="1482" height="754" alt="image" src="https://github.com/user-attachments/assets/b0690248-d9fd-451e-8efa-9eaefc6c6087" />

---

### 4. WHERE + HAVING Together

Filters both before and after aggregation.

```sql
SELECT occupation, AVG(salary)
FROM employee_salary
WHERE occupation LIKE '%manager%'
GROUP BY occupation
HAVING AVG(salary) > 75000;
```
<img width="1586" height="789" alt="image" src="https://github.com/user-attachments/assets/20dc07ec-74c6-412a-be00-052b9a4b62a7" />

---

## 🧠 Summary

| Clause | When it Runs    | Purpose                    |
| ------ | --------------- | -------------------------- |
| WHERE  | Before GROUP BY | Filters raw rows           |
| HAVING | After GROUP BY  | Filters aggregated results |

---

## 🚀 Author

Winnie Ngamau
