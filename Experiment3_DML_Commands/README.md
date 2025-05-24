# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**

![image](https://github.com/user-attachments/assets/18151131-72f1-4f6c-9c98-9e21d716d821)

```sql
UPDATE suppliers set supplier_name=UPPER(supplier_name) where contact_person like '%Singh%';
```

**Output:**

![image](https://github.com/user-attachments/assets/9b3493b3-bd3e-4275-9f97-0ccb87b46514)

**Question 2**

![image](https://github.com/user-attachments/assets/7dbbac53-7bbe-46bc-ba07-a62efc5e9cda)


```sql
update suppliers set supplier_name="A1 Suppliers" where supplier_id=8;
```

**Output:**

![image](https://github.com/user-attachments/assets/d9f8a47b-c7b4-4ffc-96c1-0ae31c66e9c6)


**Question 3**

![image](https://github.com/user-attachments/assets/abb426a6-eaf0-4dc9-b6cb-2be710b4c0f3)


```sql
update sales set sell_price=sell_price+0.05*sell_price where sale_date='2023-01-31';
```

**Output:**

![image](https://github.com/user-attachments/assets/1ab9c33b-7bf3-48e2-8efe-ebd6a11fd276)


**Question 4**

![image](https://github.com/user-attachments/assets/59d640fb-408e-43b1-a952-3b0b7b23406e)


```sql
delete from Customer  where WORKING_AREA is 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/b288590d-044c-4d44-b3ee-175343783192)


**Question 5**

![image](https://github.com/user-attachments/assets/0aae3e2d-3e98-4cf2-af90-28a7032d2470)

```sql
update PRODUCTS
set reorder_lvl= reorder_lvl*0.7
where product_name like '%cream%' and quantity >reorder_lvl;
```

**Output:**

![image](https://github.com/user-attachments/assets/3615a992-5cf9-426c-be07-4d1935faeced)


**Question 6**

![image](https://github.com/user-attachments/assets/ccb0fc61-9552-48de-b1b1-2020b2001838)


```sql
delete from Doctors
where specialization ='Cardiology';

```

**Output:**

![image](https://github.com/user-attachments/assets/9ad75cfb-d182-4870-9673-661a03ee58fa)


**Question 7**

![image](https://github.com/user-attachments/assets/d759e99d-b8bc-4e3e-b1b3-4b0d4f25e4f6)


```sql
delete from Doctors
where doctor_id  = 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/98308334-1ab1-438e-b441-e4022e5028fe)


**Question 8**

![image](https://github.com/user-attachments/assets/8aaf23ab-55bd-470e-ad04-c58ff4b88d4e)


```sql
delete from Surgeries
where surgery_id = 3;
```

**Output:**

![image](https://github.com/user-attachments/assets/82af037c-520b-444e-93a6-3454cf2be4d3)


**Question 9**

![image](https://github.com/user-attachments/assets/cfef455f-cded-4543-8582-b3a5bc6159f6)


```sql
delete from Customer
where (GRADE=2 and CUST_NAME like 'M%')
and PAYMENT_AMT<3000;
```

**Output:**

![image](https://github.com/user-attachments/assets/917dba5d-c4d1-4197-8ac7-e3480da7f2f1)


**Question 10**

![image](https://github.com/user-attachments/assets/0a90d793-4152-4f0f-b4f9-ffcd04a789d2)


```sql
delete from Customer
where GRADE >2 
and PAYMENT_AMT <(select avg(PAYMENT_AMT)from Customer)
or OUTSTANDING_AMT>8000;
```

**Output:**

![image](https://github.com/user-attachments/assets/b57099ee-b384-4fda-97fb-a70bfbfaf1d3)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
