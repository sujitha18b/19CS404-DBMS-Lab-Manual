# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**

![image](https://github.com/user-attachments/assets/c3b0c716-edde-4b55-9ed0-fa415a9f2290)

```sql
insert into Products(Name,Category,price,Stock)
values("Smartphone","Electronics",800,150),
("Headphones","Accessories",200,300);
```

**Output:**

![image](https://github.com/user-attachments/assets/77b66349-99c7-4733-a75e-554413b17835)

**Question 2**

![image](https://github.com/user-attachments/assets/cddac2fa-c338-4b6a-93da-44d0e9c71491)

```sql
 create table item(
item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),foreign key(icom_id)
references company(com_id) on update set null on delete set null);
```

**Output:**

![image](https://github.com/user-attachments/assets/29842080-c27a-4c97-90ad-5fc7cdc156a8)


**Question 3**

![image](https://github.com/user-attachments/assets/34a31de9-e572-44e6-9137-960888a7e97e)


```sql
create table Department(
DepartmentID int primary key,
DepartmentName varchar(50) UNIQUE NOT NULL,
Location varchar(100));

```

**Output:**

![image](https://github.com/user-attachments/assets/185c3c10-3ac2-4c2a-a7bb-c8514498fcd4)


**Question 4**

![image](https://github.com/user-attachments/assets/21b60cef-f66a-4ba7-b9b6-baa415be5636)

```sql
create table jobs(
job_id int,
job_title varchar(50) default "",
min_salary int default 8000,max_salary int);
```

**Output:**

![image](https://github.com/user-attachments/assets/098908b6-c729-4be8-a3ef-310bf8309935)

**Question 5**

![image](https://github.com/user-attachments/assets/7a16f295-af88-4fe0-a080-a87ae51fec92)

```sql
alter table Employees add column Date_of_joi Date;
alter table employees rename column job_title to Designation;
```

**Output:**

![image](https://github.com/user-attachments/assets/e905512e-db2b-4585-8bb6-98e45f57615e)

**Question 6**

![image](https://github.com/user-attachments/assets/c6926aa9-6ccb-4331-b129-b79a85648673)

```sql
insert into Products(ProductID,ProductName,Price,Stock)
select ProductID,ProductName,Price,Stock from Discontinued_products;

```

**Output:**

![image](https://github.com/user-attachments/assets/9edf9879-1443-4be3-8a14-1aa421dad797)


**Question 7**

![image](https://github.com/user-attachments/assets/64781f5c-9491-4cba-a0b6-ca17ed004d25)


```sql
alter table Companies add column designation varchar(50);
alter table Companies add column net_salary number;
```

**Output:**

![image](https://github.com/user-attachments/assets/2ee93ae1-f314-4a9d-9d05-d5925c8aea7b)


**Question 8**

![image](https://github.com/user-attachments/assets/2c2d3c99-89b1-497f-a2c9-d73b198a641d)

```sql
create table item(item_id varchar(50) primary key,item_desc varchar(50) not null,
rate int not null,icom_id char(4),
foreign key(icom_id) references company(com_id) on update cascade on delete cascade);
```

**Output:**

![image](https://github.com/user-attachments/assets/b96ad6d5-6ac2-46be-9d36-0aeb6730a21c)


**Question 9**

![image](https://github.com/user-attachments/assets/574bba99-c3d8-4e16-919c-17d6006f9457)


```sql
insert into Student_details(RollNo,Name,Gender) values(204,"Samuel Black","M");
```

**Output:**

![image](https://github.com/user-attachments/assets/ee19dabe-5b18-44bb-b7a3-61231e0cf313)


**Question 10**

![image](https://github.com/user-attachments/assets/22c3fa53-b403-4308-8ab5-6824c807ebad)

```sql
create table Customers(CustomerID INTEGER,Name TEXT,Email TEXT,JoinDate DATETIME);
```

**Output:**

![image](https://github.com/user-attachments/assets/0d3e5aa0-c8dd-49a7-9024-4edc585ced05)

GRADES:

![image](https://github.com/user-attachments/assets/02492fbe-de38-4d1a-ac03-37559e755709)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
