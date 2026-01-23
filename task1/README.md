CREATE TABLE students(
id INT,
name VARCHAR(50),
email VARCHAR(50),
age INT
);
INSERT INTO students VALUES
(1, 'Ravi', 'ravi@gmail.com', 20),
(2, 'Anjali', 'anjali@gmail.com', 22),
(3, 'Suresh', 'suresh@gmail.com', 21),
(4, 'Priya', 'priya@gmail.com', 19),
(5, 'Amit', 'amit@gmail.com', 23);
SELECT*FROM students;
SELECT name,email FROM students;
SELECT*FROM students WHERE age>20;
