CREATE TABLE department (
    deptId INT PRIMARY KEY,
    name VARCHAR(50),
    hod VARCHAR(10),
    phone VARCHAR(20)
);

CREATE TABLE professor (
    empId VARCHAR(10) PRIMARY KEY,
    name VARCHAR(50),
    sex VARCHAR(10),
    startYear INT,
    deptNo INT,
    phone VARCHAR(20)
);

CREATE TABLE student (
    rollNo INT PRIMARY KEY,
    name VARCHAR(50),
    degree VARCHAR(10),
    year INT,
    sex VARCHAR(10),
    deptNo INT,
    advisor VARCHAR(10)
);

CREATE TABLE course (
    courseId VARCHAR(10) PRIMARY KEY,
    cname VARCHAR(50),
    credits INT,
    deptNo INT
);

CREATE TABLE enrollment (
    rollNo INT,
    courseId VARCHAR(10),
    sem INT,
    year INT,
    grade VARCHAR(5)
);

INSERT INTO department VALUES
(1, 'Computer Sc & Engg.', 'CS001', '033-2567-0001'),
(2, 'Electronics & Comm.', 'EC001', '033-2567-0002');

INSERT INTO professor VALUES
('CS001', 'Biswanath Pal', 'Male', 1992, 1, '9830011111'),
('CS005', 'Bivas Paramanik', 'Male', 1998, 1, '9830022222'),
('CS006', 'Maitreyi Ray', 'Female', 2005, 1, '9830033333'),
('EC001', 'Swapan Roy', 'Male', 1989, 2, '9830044444'),
('EC004', 'Tanushree Ghosh', 'Female', 1999, 2, '9830055555');

INSERT INTO student VALUES 
(1, 'Parag Roy', 'B.E', 3, 'Male', 1, 'CS005'),
(2, 'Rituparna Kashyap', 'B.E', 3, 'Male', 1, 'CS005'),
(3, 'Neha', 'B.E', 3, 'Female', 1, 'CS005'),
(4, 'Raman', 'B.E', 4, 'Male', 2, 'EC004'),
(5, 'Surja Sanyal', 'M.E', 2, 'Male', 1, 'CS005'),
(6, 'Susahant Satyam', 'M.E', 1, 'Male', 2, 'EC004'),
(7, 'Kamalika Samanta', 'M.E', 1, 'Female', 1, 'CS005'),
(8, 'Aparajita', 'B.E', 2, 'Female', 2, 'EC004'),
(9, 'Sirajul Islam', 'M.E', 2, 'Male', 2, 'EC004'),
(10, 'Manisha Chaudhury', 'M.E', 2, 'Female', 2, 'EC004');

INSERT INTO course VALUES
('CS101', 'Data Structures', 4, 1),
('CS201', 'Database Systems', 6, 1),
('EC101', 'Digital Electronics', 4, 2);

INSERT INTO enrollment VALUES
(1, 'CS101', 3, 2026, 'A++'),
(2, 'CS101', 3, 2026, 'B'),
(3, 'CS201', 3, 2026, 'C'),
(4, 'EC101', 4, 2026, 'A'),
(6, 'EC101', 1, 2026, 'B'),
(7, 'CS201', 1, 2026, 'A++');
  SELECT s.name,s.rollNo
  FROM student s ,enrollment e,department d
  WHERE s.rollNo=e.rollNo
  AND s.deptId=d.deptId
  AND e.sem=2
  AND s.degree='M.E'
  
