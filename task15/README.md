CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    department VARCHAR(50),
    salary INT,
    joining_date DATE
);

INSERT INTO employees(name, department, salary, joining_date) VALUES
('Ravi','IT',50000,'2022-01-10'),
('Sita','HR',45000,'2021-03-15'),
('Arjun','IT',60000,'2020-07-20'),
('Meena','HR',48000,'2023-02-11'),
('Kiran','IT',55000,'2022-09-05');
SELECT name, department, salary,
ROW_NUMBER() OVER(PARTITION BY department ORDER BY salary DESC) AS row_num
FROM employees;
SELECT name, department, salary,
RANK() OVER(PARTITION BY department ORDER BY salary DESC) AS rank_num,
DENSE_RANK() OVER(PARTITION BY department ORDER BY salary DESC) AS dense_rank
FROM employees;
SELECT name, department, salary,
SUM(salary) OVER(PARTITION BY department ORDER BY salary) AS running_total
FROM employees;
SELECT name, salary,
LAG(salary) OVER(ORDER BY salary) AS previous_salary,
LEAD(salary) OVER(ORDER BY salary) AS next_salary
FROM employees;
SELECT name, department, salary,
AVG(salary) OVER(PARTITION BY department) AS avg_salary
FROM employees;
SELECT *
FROM (
    SELECT name, department, salary,
    RANK() OVER(PARTITION BY department ORDER BY salary DESC) AS rnk
    FROM employees
) t
WHERE rnk <= 2;
SELECT VERSION();
