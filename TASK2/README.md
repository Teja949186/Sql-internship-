DROP TABLE IF EXISTS students;
CREATE TABLE students(
id INT PRIMARY KEY,
name VARCHAR(50)NOT NULL,
email VARCHAR(100)UNIQUE NOT NULL,
dob DATE,
age INT
);
INSERT INTO students VALUES
(1, 'Ravi', 'ravi@gmail.com', '2003-05-10', 20);

INSERT INTO students VALUES
(2, 'Anjali', 'anjali@gmail.com', '2002-04-15', 22);
INSERT INTO students VALUES
(3,'chinni','chinni@gmail.com','2005-06-20',19);
ALTER TABLE students ADD phone VARCHAR(10);
ALTER TABLE students RENAME COLUMN phone TO mobile_number;
ALTER TABLE students DROP COLUMN age;
SELECT*FROM students;
