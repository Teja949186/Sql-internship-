CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    name VARCHAR(50),
    department VARCHAR(50),
    salary INT
);

INSERT INTO employees VALUES
(1, 'Ravi', 'IT', 50000),
(2, 'Sita', 'HR', 40000),
(3, 'Arjun', 'IT', 60000),
(4, 'Meena', 'Finance', 45000),
(5, 'Kiran', 'IT', 70000);
SELECT name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
SELECT name
FROM employees
WHERE salary = (SELECT MAX(salary) FROM employees);
SELECT department, AVG(salary) AS avg_salary
FROM (SELECT * FROM employees) AS temp
GROUP BY department;
SELECT name, salary,
(SELECT AVG(salary) FROM employees) AS company_avg
FROM employees;
SELECT name
FROM employees
WHERE department IN (
    SELECT department
    FROM employees
    GROUP BY department
);
SELECT e.name
FROM employees e
JOIN employees d
ON e.department = d.department;
SELECT name, salary, department
FROM employees e1
WHERE salary > (
    SELECT AVG(salary)
    FROM employees e2
    WHERE e1.department = e2.department
);
