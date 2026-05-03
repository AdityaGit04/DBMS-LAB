# <center>Experiment No. 5  
### NAME: ADITYA  
### DBMS Lab – Aggregate and String Functions  

### Aim  
To perform SQL queries using aggregate functions and string functions on EMPLOYEE_MASTER table.

---

### Theory  

SQL provides built-in functions to perform calculations and manipulate data.

**Aggregate Functions:**
- COUNT() → Counts number of records  
- SUM() → Calculates total  
- AVG() → Finds average  
- MAX() → Finds maximum value  
- MIN() → Finds minimum value  

**String Functions:**
- UPPER() → Converts to uppercase  
- LOWER() → Converts to lowercase  
- LENGTH() → Finds length of string  
- CONCAT() → Combines strings  

These functions help in data analysis and formatting.

---

### 1. Display total number of employees  
~~~sql
SELECT COUNT(*) AS Total_Employees
FROM EMPLOYEE_MASTER;
~~~

### 2. Display total salary of all employees  
~~~sql
SELECT SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE_MASTER;
~~~

### 3. Display maximum salary  
~~~sql
SELECT MAX(SAL)
FROM EMPLOYEE_MASTER;
~~~

### 4. Display minimum salary  
~~~sql
SELECT MIN(SAL)
FROM EMPLOYEE_MASTER;
~~~

### 5. Display average salary  
~~~sql
SELECT AVG(SAL)
FROM EMPLOYEE_MASTER;
~~~

### 6. Display maximum salary of clerks  
~~~sql
SELECT MAX(SAL)
FROM EMPLOYEE_MASTER
WHERE JOB = 'CLERK';
~~~

### 7. Display maximum salary in department 20  
~~~sql
SELECT MAX(SAL) AS MAXIMUM_SALARY
FROM EMPLOYEE_MASTER
WHERE DEPTNO = 20;
~~~

### 8. Display minimum salary of salesman  
~~~sql
SELECT MIN(SAL) AS MINIMUM_SALARY
FROM EMPLOYEE_MASTER
WHERE JOB = 'SALESMAN';
~~~

### 9. Display average salary of managers  
~~~sql
SELECT AVG(SAL) AS AVERAGE_SALARY
FROM EMPLOYEE_MASTER
WHERE JOB = 'MANAGER';
~~~

### 10. Display total salary of analyst in department 40  
~~~sql
SELECT SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE_MASTER
WHERE JOB = 'ANALYST'
AND DEPTNO = 40;
~~~

### 11. Display employee names in uppercase  
~~~sql
SELECT UPPER(ENAME)
FROM EMPLOYEE_MASTER;
~~~

### 12. Display employee names in lowercase  
~~~sql
SELECT LOWER(ENAME)
FROM EMPLOYEE_MASTER;
~~~

### 13. Display employee names in proper case  
~~~sql
SELECT CONCAT(
UCASE(SUBSTR(ENAME, 1, 1)),
LCASE(SUBSTR(ENAME, 2))
) AS EMP_NAME_ProperCase
FROM EMPLOYEE_MASTER;
~~~

### 14. Display length of your name  
~~~sql
SELECT LENGTH('ADITYA');
~~~

### 15. Display length of all employee names  
~~~sql
SELECT LENGTH(ENAME) AS NAME_LENGTH
FROM EMPLOYEE_MASTER;
~~~

---

### Result  
All aggregate and string functions were executed successfully.

---

### Conclusion  
This experiment helped in understanding how to perform calculations and manipulate text data using SQL functions.
