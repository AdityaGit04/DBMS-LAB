# <center>Experiment No. 4  
### NAME: ADITYA  
### DBMS Lab – Advanced SQL Queries and Conditions  

### Aim  
To perform advanced SQL queries using pattern matching, arithmetic operations, conditions, and update operations on EMPLOYEE_MASTER table.

---

### Theory  

Advanced SQL queries involve the use of:

- **LIKE operator** → Pattern matching using `%` and `_`  
- **ORDER BY** → Sorting data  
- **IN / NOT IN** → Filtering multiple values  
- **Arithmetic operations** → Calculations like salary increment, annual salary  
- **IS NULL / IS NOT NULL** → Checking NULL values  
- **UPDATE** → Modifying existing data  

These operations help in performing real-world data analysis and manipulation.

---

### 1. Employees who joined before 30-Jun-1980 OR after 31-Dec-1981  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE HIREDATE < '1980-06-30'
   OR HIREDATE > '1981-12-31';
~~~

### 2. Employees whose second letter is ‘A’  
~~~sql
SELECT ENAME
FROM EMPLOYEE_MASTER
WHERE ENAME LIKE '_A%';
~~~

### 3. Employees whose name is exactly 5 characters long  
~~~sql
SELECT ENAME
FROM EMPLOYEE_MASTER
WHERE ENAME LIKE '_____';
~~~

### 4. Employees whose second letter is ‘A’  
~~~sql
SELECT ENAME
FROM EMPLOYEE_MASTER
WHERE ENAME LIKE '_A%';
~~~

### 5. Employees NOT working as salesman, clerk, or analyst  
~~~sql
SELECT ENAME
FROM EMPLOYEE_MASTER
WHERE JOB NOT IN ('SALESMAN', 'CLERK', 'ANALYST');
~~~

### 6. Employee name with annual salary (highest first)  
~~~sql
SELECT ENAME, SAL * 12 AS ANNUAL_SALARY
FROM EMPLOYEE_MASTER
ORDER BY SAL DESC;
~~~

### 7. Display name, salary, HRA, DA, PF and total salary  
~~~sql
SELECT
  ENAME,
  SAL,
  SAL * 0.15 AS HRA,
  SAL * 0.10 AS DA,
  SAL * 0.05 AS PF,
  (SAL * (SAL * 0.15) * (SAL * 0.10) - (SAL * 0.05)) AS TOTALSAL
FROM EMPLOYEE_MASTER
ORDER BY TOTALSAL;
~~~

### 8. Increase salary by 10% for employees not eligible for commission  
~~~sql
UPDATE EMPLOYEE_MASTER
SET SAL = SAL * 1.10
WHERE COMM IS NULL;
~~~

### 9. Employees whose salary is more than 3000 after 20% increment  
~~~sql
SELECT ENAME, SAL * 1.20 AS INCREMENTED_SAL
FROM EMPLOYEE_MASTER
WHERE SAL * 1.20 > 3000;
~~~

### 10. Employees whose salary contains at least 3 digits  
~~~sql
SELECT ENAME, SAL
FROM EMPLOYEE_MASTER
WHERE SAL >= 100;
~~~

---

### Result  
All advanced SQL queries including pattern matching, calculations, and update operations were executed successfully.

---

### Conclusion  
This experiment enhanced understanding of advanced SQL concepts such as pattern matching, sorting, arithmetic operations, and updating records.
