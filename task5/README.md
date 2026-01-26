CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  department VARCHAR(20),
  marks INT
);
INSERT INTO students VALUES
(1,'Ravi','CSE',85),
(2,'Sita','ECE',92),
(3,'Aman','CSE',85),
(4,'Neha','EEE',78),
(5,'Kiran','CSE',95);
SELECT*FROM students
ORDER BY marks ASC;
SELECT*FROM students
ORDER BY marks DESC;
SELECT*FROM students
ORDER BY marks DESC,nameASC;
SELECT*FROM students
ORDER BY marks DESC
LIMIT 5;
SELECT*FROM students
WHERE department='CSE'
ORDER BY marks DESC;
SELECT*FROM students 
ORDER BY marks DESC
LIMIT 5 OFFSET 0;
SELECT*FROM students
ORDER BY marks DESC
LIMIT 5 OFFSET 5;
SELECT name,marks
FROM students
ORDER BY marks DESC 
LIMIT 10;
SELECT name,department,marks
FROM students
ORDER BY department,marks DESC;
ORDER BY marks DESC,name ASC;
ORDER BY marks DESC;
LIMIT 0;
