CREATE TABLE customers (
    customer_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    city VARCHAR(50)
);

CREATE TABLE products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(50),
    price INT
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    product_id INT,
    quantity INT,
    order_date DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);
INSERT INTO customers(name, city) VALUES
('Ravi','Hyderabad'),
('Sita','Chennai'),
('Arjun','Bangalore'),
('Meena','Delhi');

INSERT INTO products(product_name, price) VALUES
('Laptop',60000),
('Mobile',20000),
('Headphones',2000),
('Tablet',30000);

INSERT INTO orders(customer_id, product_id, quantity, order_date) VALUES
(1,1,1,'2024-01-10'),
(2,2,2,'2024-01-15'),
(1,3,3,'2024-02-05'),
(3,1,1,'2024-02-20'),
(4,4,2,'2024-03-12');
SELECT p.product_name,
SUM(o.quantity) AS total_sold
FROM orders o
JOIN products p
ON o.product_id = p.product_id
GROUP BY p.product_name
ORDER BY total_sold DESC;
SELECT DATE_FORMAT(order_date, '%Y-%m') AS month,
SUM(quantity * price) AS revenue
FROM orders o
JOIN products p
ON o.product_id = p.product_id
GROUP BY month
ORDER BY month;
SELECT c.name
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
WHERE o.order_id IS NULL;
SELECT c.name,
SUM(p.price * o.quantity) AS total_spent
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id
JOIN products p
ON o.product_id = p.product_id
GROUP BY c.name
HAVING total_spent > 50000;
CREATE INDEX idx_customer ON orders(customer_id);
CREATE INDEX idx_product ON orders(product_id);
