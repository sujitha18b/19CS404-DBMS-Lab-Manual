# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**

![image](https://github.com/user-attachments/assets/788d4766-dda6-490c-9b87-86739fcb80e2)


```sql
SELECT patients.first_name, surgeries.*
FROM patients
INNER JOIN surgeries
ON patients.patient_id = surgeries.patient_id
WHERE patients.date_of_birth > '1990-01-01';

```

**Output:**

![image](https://github.com/user-attachments/assets/2f62b468-ccfe-409e-8d76-5b426354efe6)


**Question 2**

![image](https://github.com/user-attachments/assets/a34011ab-b22d-4a13-9964-2368cdc92368)


```sql
SELECT orders.ord_no, 
       orders.purch_amt, 
       orders.ord_date, 
       customer.cust_name, 
       customer.city AS customer_city, 
       customer.grade, 
       salesman.name AS salesman_name, 
       salesman.city AS salesman_city, 
       salesman.commission
FROM orders
INNER JOIN customer ON orders.customer_id = customer.customer_id
INNER JOIN salesman ON orders.salesman_id = salesman.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/64d50c27-403b-4b25-b3be-53564b4db47c)


**Question 3**

![image](https://github.com/user-attachments/assets/4ea22625-f478-46d5-84fa-872f12aa8f8a)

```sql
SELECT customer.cust_name, 
       customer.city AS city, 
       customer.grade, 
       salesman.name AS Salesman, 
       salesman.city AS city
FROM customer
INNER JOIN salesman ON customer.salesman_id = salesman.salesman_id
WHERE customer.grade < 300
ORDER BY customer.customer_id ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/db7193d1-5cb1-4497-b3ef-e37136350d98)


**Question 4**

![image](https://github.com/user-attachments/assets/bc7aeaff-4797-4fd9-950e-92c565881e5d)


```sql
SELECT n.nurse_id, d.department_name
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE n.first_name = 'David' AND n.last_name = 'Moore';

```

**Output:**

![image](https://github.com/user-attachments/assets/73c4543d-3ed2-4357-a680-c50a0c01e106)


**Question 5**

![image](https://github.com/user-attachments/assets/399370f2-da21-4ccd-88a7-d29440f250e7)

```sql
SELECT o.ord_no, o.ord_date, o.purch_amt, c.cust_name AS "Customer Name", c.grade, s.name AS Salesman, s.commission
FROM orders o
INNER JOIN customer c ON o.customer_id = c.customer_id
INNER JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/813b7379-22be-40bb-a77a-26ec1678c4a9)

**Question 6**
![image](https://github.com/user-attachments/assets/c5637ee4-4765-450f-8247-0b35554122c3)

```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';


```

**Output:**

![image](https://github.com/user-attachments/assets/856f5c91-11c8-437a-8fce-11329f18fddb)

**Question 7**

![image](https://github.com/user-attachments/assets/0b0a7167-405b-427a-a00c-f846bc2c917d)


```sql
SELECT c.cust_name, s.name
FROM customer c
LEFT JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city = s.city;

```

**Output:**

![image](https://github.com/user-attachments/assets/539af6f5-b2e4-4aba-a160-6007819eb7b1)


**Question 8**


```sql
SELECT c.cust_name AS "Customer Name", 
       c.city AS "city", 
       s.name AS "Salesman", 
       s.commission AS "commission"
FROM customer c
JOIN salesman s ON c.salesman_id = s.salesman_id;

```

**Output:**



**Question 9**


```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';

```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
SELECT c.cust_name as "Customer Name", c.city AS city, s.name AS Salesman, s.city AS city, s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city != s.city
AND s.commission > 0.12;

```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
