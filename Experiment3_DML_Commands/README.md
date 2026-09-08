# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

DML (Data Manipulation Language) commands are used to manipulate the data stored in a database. The commonly used DML commands are **INSERT, UPDATE, DELETE, and SELECT**.

### 1. INSERT INTO

Used to add records into a relation.

**Syntax (Single Row):**

```sql
INSERT INTO table_name (field1, field2, ...) VALUES (value1, value2, ...);
```

**Syntax (Multiple Rows):**

```sql
INSERT INTO table_name (field1, field2, ...) VALUES
(value1, value2, ...),
(value3, value4, ...);
```

**Syntax (Insert from another table):**

```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```

### 2. UPDATE

Used to modify records in a relation.

**Syntax:**

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

---

# QUESTIONS AND PROGRAMS

## 1. INSERT INTO

### Question

Create a table and insert records into the table using the INSERT INTO command.

### Program

```sql
CREATE TABLE customer1 (
    id NUMBER,
    name VARCHAR2(30),
    age NUMBER,
    address VARCHAR2(50),
    salary NUMBER
);

INSERT INTO customer1 VALUES (1, 'Ramesh', 25, 'Chennai', 25000);
INSERT INTO customer1 VALUES (2, 'Suresh', 30, 'Kanchipuram', 30000);
INSERT INTO customer1 VALUES (3, 'Priya', 28, 'Madurai', 28000);
INSERT INTO customer1 VALUES (4, 'Kavi', 24, 'Coimbatore', 22000);
INSERT INTO customer1 VALUES (5, 'Arun', 32, 'Salem', 35000);

COMMIT;

SELECT * FROM customer1;
```

### Output

![Output 1](Q1_output.png)

---

## 2. UPDATE

### Question

Update the salary of a particular customer using the UPDATE command.

### Program

```sql
UPDATE customer1
SET salary = 40000
WHERE id = 2;

COMMIT;

SELECT * FROM customer1;
```

### Output

![Output 2](Q2_output.png)

---

## 3. DELETE

### Question

Delete a particular record from the customer table using the DELETE command.

### Program

```sql
DELETE FROM customer1
WHERE id = 4;

COMMIT;

SELECT * FROM customer1;
```

### Output

![Output 3](Q3_output.png)

---

## 4. SELECT

### Question

Retrieve records from the customer table using the SELECT command.

### Program

```sql
SELECT id, name, salary
FROM customer1;
```

### Output

![Output 4](Q4_output.png)

---

## 5. SELECT WITH WHERE CLAUSE

### Question

Display the details of customers whose salary is greater than 25000.

### Program

```sql
SELECT *
FROM customer1
WHERE salary > 25000;
```

### Output

![Output 5](Q5_output.png)

---

## 6. SELECT WITH ORDER BY

### Question

Display the customer details in ascending order of salary.

### Program

```sql
SELECT *
FROM customer1
ORDER BY salary ASC;
```

### Output

![Output 6](Q6_output.png)

---

## 7. UPDATE MULTIPLE COLUMNS

### Question

Update the address and salary of a customer using the UPDATE command.

### Program

```sql
UPDATE customer1
SET address = 'Bangalore',
    salary = 45000
WHERE id = 3;

COMMIT;

SELECT * FROM customer1;
```

### Output

![Output 7](Q7_output.png)

---

## 8. DELETE WITH CONDITION

### Question

Delete all customers whose salary is less than 25000.

### Program

```sql
DELETE FROM customer1
WHERE salary < 25000;

COMMIT;

SELECT * FROM customer1;
```

### Output

![Output 8](Q8_output.png)

---

## 9. SELECT USING CONDITION

### Question

Display the names and addresses of customers whose age is greater than 25.

### Program

```sql
SELECT name, address
FROM customer1
WHERE age > 25;
```

### Output

![Output 9](Q9_output.png)

---

## 10. SELECT USING MULTIPLE CONDITIONS

### Question

Display the details of customers whose age is greater than 25 and salary is greater than 25000.

### Program

```sql
SELECT *
FROM customer1
WHERE age > 25
AND salary > 25000;
```

### Output

![Output 10](Q10_output.png)

---

# RESULT

Thus, the DML commands such as **INSERT, UPDATE, DELETE, and SELECT** were studied and executed successfully.
## Question 1

![Question 1 and program](Q1_question_and_program.png)

**Program:**

```sql
UPDATE Customer
SET grade=5
WHERE city='Chennai';
```

**Output:**

![Output 1](Q1_output.png)

## Question 2

![Question 2 and program](Q2_question_and_program.png)

**Program:**

```sql
UPDATE suppliers
SET supplier_name = 'A1 Suppliers'
WHERE supplier_id = 8;
```

**Output:**

![Output 2](Q2_output.png)

## Question 3

![Question 3 and program](Q3_question_and_program.png)

**Program:**

```sql
UPDATE products
SET sell_price=sell_price*1.10
WHERE category = 'Bakery';
```

**Output:**

![Output 3](Q3_output.png)

## Question 4

![Question 4 and program](Q4_question_and_program.png)

**Program:**

```sql
UPDATE Employees
SET email='Unavailable'
```

**Output:**

![Output 4](Q4_output.png)

## Question 5

![Question 5 and program](Q5_question_and_program.png)

**Program:**

```sql
UPDATE products
SET quantity =quantity*1.10;
```

**Output:**

![Output 5](Q5_output.png)

## Question 6

![Question 6 and program](Q6_question_and_program.png)

**Program:**

```sql
DELETE FROM Customer
WHERE CUST_CITY != 'New York'
AND OUTSTANDING_AMT > 5000;
```

**Output:**

![Output 6](Q6_output.png)

## Question 7

![Question 7 and program](Q7_question_and_program.png)

**Program:**

```sql
DELETE FROM Customer
WHERE AGENT_CODE = 'A003' OR
AGENT_CODE = 'A008';
```

**Output:**

![Output 7](Q7_output.png)

## Question 8

![Question 8 and program](Q8_question_and_program.png)

**Program:**

```sql
DELETE FROM Doctors
WHERE doctor_id>=2 AND doctor_id<=4;
```

**Output:**

![Output 8](Q8_output.png)

## Question 9

![Question 9 and program](Q9_question_and_program.png)

**Program:**

```sql
DELETE FROM Doctors
WHERE specialization='Pediatrics' AND
first_name = 'Michael';
```

**Output:**

![Output 9](Q9_output.png)

## Question 10

![Question 10 and program](Q10_question_and_program.png)

**Program:**

```sql
DELETE FROM Customer
WHERE GRADE=2
AND CUST_NAME LIKE '%M%'
AND PAYMENT_AMT<3000;
```

**Output:**

![Output 10](Q10_output.png)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
