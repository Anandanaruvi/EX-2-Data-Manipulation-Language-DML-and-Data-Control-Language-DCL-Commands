# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

DATE:DATE: 11-08-2023

## AIM:
To create a manager database and execute DML queries using SQL.

## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```
sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
UPDATE manager
SET salary = salary + (salary * 0.10),
annualsalary = annualsalary + (annualsalary * 0.10);
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/76ad542e-bce5-4e3b-adfe-e40b58edf92a)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
DELETE FROM manager WHERE salary < 2750;
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/b25af04c-9f68-4411-b97c-2a80f18ef719)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
SELECT ename AS "Name", salary * 12 AS "Annual Salary"
FROM manager;
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/dcb86dde-d464-4318-afe8-b7617fe4824b)

### Q5)	List the names of Clerks from emp table.

### QUERY:
```
SELECT ename from manager where designation='clerk';
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/6d4bf690-493b-4f2c-9824-b58242f02b57)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```
SELECT ename from manager where designation!='manager';
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/b5baa858-6bf7-4f40-93b1-b34ecd0540ba)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
SELECT ename from manager where commission=0;
```

### OUTPUT:

![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/b1c9f5d3-438a-4e83-b386-f10530e87be5)

### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
SELECT ename
FROM manager
WHERE ename LIKE 'S%' OR ename LIKE '%s';
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/393999f2-6917-42de-bf86-f6cf7c2d2fd9)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation,deptno,Hiredate from manager
order by Hiredate asc;
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/a958cfbf-8789-4927-8a6f-20bf6fb349ea)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
SELECT *
FROM manager
WHERE Hiredate < TO_DATE('1981-09-30', 'YYYY-MM-DD');
```

### OUTPUT:

![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/ded64d2f-c0c6-4320-9843-84a76c6ac23e)

### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from manager order by deptno asc;
select ename,deptno,salary from manager order by salary desc;
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/a1a4c19d-9968-481a-8791-5e66a3828690)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (10,30,40);
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/29d1eefe-285e-43fd-8ee4-07793a0ffef5)

### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/330210bf-fa53-4cb9-bdca-025ca95c5b50)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select ename ,salary,annualsalary from manager
where salary = (select max(salary) from manager);

select ename ,salary,annualsalary from manager
where salary = (select min(salary) from manager);

select avg(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/e9651ca4-c36c-4a1c-9b5e-de5d307a685a)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation, COUNT(*) AS "Number of Employees"
FROM manager
GROUP BY designation
ORDER BY COUNT(*) DESC;
```

### OUTPUT:
![image](https://github.com/Anandanaruvi/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120443233/68fa36e7-756a-4356-b33f-ee9cf05c76ca)

RESULT:
Thus, Manager database is created and DML queries such as insertion, updation, deletion are executed using SQL.


SUBMITTED BY: A.ARUVI

REG.NO:212222230014
