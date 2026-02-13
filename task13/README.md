CREATE TABLE products (
    product_id INT PRIMARY KEY,
    price INT NOT NULL CHECK (price > 0),
    product_code VARCHAR(20) UNIQUE NOT NULL
);
CREATE TABLE accounts (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    balance INT
);

INSERT INTO accounts VALUES
(1, 'Ravi', 10000),
(2, 'Sita', 5000);
START TRANSACTION;

UPDATE accounts
SET balance = balance - 2000
WHERE id = 1;

UPDATE accounts
SET balance = balance + 2000
WHERE id = 2;

COMMIT;
START TRANSACTION;

UPDATE accounts
SET balance = balance - 7000
WHERE id = 1;

-- Suppose error occurs here
ROLLBACK;
SELECT @@transaction_isolation;
SET SESSION TRANSACTION ISOLATION LEVEL READ COMMITTED;
START TRANSACTION;

SELECT * FROM accounts
WHERE id = 1
FOR UPDATE;

UPDATE accounts
SET balance = balance - 1000
WHERE id = 1;

COMMIT;
SET SESSION TRANSACTION ISOLATION LEVEL READ COMMITTED;
SELECT @@autocommit;
