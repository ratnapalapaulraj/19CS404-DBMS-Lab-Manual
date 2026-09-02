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
--
What is the average dosage prescribed for each medication?

Sample tablePrescriptions Table
<img width="842" height="117" alt="image" src="https://github.com/user-attachments/assets/06ec6c71-762b-4075-9045-79dc103dcc6e" />
For example:

Result
Medication     AvgDosage
-------------  ----------
Ciprofloxacin  500.0
Doxorubicin    60.0
Ibuprofen      400.0
Levothyroxine  50.0
Lisinopril     10.0
MMR            0.5
Pending        0.0
Prenatal vita  1.0
Sertraline     50.0
Topiramate     25.0

```sql
SELECT Medication,AVG(Dosage) AS AvgDosage
FROM Prescriptions
GROUP BY Medication
```

**Output:**

<img width="1266" height="737" alt="image" src="https://github.com/user-attachments/assets/d40d9bc0-a2a2-48af-8b6b-4d0a061d6fd5" />

**Question 2**
---
What is the average duration of insurance coverage for patients covered by each insurance company?

Sample table:Insurance Table

name               type
-----------------  ----------
InsuranceID        INTEGER
PatientID          INTEGER
InsuranceCompany   TEXT
PolicyNumber       TEXT
PolicyHolder       TEXT
StartDate          DATE
EndDate            DATE
For example:

Result
InsuranceCompany  AvgCoverageDurationDays
----------------  -----------------------
ABC Insurance     7.0
DEF Insurance     3.0
JKL Insurance     3.0
STU Insurance     3.0
VWX Insurance     3.0
XYZ Insurance     3.0
YZA Insurance     3.0

```sql
SELECT InsuranceCompany,AVG(EndDate - StartDate) AS AvgCoverageDurationDays
FROM Insurance
GROUP BY InsuranceCompany;
```

**Output:**

<img width="1267" height="690" alt="image" src="https://github.com/user-attachments/assets/d9362387-df12-4c70-928e-8f6f4f03076c" />

**Question 3**
---
What is the count of male and female patients?

Sample table: Patients Table
<img width="1076" height="161" alt="image" src="https://github.com/user-attachments/assets/632734f8-844e-46b7-ad43-30360ad9189a" />
For example:

Result
Gender      TotalPatients
----------  -------------
Female      5
Male        5

```sql
SELECT Gender,COUNT(Gender) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**

<img width="1262" height="406" alt="image" src="https://github.com/user-attachments/assets/4ad08a95-8453-47cd-b5bd-d6a8cd64d6af" />

**Question 4**
---
Write a SQL query to determine the number of customers who received at least one grade for their activity.

Sample table: customer

customer_id |   cust_name    |    city    | grade | salesman_id 

-------------+----------------+------------+-------+-------------

        3002 | Nick Rimando   | New York   |   100 |        5001

        3007 | Brad Davis     | New York   |   200 |        5001

        3005 | Graham Zusi    | California |   200 |        5002

 

For example:

Result
COUNT
----------
8

```sql
SELECT COUNT(grade>1) AS COUNT
FROM customer
```

**Output:**

<img width="1240" height="371" alt="image" src="https://github.com/user-attachments/assets/889fc6a9-969c-426a-b68e-996e692e3bfe" />

**Question 5**
---
Write a SQL query to find the customer with longest name?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT
city        TEXT
email       TEXT
phone       INTEGER
For example:

Result
name          length
------------  ----------
Preeti Patel  12

```sql
SELECT name,MAX(LENGTH(name)) AS length
FROM customer
```

**Output:**<img width="1323" height="365" alt="image" src="https://github.com/user-attachments/assets/c943955e-7f3f-4586-b6ba-5bcc69c3e114" />

**Question 6**
---
Write a SQL query to calculate the average purchase amount of all orders. Return average purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

 

For example:

Result
AVERAGE
----------
1461.765

```sql
SELECT AVG(purch_amt) AS AVERAGE
FROM orders;
```

**Output:**

<img width="1277" height="382" alt="image" src="https://github.com/user-attachments/assets/ea14a97c-5160-4707-be34-68872d52eb98" />

**Question 7**
---
Write a SQL query to return the total number of rows in the 'customer' table where the city is Noida.

Sample table: customer
<img width="668" height="138" alt="image" src="https://github.com/user-attachments/assets/340725bb-2dd3-494a-970b-1c99cce975af" />
For example:

Result
COUNT
----------
1

```sql
SELECT COUNT(*) AS COUNT
FROM customer
WHERE city='Noida';
```

**Output:**

<img width="1197" height="358" alt="image" src="https://github.com/user-attachments/assets/f5c28014-8980-41e4-8aeb-dae73ee9fe68" />

**Question 8**
---
Write the SQL query that achieves the selection of category and calculates the sum of the product of price and category ID as Revenue for each category from the "products" table, and includes only those products where the total revenue is greater than 25.

Sample table: products
<img width="972" height="212" alt="image" src="https://github.com/user-attachments/assets/4b933fb8-228f-4055-b102-1f1428114fae" />
For example:

Result
category_id  Revenue
-----------  ----------
1            49.5
2            126
3            79.44

```sql
SELECT category_id,
       SUM(price * category_id) AS Revenue
FROM products
GROUP BY category_id
HAVING SUM(price * category_id) > 25;
```

**Output:**
<img width="1152" height="356" alt="image" src="https://github.com/user-attachments/assets/048dd41b-1c99-4110-94a0-b47b29dfac39" />


**Question 9**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the minimum work hours for each date, and excludes dates where the minimum work hour is not less than 10.

Sample table: employee1
<img width="1031" height="203" alt="image" src="https://github.com/user-attachments/assets/77fce56e-7c9a-46b0-bfdf-027cb1e4cfc9" />
For example:

Result
jdate       MIN(workhour)
----------  -------------
2002.0      9
2004.0      9
2006.0      9

```sql
SELECT jdate,MIN(workhour)
FROM employee1
GROUP BY jdate;
```

**Output:**

<img width="1251" height="471" alt="image" src="https://github.com/user-attachments/assets/310e7636-0745-44ad-b460-f167768a32ad" />

**Question 10**
---
Write the SQL query that accomplishes the grouping of data by age intervals using the expression (age/5)5, calculates the minimum age for each group, and excludes groups where the minimum age is not less than 25.

Sample table: customer1
<img width="992" height="173" alt="image" src="https://github.com/user-attachments/assets/d19972be-c7c6-4e28-9ec1-3e42eb0c1de4" />
For example:

Result
age_group   MIN(age)
----------  ----------
20          22

```sql
SELECT (age/5)*5 AS age_group,MIN(age)
FROM customer1
GROUP BY (age/5)*5
HAVING MIN(age)<25;
```

**Output:**

<img width="1241" height="375" alt="image" src="https://github.com/user-attachments/assets/6c6968cd-6372-4cdb-aaea-b7c022af8666" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
