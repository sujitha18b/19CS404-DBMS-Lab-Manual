# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**

![image](https://github.com/user-attachments/assets/2e8c6b2b-7940-45d6-b72e-67e5946b0485)


```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    o.customer_id, 
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s 
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/d923a7e9-1b01-4ede-b031-dcfec47f21bc)

**Question 2**

![image](https://github.com/user-attachments/assets/d713bd35-b2e8-486b-979f-12ef362f703e)


```sql
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
); 
```

**Output:**

![image](https://github.com/user-attachments/assets/49d4a56f-9c39-4d46-9bc2-bfe5ff322e3d)


**Question 3**

![image](https://github.com/user-attachments/assets/f4951d8f-ed38-41d7-a55f-fff4fb7bc356)


```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';

```

**Output:**

![image](https://github.com/user-attachments/assets/44eec90e-ee54-47ec-8e28-080d97a3e717)


**Question 4**

![image](https://github.com/user-attachments/assets/03362ae9-b768-4ddd-b2e8-2c8115016cc3)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY = 1500;
```

**Output:**

![image](https://github.com/user-attachments/assets/11ea27d1-fafc-4cd9-87cb-0ee3b64edd2d)


**Question 5**

![image](https://github.com/user-attachments/assets/7dd1fb1d-9ec6-45d5-83b5-6b0f5e4f8391)


```sql
SELECT *
FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 1000000
);

```

**Output:**

![image](https://github.com/user-attachments/assets/846d5fdf-3a23-455a-b444-8692e0c56085)


**Question 6**

![image](https://github.com/user-attachments/assets/c4a8f25f-b40e-428e-8c8a-0ebdda07c273)


```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    o.customer_id, 
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s 
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/995ab955-ecaa-4b81-a2d4-c763ea1eb177)


**Question 7**

![image](https://github.com/user-attachments/assets/16c45802-38de-4c69-8535-fe88f458d0df)


```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    o.ord_date, 
    o.customer_id, 
    o.salesman_id
FROM 
    orders o
JOIN 
    salesman s 
ON 
    o.salesman_id = s.salesman_id
WHERE 
    s.city = 'London';
```

**Output:**

![image](https://github.com/user-attachments/assets/31395506-3315-46b9-b3bb-bbc0ef13c79a)


**Question 8**

![image](https://github.com/user-attachments/assets/8170e6e1-3c1a-412b-9100-20b92a5c80bd)

```sql
SELECT 
    department_id,
    department_name
FROM 
    Departments
WHERE 
    LENGTH(department_name) > (
        SELECT AVG(LENGTH(department_name))
        FROM Departments
    );
```

**Output:**

![image](https://github.com/user-attachments/assets/1506a59a-b5c2-42c5-85c2-d3d4f6ff95a9)


**Question 9**

![image](https://github.com/user-attachments/assets/5348a4f7-1b4e-44ec-816b-1b29e818c0b7)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;
```

**Output:**

![image](https://github.com/user-attachments/assets/abd32388-8eb5-4481-94a0-3dae0d7b543b)


**Question 10**

![image](https://github.com/user-attachments/assets/89ed9208-dcb7-4491-889a-e27a4323a550)


```sql
SELECT 
    s.salesman_id, 
    s.name
FROM 
    salesman s
JOIN 
    customer c ON s.salesman_id = c.salesman_id
GROUP BY 
    s.salesman_id, s.name
HAVING 
    COUNT(c.customer_id) > 1;

```

**Output:**

![image](https://github.com/user-attachments/assets/73c30272-a81e-4803-99ce-2abb87f347f7)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
