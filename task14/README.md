CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    salary DECIMAL(10,2)
);
DELIMITER //

CREATE PROCEDURE AddEmployee(
    IN emp_name VARCHAR(50),
    IN emp_salary DECIMAL(10,2)
)
BEGIN
    INSERT INTO employees(name, salary)
    VALUES(emp_name, emp_salary);
END //

DELIMITER ;
CALL AddEmployee('Ramesh', 40000);
CALL AddEmployee('Anita', 50000);

SELECT * FROM employees;
DELIMITER //

CREATE FUNCTION CalculateTax(salary DECIMAL(10,2))
RETURNS DECIMAL(10,2)
DETERMINISTIC
BEGIN
    RETURN salary * 0.10; -- 10% tax
END //

DELIMITER ;
SELECT name, salary, CalculateTax(salary) AS tax
FROM employees;
DELIMITER //

CREATE PROCEDURE SafeAddEmployee(
    IN emp_name VARCHAR(50),
    IN emp_salary DECIMAL(10,2)
)
BEGIN
    IF emp_salary < 0 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Salary cannot be negative';
    ELSE
        INSERT INTO employees(name, salary)
        VALUES(emp_name, emp_salary);
    END IF;
END //

DELIMITER ;
CALL SafeAddEmployee('Kiran', -2000);
SET autocommit = 0;
