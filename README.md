

## MYSQL Assignment

## 1
Given a table of employees, find the number of male and female employees in each
department:


```mysql
CREATE TABLE employees (
  EmpID INT PRIMARY KEY,
  Name VARCHAR(10),
  Gender VARCHAR(10),
  Department VARCHAR(25)
);

INSERT INTO employees (EmpID, Name, Gender, Department)
VALUES
  (1, 'X', 'Female', 'Finance'),
  (2, 'Y', 'Male', 'IT'),
  (3, 'Z', 'Male', 'HR'),
  (4, 'W', 'Female', 'IT');

SELECT Department,
       SUM(Gender = 'Female') AS "Num of Female",
       SUM(Gender = 'Male') AS "Num of Male"
FROM employees
GROUP BY Department;
```



## 2
Given a table with salaries of employees for different month, find the max amount from the
rows with month name:

```mysql
CREATE TABLE employee_salaries (
  Name VARCHAR(50),
  Jan INT,
  Feb INT,
  Mar INT
);

INSERT INTO employee_salaries (Name, Jan, Feb, Mar)
VALUES
  ('X', 5200, 9093, 3832),
  ('Y', 9023, 8942, 4000),
  ('Z', 9834, 8197, 9903),
  ('W', 3244, 4321, 2093);



WITH data AS (
  SELECT Name, 'Jan' AS Month, Jan AS Salary FROM employee_salaries
  UNION ALL
  SELECT Name, 'Feb' AS Month, Feb AS Salary FROM employee_salaries
  UNION ALL
  SELECT Name, 'Mar' AS Month, Mar AS Salary FROM employee_salaries
)

SELECT d1.Name,d1.Salary,d1.Month FROM data AS d1 WHERE d1.Salary = (SELECT max(salary) FROM data AS d2 WHERE d1.name = d2.name GROUP BY d2.Name) ORDER BY d1.Name;
```

## 3
Given the marks obtained by candidates in a test, rank them in proper order.

````mysql
Create table test_results( Candidate_ID int ,Marks Int);

INSERT INTO test_results (Candidate_ID, Marks)
VALUES
  (1, 98),
  (2, 78),
  (3, 87),
  (4, 98),
  (5, 78);

SELECT Marks,ROW_NUMBER() OVER (ORDER BY marks DESC) AS Ranking,GROUP_CONCAT(Candidate_ID) FROM test_results GROUP BY marks ;

````

## 4

4. If same value is repeated for different id, then keep the value that has smallest id and delete
all the other rows having same value:

````mysql

INSERT INTO candidates (Candidate_ID, Email)
VALUES
  (45, 'abc@gmail.com'),
  (23, 'def@yahoo.com'),
  (34, 'abc@gmail.com'),
  (21, 'bcf@gmail.com'),
  (94, 'def@yahoo.com');
WITH old_candidates AS (
SELECT * FROM candidates
)
DELETE FROM candidates
WHERE Candidate_ID NOT IN (
SELECT MIN(Candidate_ID) FROM old_candidates
GROUP BY Email
);
````





