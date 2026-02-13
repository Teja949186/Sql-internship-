CREATE TABLE employees (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    email VARCHAR(100) UNIQUE,
    age INT CHECK (age BETWEEN 18 AND 60),
    salary INT CHECK (salary >= 20000),
    join_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
INSERT INTO employees (email, age, salary)
VALUES ('ravi@gmail.com', 25, 30000);
SELECT * FROM employees;
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    price INT NOT NULL CHECK (price > 0),
    product_code VARCHAR(20) UNIQUE NOT NULL
);
