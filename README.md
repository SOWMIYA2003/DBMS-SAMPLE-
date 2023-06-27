# DBMS-SAMPLE-
### 1
```
1. 
a)	List the details of the books whose quantity below 15 and year of publication is below 2015
b)	List the details of book whose publication is not equal to W3school
c)	Arrange the book by Ascending order
d)	Create List all the books name in decending order of year_of_publication 
e)	Delete the details of the book whose author is dennis.

```
```
CREATE TABLE Book(
	id int,
    bname varchar(255),
    bauthor varchar(255),
    bquantity int ,
    byearpublish int,
    publication varchar(255),
    bprice int
);

INSERT INTO Book VALUES (101,'DBMS','Scott',12,2014,'Kim',234);
INSERT INTO Book VALUES (102,'C# PROGRAMMING','Dennis',17,2015,'Wast',214);
INSERT INTO Book VALUES (103,'C++ PROGRAM','Grey',14,2014,'W3school',314);
INSERT INTO Book VALUES (104,'SQL','Travis',14,2012,'Herny',244);
INSERT INTO Book VALUES (105,'ORACLE','Dennis',10,2011,'W3school',444);
INSERT INTO Book VALUES (106,'PYTHON','Dennis',11,2014,'Kesh',254);
INSERT INTO Book VALUES (107,'JAVA','Denver',15,2015,'Fenrn',250);

SELECT *FROM Book;

SELECT *FROM Book WHERE bquantity < 15 AND byearpublish < 2015;

SELECT *FROM Book WHERE publication <> 'W3school';

SELECT * FROM Book ORDER BY bname ASC;

SELECT bname , byearpublish FROM Book ORDER BY byearpublish DESC;

DELETE FROM Book WHERE bauthor = 'Dennis';

SELECT *FROM Book;

```
### 2
```
2.
a)	Delete the table
b)	Delete the database
c)	Rename the database
d)	Modify the column price from integer to float in book table.
e)	Modify the price value & Book title

```
```
CREATE DATABASE BookD;
CREATE TABLE Book(
	id int,
    bname varchar(255),
    bauthor varchar(255),
    bquantity int ,
    byearpublish YEAR,
    publication varchar(255),
    bprice int
);

INSERT INTO Book VALUES (101,'DBMS','Scott',12,2014,'Kim',234.23);
INSERT INTO Book VALUES (102,'C# PROGRAMMING','Dennis',17,2015,'Wast',214.23);
INSERT INTO Book VALUES (103,'C++ PROGRAM','Grey',14,2014,'W3school',314.83);
INSERT INTO Book VALUES (104,'SQL','Travis',14,2012,'Herny',244.76);
INSERT INTO Book VALUES (105,'ORACLE','Dennis',10,2011,'W3school',444.54);
INSERT INTO Book VALUES (106,'PYTHON','Dennis',11,2014,'Kesh',254.24);
INSERT INTO Book VALUES (107,'JAVA','Denver',15,2015,'Fenrn',250.34);

SELECT *FROM Book;

ALTER TABLE Book MODIFY COLUMN bprice FLOAT;
SELECT *FROM Book;

UPDATE Book SET bprice = 800, bname = 'Physics' WHERE id = 101;
SELECT *FROM Book;

RENAME DATABASE MyDatabase TO Newdata;

DROP TABLE Book;
DROP DATABASE BookD;


```
### 3 
```
3.
a)	Create an employee table with attributes empid,name,experience,salary,city
b)	Add age column inside the table
c)	List the details of the employee whose salary is greater than 50000
d)	List the details of the employee whose city is Chennai
e)	Delete the table

```
```
CREATE DATABASE EmployeeDetails;
CREATE TABLE Employee(
    empid int,
    ename varchar(255),
    experience float,
    salary int,
    city varchar(255)
);

INSERT INTO Employee VALUES(101,'Suresh',2.5,'25000','Chennai');
INSERT INTO Employee VALUES(102,'Arjun',3.5,'45000','Chennai');
INSERT INTO Employee VALUES(103,'Vimal',1,'22000','Theni');
INSERT INTO Employee VALUES(104,'Kesh',5,'24000','Chennai');
INSERT INTO Employee VALUES(105,'Denver',4,'67000','Madurai');
INSERT INTO Employee VALUES(106,'Maddy',1.5,'54000','Salem');

SELECT *FROM Employee;

ALTER TABLE Employee ADD age INT;
UPDATE Employee SET age=25 WHERE empid < 150;
SELECT *FROM Employee;

SELECT *FROM Employee WHERE salary>50000;

SELECT *FROM Employee WHERE city = 'Chennai';

DROP TABLE Employee;

```
### 4
```
4.
EMPLOYEES (Employee_Id, First_Name, Last_Name, Email, Phone_Number, Hire_Date,
Job_Id, Salary, Commission_Pct, Manager_Id, Department_Id)
a)	List out the employees who works under manager 100
b)	Find the names of the employees who have a salary greater than or equal to 4800
c)	List out the employees whose last name is ‘AUSTIN’
d)	Find the names of the employees who works in departments 60,70 and 80
e)	Display the unique Manager_Id.

```
```
create table employees (
	Emp_id int,
       First_name varchar(255),
    Last_name varchar(255),
    Email varchar(255),
    Phone_No varchar(255),
    Hire_date varchar(255),
    Job_Id int,
    Emp_Salary int,
	Comission_Pct int,
	manager_id int,
	Department_id int
);

insert into employees values(47401,'Rama','Rao','RamaRao@gmail.com','8965324170','28-Jan-2003',301,60000,601,100,60);
insert into employees values(47402,'Ranga','Reddy','RangaReddy@gmail.com','7020321450','23-Jun-2004',302,56464,602,101,70);
insert into employees values(47403,'Raja','Shekhar','RajaSheker@gmail.com','9848002255','12-aug-2004',303,58451,603,103,80);
insert into employees values(47404,'Ravi','AUSTIN','RaviAustin@gmail.com','9701811356','30-sep-2006',304,36520,604,100,90);
insert into employees values(47405,'Ranga','Raju','RnagaRaju@gmail.com','9032553262','17-May-2014',305,2568,605,105,60);

SELECT *FROM employees;

select Emp_id,First_Name,Last_Name,Emp_Salary from employees;

select * from employees where manager_id=100;

select * from employees where EMP_SALARY>=4800;

select * from employees where Last_Name='AUSTIN';

select * from employees where DEPARTMENT_ID IN(60,70,80);

select DISTINCT(MANAGER_ID) from employees;


```
### 5
```
5. Create Client_master with the following fields(ClientNO, Name, Address, City, State, bal_due)
( a ) Insert five records
( b ) Find the names of clients whose bal_due> 5000 .
( c ) Change the bal_due of ClientNO “ C123” to Rs. 5100
( d ) Change the name of Client_master to Client12 .
( e ) Display the bal_due heading as “BALANCE”

```
```
create table Client_Master(
	Client_no varchar(6),
	Client_Name varchar(255),
	Client_Address varchar(25),
	Client_City varchar(20),
	Client_State varchar(20),
	Balance_Due int
);

insert INTO CLIENT_MASTER Values('C123','Ramesh','L B Nagar', 'Hyderabad',    'Telangana', 7000);
insert INTO CLIENT_MASTER Values('C124', 'Suresh', 'Dilsuknagar', 'Hyderabad', 'Telangana',6000);
insert INTO CLIENT_MASTER Values('C125','Vignesh','Saroor nagar', 'Hyderabad', 'Telangana',3500);
insert INTO CLIENT_MASTER Values('C126','Rajiv','A S Rao Nagar','Hyderabad', 'Telangana',4500);
insert INTO CLIENT_MASTER Values('C127','Ranga', 'Vanasthalipuram','Hyderabad', 'Telangana',5478);

select * from Client_Master; 

select Client_Name from Client_Master where Balance_Due>5000; 

update Client_Master set Balance_Due=5100 where Client_No='C123';
select * from Client_Master; 

RENAME TABLE Client_Master to Client12;

select Client_No, Balance_Due as Balance from Client12;

```
### 6
```
6. Create Sales table with the following fields( Sales No, Salesname, Branch, Salesamount, DOB)
( a ) Insert five records
( b ) Calculate total salesamount in each branch
( c ) Calculate average salesamount in each branch .
( d ) Display all the salesmen, DOB who are born in the month of December as day in
character format i.e. 21-Dec-09
( e ) Display the name and DOB of salesman in alphabetical order of the month.

```
```
Create Table Sales(
		Sales_No int,
		Sales_Name varchar(255),
		Branch varchar(255), 
		Sales_Amount int, 
		DOB DATE
);
DROP TABLE Sales;
insert into Sales VALUES(1020,'AutoMobiles','Hyderabad',68452,'1985-07-28');
insert into Sales VALUES(1021,'Electronics','Secunderabad',47850,'1995-12-22');
insert into Sales VALUES(1022,'Electronics','Secunderabad',44500,'1986-06-03');
insert into Sales VALUES(1023,'AutoMobiles','Hyderabad',74200,'1996-09-28');
insert into Sales VALUES(1024,'AutoMobiles','Hyderabad',54500,'1984-10-28');

select * from Sales;

select branch, sum(Sales_Amount) as total_sales_amount from sales group by Branch;

select branch, avg(Sales_Amount) as average_sales_amount from sales group by Branch;

select Sales_Name, DATE_FORMAT(DOB , "%d-%b-%y") AS DOB from sales where MONTH(DOB)=12;

select Sales_Name, DATE_FORMAT(DOB , "%d-%b-%y") AS FORMATTED_DATE from sales Order by MONTH(DOB) ASC;

```
### 7
```
7. (EmpNo, EmpName, Job,Basic, DA, HRA,PF, GrossPay, NetPay)
(Calculate DA as 30% of Basic and HRA as 40% of Basic)
( a ) Insert Five Records and calculate GrossPay and NetPay.
( b ) Display the employees whose Basic is lowest in each department .
( c ) If NetPay is less than <Rs. 10,000 add Rs. 1200 as special allowances .
( d ) Display the employees whose GrossPay lies between 10,000 & 20,000
( e ) Display all the employees who earn maximum salary

```
```
create table Employee (
	Emp_No int, 
	Emp_Name varchar(255) , 
	Designation varchar(255),
	Emp_Basic INT
);
insert into Employee values(4029,'Talatam Venkatesh','Director',10000);
insert into Employee values(4039,'Gumaa','Technical Engineer',15000);
insert into Employee values(4015,'Anudeep Varma','Technical Engineer',12000);
insert into Employee values(4016,'I Vasudeva Varma','Technical Engineer',13000);
insert into Employee values(4027,'Uday Reddy','Director',16000);
insert into Employee values(4006,'Sai Mani','Director',10000);

select *from Employee;

ALTER TABLE Employee ADD Emp_DA float;
UPDATE Employee SET Emp_DA=(30/100)*Emp_Basic;

alter table Employee add Emp_HRA float ;
update Employee set Emp_HRA=(40/100)*Emp_Basic;

alter table Employee add Emp_PF float;
update Employee set Emp_PF= Emp_basic*(12/100);

alter table Employee add Emp_Grosspay float;
update Employee set Emp_grosspay= Emp_HRA+Emp_DA+Emp_basic;

alter table Employee add Emp_netpay float;
update Employee set Emp_netpay=Emp_Grosspay-Emp_PF;

select * from Employee;

SELECT Emp_No, Designation,Emp_Name FROM Employee 
WHERE Emp_Basic IN (
  SELECT MIN(Emp_Basic) FROM Employee GROUP BY Designation
);

update Employee set Emp_netpay=emp_netpay+1200 where Emp_netpay<10000;
select * from Employee;

select * from Employee where Emp_Grosspay between 10000 and 20000;

select * from Employee where Emp_Grosspay = (select max(Emp_Grosspay) from Employee);


```
### 8
```
8. An Enterprise wishes to maintain a database to automate its operations. Enterprise is divided into certain departments and each department consists of employees. The following two tables describes the automation schemas
Dept (deptno, dname, loc)
Emp (empno, ename, job, mgr, hiredate, sal, comm, deptno)
a) Update the employee salary by 15%, whose experience is greater than 10 years.
b) Delete the employees, who completed 30 years of service.
c) Display the manager who is having maximum number of employees working under him?
d) Create a view, which contain employee names and their manage

```
```
create table dept(
deptno int, 
dname varchar(255) , 
loc varchar(255) 
);
insert into dept values(101, 'FINANCE','SYDNEY');
insert into dept values(102, 'AUDIT','MELBOURNE');
insert into dept values(103, 'MARKETING','PERTH');
insert into dept values(104, 'PRODUCTION','BRISBANE');
insert into dept values(105, 'Humanresource','hyderabad');

SELECT *FROM dept;

create table emp(
empno int , 
ename varchar(255), 
job varchar(255) , 
mgr int references emp(empno), 
hiredate date, 
sal int, 
comm int, 
deptno int
);

insert into emp (empno, ename ,job, hiredate, sal, deptno)  values(68319,'KAYLING','PRESIDENT','1991-11-18',6000.00,101);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(66928,'BLAZE','MANAGER',68319,'1991-06-09', 2750.00,103);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values (67832,'CLARE','MANAGER',68319,'1991-11-18', 2550.00,101);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(69062,'FRANK','ANALYST', 65646,'1991-12-03', 3100.00,102);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(63679,'SANDRINE','CLERK', 69062,'1990-12-18', 900.00,102);
insert into emp (empno, ename ,job,mgr, hiredate, sal,comm, deptno)   values(64989,'ADELYN','SALESMAN',66928,'1991-02-20', 1700.00,400, 103);
insert into emp (empno, ename ,job,mgr, hiredate, sal,comm, deptno)   values(68454,'TUCKER','SALESMAN', 66928,'1991-07-08', 1600.00, 0, 103);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno) values(68736,'ADNRES','CLERK', 67858,'1997-05-23', 1200.00,102);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(69000,'JULIUS','CLERK', 66928,'1991-12-03', 1050.00,103);

SELECT *FROM emp;

UPDATE Emp SET sal = sal * 1.15 WHERE YEAR(CURDATE()) - YEAR(hiredate) > 10;
SELECT *FROM emp;

create view mgrcount as select mgr, count(empno) total from emp group by mgr;
select mgr from mgrcount where total in (select max(total) from mgrcount);
SELECT *FROM mgrcount;

create view employee_manager as 
select e1.ename as employeename ,e2.ename as managername from emp e1, emp e2 where e1.mgr=e2.empno;
SELECT * FROM employee_manager;

DELETE FROM Emp WHERE YEAR(CURDATE()) - YEAR(hiredate) >= 30;
SELECT *FROM Emp;

/*no need*/
DROP VIEW mgrcount;
DROP VIEW employee_manager;
DROP TABLE emp;
DROP TABLE dept;

```
### 9
```
9. Using Employee Database perform the following queries
a) Determine the names of employee, who earn more than their managers.
b) Determine the names of employees, who take highest salary in their departments.
c) Determine the employees, who are located at the same place.
d) Determine the employees, whose total salary is like the minimum Salary of any
department.
e) Determine the department which does not contain any employees

```
```
Create  table empman(
	empid int,
    empname varchar(255),
    empsalary int,
    empcity varchar(255),
    empdept varchar(255),
    manid int,
    manname varchar(255),
    mansalary int,
    mancity varchar(255),
    mandept varchar(255)
);
INSERT INTO empman VALUES(101,'Arjun',20000,'Chennai','IT',201,'Manager1',30000,'Chennai','IT');
INSERT INTO empman VALUES(102,'Aakash',56000,'Kerala','Finance',201,'Manager2',45000,'Madurai','Finance');
INSERT INTO empman VALUES(103,'Aravind',31000,'Salem','Marketing',201,'Manager3',20000,'Theni','Marketing');
INSERT INTO empman VALUES(104,'David',45000,'Ambur','IT',201,'Manager1',30000,'Chennai','IT');
INSERT INTO empman VALUES(105,'James',20000,'Kanchi','Finance',201,'Manager2',45000,'Madurai','Finance');
INSERT INTO empman VALUES(106,'Mathew',19000,'Trichy','Marketing',201,'Manager3',20000,'Theni','Marketing');
INSERT INTO empman VALUES(107,'Nick',40000,'Chennai','IT',201,'Manager1',30000,'Chennai','IT');
SELECT *FROM empman;

select empid,empname from empman where empsalary>mansalary;

SELECT empname , empdept, empsalary  FROM empman
WHERE (empdept,empsalary) IN (
  SELECT empdept, MAX(empsalary)
  FROM empman
  GROUP BY empdept
);
select ename,dname from emp , dept where emp.deptno=dept.deptno order by dname;
select empno, ename, sal from emp where sal in(select max(sal) from emp group by deptno);
select dname from dept where deptno not in(select deptno from emp);

DROP TABLE empman;

```
### 10
```
10. Using the tables “DEPARTMENTS” and “EMPLOYEES” perform the following
queries
a) Display the employee details, departments that the departments are same in both the emp
and dept.
b) Display the employee name and Department name by implementing a left outer join.
c) Display the employee name and Department name by implementing a right outer join.
d) Display the details of those who draw the salary greater than the average salary.

```
```
create table dept(
deptno int, 
dname varchar(255) , 
loc varchar(255) 
);
insert into dept values(101, 'FINANCE','SYDNEY');
insert into dept values(102, 'AUDIT','MELBOURNE');
insert into dept values(103, 'MARKETING','PERTH');
insert into dept values(104, 'PRODUCTION','BRISBANE');
insert into dept values(105, 'Humanresource','hyderabad');

SELECT *FROM dept;

create table emp(
empno int , 
ename varchar(255), 
job varchar(255) , 
mgr int references emp(empno), 
hiredate date, 
sal int, 
comm int, 
deptno int
);

insert into emp (empno, ename ,job, hiredate, sal, deptno)  values(68319,'KAYLING','PRESIDENT','1991-11-18',6000.00,101);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(66928,'BLAZE','MANAGER',68319,'1991-06-09', 2750.00,103);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values (67832,'CLARE','MANAGER',68319,'1991-11-18', 2550.00,101);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(69062,'FRANK','ANALYST', 65646,'1991-12-03', 3100.00,102);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(63679,'SANDRINE','CLERK', 69062,'1990-12-18', 900.00,102);
insert into emp (empno, ename ,job,mgr, hiredate, sal,comm, deptno)   values(64989,'ADELYN','SALESMAN',66928,'1991-02-20', 1700.00,400, 103);
insert into emp (empno, ename ,job,mgr, hiredate, sal,comm, deptno)   values(68454,'TUCKER','SALESMAN', 66928,'1991-07-08', 1600.00, 0, 103);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno) values(68736,'ADNRES','CLERK', 67858,'1997-05-23', 1200.00,102);
insert into emp (empno, ename ,job,mgr, hiredate, sal, deptno)  values(69000,'JULIUS','CLERK', 66928,'1991-12-03', 1050.00,103);

SELECT *FROM emp;

select ename, dname from dept,emp where emp.deptno=dept.deptno;

SELECT ename,dname
FROM emp
LEFT JOIN dept
ON emp.deptno = dept.deptno;

SELECT ename,dname
FROM emp
RIGHT JOIN dept
ON emp.deptno = dept.deptno;

Select empno,sal from emp where sal > (select avg(sal) from emp);

/* need emp and dept table*/

```
