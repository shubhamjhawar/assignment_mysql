
# Dhruv approach

#### Q1
- Used joins to do it but will fill the table with NULLS need to run another query to replace them with zeroes
- Used left and right join to complete the table as follows and give the desired output 
- Created the full join using left and right join


#### Q2

Created SCHEMA q2 and TABLE employees. Inserted values into the table.
To create the table similar to result he used UNION to combine three tables (corressponding to each month).
Example table for January looks like this.
Query - SELECT `Name`, Jan AS `Value`, "Jan" AS `Month` FROM employees
Then for filtering he used a WHERE matching name and salary from a table containing the name and maximum salary (using GREATEST) of each employee.

#### Q3


-For combining ids with comma he used GROUP_CONCAT to join rows with same value.
For ranks variable @rk = rk + 1 was used and order was done based on rank

### Q4

-  For deleting I used a subquery to select the the minimum id for each email.
- Then he used NOT IN for selecting and deleting rows with larger IDs. Since we cannot use the table from which we are deleting in the WHERE clause in MySQL, I nested SELECT to bypass this situation.



