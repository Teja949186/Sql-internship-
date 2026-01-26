CREATE TABLE students (
  id INT PRIMARY KEY,
  name VARCHAR(50),
  class VARCHAR(10),
  marks INT
);
INSERT INTO students VALUES
(1, 'Ravi', '10th', 85),
(2, 'Sita', '10th', 92),
(3, 'Amit', '9th', 78),
(4, 'Priya', '9th', 92),
(5, 'Kiran', '10th', 65),
(6, 'Anu', '9th', NULL);
SELECT*FROM students
ORDER BY marks ASC;
SELECT*FROM students
ORDER BY marks DESC;
SELECT*FROM students 
ORDER BY class ASC,marks DESC;
SELECT*FROM students
ORDER BY marks DESC
LIMIT 5;
SELECT*FROM students
WHERE class ='10th'
ORDER BY marks DESC;
SELECT*FROM students
ORDER BY id 
LIMIT 5 OFFSET 5;
CREATE INDEX idx_marks ON students(marks);
SELECT name,marks
FROM students
ORDER BY marks DESC
LIMIT 10;
SELECT name,marks
FROM students
ORDER BY marks DESC,name ASC
SELECT*FROM students
ORDER BY marks IS NULL,marks DESC
SELECT*FROM students
ORDER BY marks DESC,id ASC;
