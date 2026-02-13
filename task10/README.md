CREATE TABLE departments (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(50)
);

CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    name VARCHAR(50),
    dept_id INT,
    salary INT,
    FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
);

INSERT INTO departments VALUES
(1,'IT'),
(2,'HR'),
(3,'Finance');

INSERT INTO employees VALUES
(101,'Ravi',1,60000),
(102,'Sita',2,45000),
(103,'Arjun',1,70000),
(104,'Meena',3,50000);
SELECT e.emp_id, e.name, d.dept_name, e.salary
FROM employees e
JOIN departments d
ON e.dept_id = d.dept_id
WHERE e.salary > 50000;
CREATE VIEW high_salary_employees AS
SELECT e.emp_id, e.name, d.dept_name, e.salary
FROM employees e
JOIN departments d
ON e.dept_id = d.dept_id;
SELECT * FROM high_salary_employees;
SELECT *
FROM high_salary_employees
WHERE salary > 55000
ORDER BY salary DESC;
INSERT INTO high_salary_employees
(emp_id, name, dept_name, salary)
VALUES (105,'Kiran','IT',65000);
DROP VIEW IF EXISTS high_salary_employees;
