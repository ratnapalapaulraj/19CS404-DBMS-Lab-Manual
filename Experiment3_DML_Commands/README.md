# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.

### 2. UPDATE
Used to modify records in a relation.

### 3. DELETE
Used to delete records from a relation.

### 4. SELECT
Used to retrieve records from a table.

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
