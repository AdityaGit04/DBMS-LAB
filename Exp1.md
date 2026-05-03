# <center>Experiment No. 1  
### NAME: ADITYA  
### DBMS Lab – DDL, DML and DQL Operations  

### Aim  
To perform and understand SQL operations including table creation, insertion, deletion, updating and modification using Employee and Department tables.

---

### Theory  

SQL (Structured Query Language) is used to manage and manipulate relational databases.

**DDL (Data Definition Language):**  
Used to define database structure (CREATE, ALTER, DROP)

**DML (Data Manipulation Language):**  
Used to modify data (INSERT, UPDATE, DELETE)

**DQL (Data Query Language):**  
Used to retrieve data (SELECT)

**Constraints Used:**  
PRIMARY KEY, FOREIGN KEY, NOT NULL  

These commands help in creating, managing and modifying structured data efficiently.

---

### 1. Create Employee_master Table  
~~~sql
CREATE TABLE Employee_master(
    EMPNO INT PRIMARY KEY,
    ENAME VARCHAR(20) NOT NULL,
    JOB VARCHAR(20),
    MGR INT,
    HIREDATE DATE,
    SAL INT(10),
    COMM INT(7),
    DEPTNO INT(2),
    FOREIGN KEY(DEPTNO) REFERENCES Department(DEPTNO)
);
~~~

### 2. Describe Employee_master Table  
~~~sql
DESC Employee_master;
~~~

### 3. Describe Department Table  
~~~sql
DESC Department;
~~~

### 4. Insert Data into Department  
~~~sql
INSERT INTO Department (DEPTNO, DNAME) VALUES
(10, 'RESEARCH'),
(20, 'ACCOUNTING'),
(30, 'SALES'),
(40, 'OPERATIONS');
~~~

### 5. Display Department Table  
~~~sql
SELECT * FROM Department;
~~~

### 6. Insert Data into Employee_master  
~~~sql
INSERT INTO Employee_master
(EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES
(7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800, NULL, 20),
(7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600, 300, 30),
(7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250, 300, 30),
(7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975, NULL, 20),
(7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250, 1400, 30),
(7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850, NULL, 30),
(7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450, NULL, 20),
(7788, 'SCOTT', 'ANALYST', 7566, '1982-12-09', 3000, NULL, 40),
(7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000, NULL, 20),
(7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500, 0, 30),
(7876, 'ADAMS', 'CLERK', 7788, '1983-01-12', 1100, NULL, 20),
(7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950, NULL, 30),
(7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000, NULL, 20),
(7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300, NULL, 10);
~~~

### 7. Display Employee_master Table  
~~~sql
SELECT * FROM Employee_master;
~~~

### 8. Delete Records where DEPTNO = 10  
~~~sql
DELETE FROM Employee_master
WHERE DEPTNO = 10;
~~~

### 9. Update Salary by 10% where DEPTNO = 20  
~~~sql
UPDATE Employee_master
SET SAL = SAL * 1.10
WHERE DEPTNO = 20;
~~~

### 10. Alter Table (Modify SAL Data Type)  
~~~sql
ALTER TABLE Employee_master
MODIFY SAL FLOAT(10,2);
~~~

### 11. Drop Employee_master Table  
~~~sql
DROP TABLE Employee_master;
~~~

---

### Result  
All SQL operations such as CREATE, INSERT, UPDATE, DELETE and ALTER were successfully executed.

---

### Conclusion  
This experiment helped in understanding practical implementation of SQL commands and how data is managed inside relational databases.
