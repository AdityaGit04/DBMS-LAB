# <center>Experiment No. 2  
### NAME: ADITYA  
### DBMS Lab – Data Retrieval using SQL  

### Aim  
To perform SQL queries for retrieving specific data from EMPLOYEE_MASTER and DEPARTMENT tables using various conditions.

---

### Theory  

Data retrieval in SQL is performed using the **SELECT** statement.

Important clauses used:

- **DISTINCT** → Removes duplicate values  
- **WHERE** → Filters records based on condition  
- **AND / OR** → Combines multiple conditions  
- **IN / NOT IN** → Matches values from a list  
- **BETWEEN** → Filters values in a range  
- **LIKE** → Pattern matching  

These clauses help in extracting meaningful and filtered data from tables.

---

### 1. List all distinct jobs in Employee  
~~~sql
SELECT DISTINCT JOB
FROM EMPLOYEE_MASTER;
~~~

### 2. List all information about employee in Department Number 30  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE DEPTNO = 30;
~~~

### 3. Find all department number with department names greater than 20  
~~~sql
SELECT DEPTNO, DNAME
FROM DEPARTMENT
WHERE DEPTNO > 20;
~~~

### 4. Find all information about managers and clerks in department 30  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE DEPTNO = 30
AND (JOB = 'MANAGER' OR JOB = 'CLERK');
~~~

### 5. List employee name, employee number and department of all clerks  
~~~sql
SELECT ENAME, EMPNO, DEPTNO
FROM EMPLOYEE_MASTER
WHERE JOB = 'CLERK';
~~~

### 6. Find all managers not in department 30  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE JOB = 'MANAGER'
AND DEPTNO <> 30;
~~~

### 7. List all employees in department 10 who are not managers or clerks  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE DEPTNO = 10
AND JOB NOT IN ('MANAGER', 'CLERK');
~~~

### 8. Find employees and jobs earning between 1200 and 1400  
~~~sql
SELECT ENAME, JOB
FROM EMPLOYEE_MASTER
WHERE SAL BETWEEN 1200 AND 1400;
~~~

### 9. List name and department number of employees who are clerks, analyst or salesman  
~~~sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE_MASTER
WHERE JOB IN ('CLERK', 'ANALYST', 'SALESMAN');
~~~

### 10. List name and department number of employees whose names begin with M  
~~~sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE_MASTER
WHERE ENAME LIKE 'M%';
~~~

---

### Result  
All SELECT queries were executed successfully and required data was retrieved.

---

### Conclusion  
This experiment helped in understanding how to retrieve filtered data using SQL clauses like WHERE, LIKE, BETWEEN, and IN.
