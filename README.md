# Student-course-management-system
-- What the project does:
-- Stores detailed student records, including names, emails, and birth dates.
-- Maintains a catalog of courses offered by the institution.
-- Assigns instructors to specific courses.
-- Keeps track of which students are enrolled in which courses.
-- Records the grades or outcomes for each course enrollment.
-- sql code 
-- Create Students table
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    full_name VARCHAR(100),
    email VARCHAR(100),
    date_of_birth DATE
);

-- Create Instructors table
CREATE TABLE Instructors (
    instructor_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(50)
);

-- Create Courses table
CREATE TABLE Courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100),
    instructor_id INT,
    FOREIGN KEY (instructor_id) REFERENCES Instructors(instructor_id)
);

-- Create Enrollments table
CREATE TABLE Enrollments (
    enrollment_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    grade VARCHAR(2),
    FOREIGN KEY (student_id) REFERENCES Students(student_id),
    FOREIGN KEY (course_id) REFERENCES Courses(course_id)
);
