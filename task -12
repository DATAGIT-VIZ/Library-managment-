-------- TASK 1 -----
-- create a new book record 
select  from books;
Insert into books(isbn,book_title,category,rental_price,status,author,publisher)
values( '978-1-60129-456-2','To Kill a Mockingbird','Classic',6.00,'yes','Harper Lee','J.B . Lippincott & Co.');

-------- TASK 2 -----
-- Update Existing member

Update members 
set  member_address='125 Main St'
where member_id= 'C101';
select * from members

-------- TASK 3 -----
-------Delete a record from issued status
Delete from issued_status 
where issued_id= 'IS121';
select * from issued_status  

---------  TASK 4-----
----- Retrieve all books issued by a specific
select * from issued_status 
where issued_emp_id = 'E101'


 -------TASK 5----
 -- List members who have issued more than one book 
 
 SELECT 
    issued_emp_id, 
    COUNT(*) 
FROM issued_status
GROUP BY 1
HAVING COUNT(*) > 1;

--CTAS
-----Task 6: Create Summary Tables: Use CTAS to generate new tables based on query results - each book and total book_issued_cnt**

create table books_cnts
AS
select  
b.isbn,
count(ist.issued_id) as no_issued
from books as b 
join
issued_status as ist 
on ist.issued_book_isbn=b.isbn 
group by 1,2;
 
select * from books_cnts

---- Task 7. Retrieve All Books in a Specific Category:
select * from books
where category = 'Classic';

-----Task 8: Find Total Rental Income by Category:
select 
category ,
sum(rental_price),
COUNT(*)
as total_rental_income
from books
group by category 
order by total_rental_income desc;

----TASK 9 List Members Who Registered in the Last 180 Days:

SELECT * FROM MEMBERS
WHERE
reg_date>=  Current_date - interval '180 days';

select current_date 

insert into members(member_id,member_name,member_address,reg_date)
values
('C120','SAM','St jacinto','2024-06-01');

----Task 10 List Employees with Their Branch Manager's Name and their branch details:

SELECT 
    e1.emp_id,
    e1.emp_name,
    e1.position,
    e1.salary,
    b.*,
    e2.emp_name as manager
FROM employees as e1
JOIN 
branch as b
ON e1.branch_id = b.branch_id    
JOIN
employees as e2
ON e2.emp_id = b.manager_id

------ Task 11 Create a Table of Books with Rental Price Above a Certain Threshold:

create table expensive_books as 
select * from books

where rental_price > 7

select * from expensive_books
-----Task 12: Retrieve the List of Books Not Yet Returned
select *
from issued_status as ist 
left join 
return_status as rs
on ist.issued_id= rs.issued_id
where rs.return_id is NULL
select * from return_status 
