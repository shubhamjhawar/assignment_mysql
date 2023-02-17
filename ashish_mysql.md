# Ashish Approach

#### Q1
- Created `TABLE1` using `CREATE TABLE`.
- Used `COUNT` with a subquery to build male and female columns. 
- Subquery uses `CASE` statement which assigns 0 or 1 based on the column.

#### Q2

- Created `TABLE2` using `CREATE TABLE`.
- For Salary column used `CASE`. First case was to determine if January was the highest salary month. If not then compared February to assign the highest.
- Similary for Month column used `CASE`. Building similar cases as in Salary column, assigned the months.

#### Q3

- Created `TABLE3` using `CREATE TABLE`.
- Used `GROUP BY` to divide based on marks.
- Used `GROUP_CONCAT` to combine Ids with same marks.
- To give ranks, used `DENSE_RANK` with `ORDER BY` on marks.

### Q4

-  Used nested subquery to delete and select from the same table



