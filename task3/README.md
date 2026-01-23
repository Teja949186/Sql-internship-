CREATE TABLE students(
id INT,
name VARCHAR(50),
age INT,
email VARCHAR(100)
);
INSERT INTO students VALUES
(1, 'Ravi', 20, 'ravi@gmail.com'),
(2, 'Keerthi', 22, 'keerthi@yahoo.com'),
(3, 'Anu', 19, NULL),
(4, 'Rahul', 21, 'rahul@gmail.com'),
(5, 'Kiran', 22, 'kiran@gmail.com');
SELECT*FROM students WHERE age=22;
SELECT*FROM students WHERE age=22 AND name='Keerthi';
SELECT*FROM students WHERE age=20 OR age=21;
SELECT*FROM students WHERE name LIKE 'R%';
SELECT*FROM students WHERE name LIKE '_a%';
SELECT*FROM students WHERE age IN(20,22);
SELECT*FROM students WHERE age BETWEEN 20 AND 22;
SELECT*FROM students WHERE email IS NULL;
SELECT name,age FROM students WHERE age>20 ORDER BY age;
SELECT name AS student_name,age AS student_age FROM students;
SELECT*FROM students WHERE email LIKE '%gmail.com';
