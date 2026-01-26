CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  department VARCHAR(20),
  marks INT
);
INSERT INTO students VALUES
(1, 'Ravi', 'CSE', 85),
(2, 'Sita', 'ECE', 92),
(3, 'Aman', 'CSE', 85),
(4, 'Neha', 'EEE', 78),
(5, 'Kiran', 'CSE', 95),
(6, 'Anu', 'ECE', 92);
SELECT * FROM students
ORDER BY marks;
SELECT * FROM students
ORDER BY marks DESC;
SELECT * FROM students
ORDER BY marks DESC, name ASC;
SELECT * FROM students
ORDER BY marks DESC
LIMIT 3;
SELECT * FROM students
ORDER BY marks DESC
LIMIT 3;
SELECT * FROM students
WHERE department = 'CSE'
ORDER BY marks DESC;
SELECT * FROM students
ORDER BY marks DESC
LIMIT 2 OFFSET 0;
SELECT * FROM students
ORDER BY marks DESC
LIMIT 2 OFFSET 2;
CREATE INDEX idx_marks ON students(marks);
SELECT name, marks
FROM students
ORDER BY marks DESC
LIMIT 5;
SELECT * FROM students
ORDER BY marks DESC, name ASC;
INSERT INTO students VALUES (7, 'Rahul', 'CSE', NULL);
SELECT * FROM students
ORDER BY marks DESC;
SELECT * FROM students
LIMIT 0;
