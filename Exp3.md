# <center>Experiment No. 3  
### NAME: ADITYA  
### DBMS Lab – SQL Queries with Conditions and Functions  

### Aim  
To perform SQL queries using sorting, pattern matching, conditional operators and arithmetic operations on EMPLOYEE_MASTER table.

---

### Theory  

SQL provides various operators and clauses to retrieve and manipulate data efficiently.

- **ORDER BY** → Sorts data (ASC / DESC)  
- **LIKE** → Pattern matching using wildcards (% , _)  
- **IN** → Matches values from a list  
- **IS NULL / IS NOT NULL** → Checks NULL values  
- **Arithmetic Operations** → Used for calculations (SAL + COMM, SAL * 12)  
- **IFNULL()** → Handles NULL values  

These operations help in analyzing and filtering data effectively.

---

### 1. List all employees and jobs in Department 30 in descending order by salary  
~~~sql
SELECT ENAME, JOB, SAL
FROM Employee_master
WHERE DEPTNO = 30
ORDER BY SAL DESC;
~~~

### 2. List job and department number of employees  
~~~sql
SELECT JOB, DEPTNO
FROM Employee_master
WHERE ENAME LIKE 'A___N';
~~~

### 3. Display names of employees whose name starts with S  
~~~sql
SELECT ENAME
FROM Employee_master
WHERE ENAME LIKE 'S%';
~~~

### 4. Display names of employees whose name ends with S  
~~~sql
SELECT ENAME
FROM Employee_master
WHERE ENAME LIKE '%S';
~~~

### 5. Display names of employees working in department 10, 20, 40 or working as clerk, salesman or analyst  
~~~sql
SELECT ENAME
FROM Employee_master
WHERE DEPTNO IN (10, 20, 40)
   OR JOB IN ('CLERK', 'SALESMAN', 'ANALYST');
~~~

### 6. Display employee number and names of employees who earn commission  
~~~sql
SELECT EMPNO, ENAME
FROM Employee_master
WHERE COMM IS NOT NULL
AND COMM > 0;
~~~

### 7. Display employee number and total salary (salary + commission)  
~~~sql
SELECT EMPNO, SAL + IFNULL(COMM, 0) AS TOTAL_SALARY
FROM Employee_master;
~~~

### 8. Display employee number and annual salary  
~~~sql
SELECT EMPNO, SAL * 12 AS ANNUAL_SALARY
FROM Employee_master;
~~~

### 9. Display names of employees working as clerks earning more than 3000  
~~~sql
SELECT ENAME
FROM Employee_master
WHERE JOB = 'CLERK'
AND SAL > 3000;
~~~

### 10. Display names of employees working as clerk, salesman or analyst earning more than 3000  
~~~sql
SELECT ENAME
FROM Employee_master
WHERE JOB IN ('CLERK', 'SALESMAN', 'ANALYST')
AND SAL > 3000;
~~~

---

### Result  
All SQL queries using sorting, conditions and functions were executed successfully.

---

### Conclusion  
This experiment helped in understanding sorting, pattern matching and performing calculations using SQL queries.
