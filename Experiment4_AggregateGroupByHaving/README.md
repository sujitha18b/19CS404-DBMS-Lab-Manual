# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**

![image](https://github.com/user-attachments/assets/8d2c240a-0722-4ca7-b2d1-048c536983f4)


```sql
select 
PatientID,
count(*) as TotalAppointments
from
Appointments
group by
PatientID
order by
PatientID;
```

**Output:**

![image](https://github.com/user-attachments/assets/00d4de7f-dbbd-4e56-ad4d-0316df31fada)


**Question 2**

![image](https://github.com/user-attachments/assets/3f8a08f0-b433-4dc7-83ac-d9d074252a27)


```sql
select
strftime('%H',AppointmentDateTime) as "HourOfDay",
count(*) as "TotalAppointments"
from
Appointments
group by
strftime('%H',AppointmentDateTime)
order by
HourOfDay;
```

**Output:**

![image](https://github.com/user-attachments/assets/e22cab2d-fc4b-4d74-a7ae-87b0311e5575)


**Question 3**

![image](https://github.com/user-attachments/assets/ac3dfc06-0de9-4455-891a-b24aeb52e354)


```sql
select
strftime('%Y',ValidityPeriod) as "ValidityYear",
count(*) as "TotalPatients"
from
Insurance 
group by
strftime('%Y',ValidityPeriod)
order by
ValidityYear;
```

**Output:**

![image](https://github.com/user-attachments/assets/a9282aa2-8f1d-4de0-a5a5-cc1f59f20d14)


**Question 4**

![image](https://github.com/user-attachments/assets/a0281d3c-a2a3-4f64-ad99-53eb8b3624d8)

```sql
select
count(*) as "COUNT"
from
customer
where
city!= 'Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/56f9f1f3-27af-4f1b-89f0-b44058a34944)

**Question 5**

![image](https://github.com/user-attachments/assets/89675c30-4737-44ce-a568-9c9a6523fbb4)

```sql
select
name as "fruit_name",
min(inventory) as "lowest_quantity"
from
fruits
group by
name
order by
min(inventory)asc
limit 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/9af2a783-253e-421d-aad0-2aa138577503)

**Question 6**

![image](https://github.com/user-attachments/assets/01940608-f0a6-4c65-aef7-56b552c6de3c)


```sql
select
name,
max(length(name)) as "length"
from
customer
order by
max(length(name))asc
 limit 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/3b101303-836e-45c2-b198-02265ee5cf0f)


**Question 7**

![image](https://github.com/user-attachments/assets/fcebb145-56e4-42e1-bdfb-8b5e55b0fb8c)


```sql
select
name,
email,
min(length(email)) as"min_email_length"
from
customer
order by
min(length(email))
limit 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/b07d85f2-c06f-4d0e-9f1d-a22fbde43de3)

**Question 8**

![image](https://github.com/user-attachments/assets/b6ea0588-e18c-47c1-aac4-083c873e6da8)


```sql
select 
(age/5)*5 as "age_group",
min(salary) as"MIN(salary)"
from
customer1
group by
(age/5)*5
having
min(salary)<2000
order by
age_group;
```

**Output:**

![image](https://github.com/user-attachments/assets/c45b5b5a-8f6c-40e6-b24e-bb27ca135852)

**Question 9**

![image](https://github.com/user-attachments/assets/f22820cf-96b1-4d51-8187-a10e9b53d67d)


```sql
select
jdate,
sum(workhour) as "SUM(workhour)"
from
employee1
group by
jdate
having
sum(workhour)>40
order by
jdate;
```

**Output:**

![image](https://github.com/user-attachments/assets/ebcdaf74-b273-4088-a206-5c1e87348e85)


**Question 10**

![image](https://github.com/user-attachments/assets/416baccf-8139-41a0-81ec-29febc0569fc)

```sql
select
address,
sum(salary) as "SUM(salary)"
from
customer1
group by
address
having
sum(salary)>2000
order by
address;
```

**Output:**

![image](https://github.com/user-attachments/assets/14964167-d0c3-4507-84df-6c6f1210625e)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
