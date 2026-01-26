CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    marks INT,
    department VARCHAR(20)
);

INSERT INTO students VALUES
(1, 'Ravi', 85, 'CSE'),
(2, 'Sita', 92, 'ECE'),
(3, 'Arjun', 78, 'CSE'),
(4, 'Meena', 92, 'CSE'),
(5, 'Kiran', 65, 'EEE'); 
SELECT*FROM students
ORDER BY marks ASC;
SELECT*FROM students
ORDER BY marks DESC,name ASC;
SELECT*FROM students
ORDER BY marks DESC
LIMIT 3;
SELECT*FROM students
WHERE department='CSE'
ORDER BY marks DESC;
SELECT*FROM students
ORDER BY id
LIMIT 2 OFFSET 0;
SELECT*FROM students
ORDER BY idLIMIT 2 OFFSET 2;
SELECT name,marks
FROM students
ORDER BYmarks DESCLIMIT 5;
SELECT*FROM students
ORDER BY marks DESC
LIMIT 0;
