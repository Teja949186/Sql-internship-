CREATE TABLE employees (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    department VARCHAR(50),
    salary INT
);
INSERT INTO employees (name, department, salary)
SELECT 
    CONCAT('Employee', FLOOR(RAND()*10000)),
    ELT(FLOOR(1 + RAND()*3), 'IT','HR','Finance'),
    FLOOR(30000 + RAND()*40000)
FROM information_schema.tables
LIMIT 5000;
SELECT * 
FROM employees
WHERE department = 'IT';
CREATE INDEX idx_department
ON employees(department);
SELECT * 
FROM employees
WHERE department = 'IT';EXPLAIN
SELECT * 
FROM employees
WHERE department = 'IT';
