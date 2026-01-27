CREATE TABLE departments (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(50)
);

CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(50),
    dept_id INT,
    FOREIGN KEY (dept_id) REFERENCES departments(dept_id)
);
INSERT INTO departments VALUES 
(1, 'CSE'), (2, 'ECE'), (3, 'MECH');

INSERT INTO employees VALUES 
(101, 'Ravi', 1),
(102, 'Sita', 2),
(103, 'Arjun', 1),
(104, 'Meena', NULL); -- Employee without a department
SELECT e.emp_name, d.dept_name
FROM employees AS e
INNER JOIN departments AS d
ON e.dept_id = d.dept_id;
SELECT e.emp_name, d.dept_name
FROM employees AS e
LEFT JOIN departments AS d
ON e.dept_id = d.dept_id;
SELECT e.emp_name, d.dept_name
FROM employees AS e
RIGHT JOIN departments AS d
ON e.dept_id = d.dept_id;
SELECT e.emp_name, d.dept_name
FROM employees AS e
LEFT JOIN departments AS d
ON e.dept_id = d.dept_id

UNION

SELECT e.emp_name, d.dept_name
FROM employees AS e
RIGHT JOIN departments AS d
ON e.dept_id = d.dept_id;
