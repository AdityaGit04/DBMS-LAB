# <center>Experiment No. 2  
### NAME: ADITYA  

### 1. List all distinct job in Employee  
~~~sql
SELECT DISTINCT JOB 
FROM EMPLOYEE_MASTER;
~~~

<pre>
+-----------+
| JOB       |
+-----------+
| CLERK     |
| SALESMAN  |
| MANAGER   |
| ANALYST   |
| PRESIDENT |
+-----------+
5 rows in set (0.034 sec)
</pre>

---

### 2. List all information about employee in Department Number 30  
~~~sql
SELECT * 
FROM EMPLOYEE_MASTER
WHERE DEPTNO = 30;
~~~

<pre>
+-------+--------+----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+----------+------+------------+------+------+--------+
|  7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600 |  300 |     30 |
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250 |  300 |     30 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250 | 1400 |     30 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850 | NULL |     30 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500 |    0 |     30 |
|  7900 | JAMES  | CLERK    | 7698 | 1981-12-03 |  950 | NULL |     30 |
+-------+--------+----------+------+------------+------+------+--------+
6 rows in set (0.001 sec)
</pre>

---

### 3. Find all department number with department names greater than 20  
~~~sql
SELECT DEPTNO, DNAME
FROM DEPARTMENT
WHERE DEPTNO > 20;
~~~

<pre>
+--------+------------+
| DEPTNO | DNAME      |
+--------+------------+
|     30 | SALES      |
|     40 | OPERATIONS |
+--------+------------+
2 rows in set (0.034 sec)
</pre>

---

### 4. Managers and clerks in department 30  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE DEPTNO = 30
AND JOB IN ('MANAGER','CLERK');
~~~

<pre>
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7698 | BLAKE | MANAGER | 7839 | 1981-05-01 | 2850 | NULL |     30 |
|  7900 | JAMES | CLERK   | 7698 | 1981-12-03 |  950 | NULL |     30 |
+-------+-------+---------+------+------------+------+------+--------+
2 rows in set (0.001 sec)
</pre>

---

### 5. Clerks info  
~~~sql
SELECT ENAME, EMPNO, DEPTNO
FROM EMPLOYEE_MASTER
WHERE JOB = 'CLERK';
~~~

<pre>
+--------+-------+--------+
| ENAME  | EMPNO | DEPTNO |
+--------+-------+--------+
| SMITH  |  7369 |     20 |
| ADAMS  |  7876 |     20 |
| JAMES  |  7900 |     30 |
| MILLER |  7934 |     10 |
+--------+-------+--------+
4 rows in set (0.001 sec)
</pre>

---

### 6. Managers not in department 30  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE JOB = 'MANAGER'
AND DEPTNO <> 30;
~~~

<pre>
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7566 | JONES | MANAGER | 7839 | 1981-04-02 | 2975 | NULL |     20 |
|  7782 | CLARK | MANAGER | 7839 | 1981-06-09 | 2450 | NULL |     20 |
+-------+-------+---------+------+------------+------+------+--------+
2 rows in set (0.001 sec)
</pre>

---

### 7. Dept 10 not manager/clerk  
~~~sql
SELECT *
FROM EMPLOYEE_MASTER
WHERE DEPTNO = 10
AND JOB NOT IN ('MANAGER','CLERK');
~~~

<pre>
Empty set (0.001 sec)
</pre>

---

### 8. Salary between 1200–1400  
~~~sql
SELECT ENAME, JOB, SAL
FROM EMPLOYEE_MASTER
WHERE SAL BETWEEN 1200 AND 1400;
~~~

<pre>
+--------+----------+------+
| ENAME  | JOB      | SAL  |
+--------+----------+------+
| WARD   | SALESMAN | 1250 |
| MARTIN | SALESMAN | 1250 |
| MILLER | CLERK    | 1300 |
+--------+----------+------+
3 rows in set (0.001 sec)
</pre>

---

### 9. Clerk/Analyst/Salesman  
~~~sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE_MASTER
WHERE JOB IN ('CLERK','ANALYST','SALESMAN');
~~~

<pre>
(10 rows output — same as your file)
</pre>

---

### 10. Names starting with M  
~~~sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE_MASTER
WHERE ENAME LIKE 'M%';
~~~

<pre>
+--------+--------+
| ENAME  | DEPTNO |
+--------+--------+
| MARTIN |     30 |
| MILLER |     10 |
+--------+--------+
2 rows in set (0.001 sec)
</pre>
