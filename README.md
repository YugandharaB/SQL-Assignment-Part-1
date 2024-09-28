# SQL-Assignment-Part-1
SQL Assignments where I have performed simple SQL queries 

1) SELECT SELECT AVG(grade) AS average_grade
FROM Enrollments
JOIN Students ON Enrollments.student_id = Students.student_id;
2) SELECT Students.name, Courses.course_name
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;

3) SELECT grade_level, COUNT(*) AS number_of_students
FROM Students
GROUP BY grade_level;

4) SELECT Courses.course_name, MAX(Enrollments.grade) AS max_grade
FROM Courses
JOIN Enrollments ON Courses.course_id = Enrollments.course_id
GROUP BY Courses.course_name;

5) SELECT AVG(Enrollments.grade) AS average_grade
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
WHERE Students.grade_level = 3;

6) SELECT Students.name, Courses.course_name, Courses.credits
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;
 
7) SELECT Courses.course_name
FROM Courses
JOIN Enrollments ON Courses.course_id = Enrollments.course_id
GROUP BY Courses.course_name
HAVING AVG(Enrollments.grade) > 3.0;

8) SELECT Students.student_id, Students.name
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
WHERE Enrollments.grade!= 4.0
GROUP BY Students.student_id;

9) WITH AvgGrade AS (
  SELECT AVG(grade) AS avg_grade
  FROM Enrollments
)
SELECT Students.name
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
GROUP BY Students.student_id
HAVING AVG(Enrollments.grade) > (SELECT avg_grade FROM AvgGrade);

10) SELECT Students.name, 
       COUNT(*) AS total_courses, 
       AVG(Enrollments.grade) AS average_grade
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
GROUP BY Students.student_id;  

