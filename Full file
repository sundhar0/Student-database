CREATE DATABASE StudentDB;
USE StudentDB;

CREATE TABLE students (
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    date_of_birth DATE,
    email VARCHAR(100) UNIQUE,
    phone_number VARCHAR(15),
    enrollment_date DATE DEFAULT CURRENT_DATE
);

CREATE TABLE courses (
    course_id INT PRIMARY KEY AUTO_INCREMENT,
    course_name VARCHAR(100),
    course_code VARCHAR(10) UNIQUE,
    credits INT
);

CREATE TABLE enrollments (
    enrollment_id INT PRIMARY KEY AUTO_INCREMENT,
    student_id INT,
    course_id INT,
    enrollment_date DATE DEFAULT CURRENT_DATE,
    grade VARCHAR(2),
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);

-- Insert into students
INSERT INTO students (first_name, last_name, date_of_birth, email, phone_number)
VALUES 
('John', 'Doe', '2000-01-15', 'john.doe@example.com', '555-1234'),
('Jane', 'Smith', '2001-02-20', 'jane.smith@example.com', '555-5678');

-- Insert into courses
INSERT INTO courses (course_name, course_code, credits)
VALUES 
('Introduction to Computer Science', 'CS101', 4),
('Calculus I', 'MATH101', 3);

-- Insert into enrollments
INSERT INTO enrollments (student_id, course_id, grade)
VALUES 
(1, 1, 'A'),
(2, 2, 'B');

-- Get all students
SELECT * FROM students;

-- Get all courses a student is enrolled in
SELECT students.first_name, students.last_name, courses.course_name, enrollments.grade
FROM enrollments
JOIN students ON enrollments.student_id = students.student_id
JOIN courses ON enrollments.course_id = courses.course_id
WHERE students.student_id = 1;

