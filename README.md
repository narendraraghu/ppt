# ppt

--Max salary
select * from employee where salary= (select max(salary) from employee)

--select highest salary in employee
	select max(salary) from employee;

--select second highest salary from employee
select max(salary) from employee
where salary not in (select max(salary) from employee)

--select employee range from employee based on ids
select * from employee where employee_id between 2001 and 299999;

--select employee name salary and depatname
select e.first_name , salary, depatname_name
from Employee e Inner Join Dept d ON (e.depatname_id = d.depatname_id)
where salary IN (select max(salary) from employee)

-- return highest salary employee name  and depatname
 select e.first_name , salary, depatname_name
from Employee e Inner Join Dept d ON (e.depatname_id = d.depatname_id)
where salary IN (select max(salary) from employee)
group by depatname_id
