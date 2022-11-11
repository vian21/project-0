---
sidebar_position: 3
---
# Database Schema

## Schools:

contains data about schools using the app

- id: INT - auto
- name: VARCHAR(255)
- motto: VARCHAR(255) - words that describe the school's values
- type: INT - int because we can have multiple types of schools (elementary and secondary)
- email: VARCHAR(255) - (addresse e-mail de l'ecole qui sera sur le bulletin, dans le compte de l'ecole)
- logo: VARCHAR(255) - name of the image in the public upload folder
- website: VARCHAR(255) -
- country: VARCHAR(60)

## Grading_scale

contains the grading scale used by a school. eg 90 -> A+, 80 -> B. etc... Each school has its own grading scale.

- id: int - auto-increment
- school_id: int - auto-increment
- max: max and min are intervalles
- min:
- grade: VARCHAR(2) -(A+, A)
- gpa: float

## <del>Students</del>

Students table has been merged with users table since they are kinda the same. They both contain the same data and by just using one table, it will simplify authentication for us. Instead of checking in both tables or creating 2 different login pages for students and admins/ teachers. We will just create one that everyone wil use.

- id: int - (auto-increment)
- first_name: VARCHAR(255) - The student's first name
- last_name: VARCHAR(255) - The student's last name
- DOB: Date
- Gender: INT(2)
- email: VARCHAR(255) - Can be used to create a school account (ex:xxx@uottawa.ca)
- image: VARCHAR(255) -
- address: VARCHAR(255) -
- tel: int - (optional)
- uniqueID: TEXT(unique)- utiliser pour reinitialiser ton mot de passe
- password: TEXT
- status: INT(2)- (The status determines if the account is existing/active or not)

## Subject

Contains data about courses offered at a specific school.

- id:
- school_id: in which school the subject is taught
- teacher_id: id of the teacher teaching the subject
- room: VARCHAR(255)[null]. Where the class is taken.
- start: date
- end: date
- archived: BOOLEAN (Is the course finished or not)
- language: VARCHAR(255) - Course language
- subject_code: VARCHAR(5) - course code e.g FRA, SEG, ITI, MAT, PHY
- course_number: VARCHAR(5) - the code of the course e.g 1720, 1512, 4M, 4U..
- name: VARCHAR(255) - name of the course e.g Intro to computing, Calculus I, calculus II
- description: VARCHAR(255)

- **Note**: The combination of the subject code and course number will give the course code: MAT + 1720 = MAT 1720

## Users (Staff and students)

- id:
- first_name: VARCHAR(255) -
- last_name: VARCHAR(255) -
- DOB:
- gender: INT(1) (default = 0 == "Male")
- email: VARCHAR(255) -
- address: VARCHAR(255) - the address whre they live. eg. 15 Blair Road.
- nationality: VARCHAR(60) -
- password: TEXT
- account_type: INT(1)
  - root [0] - us, the app owners
  - admin [1]
  - teacher [2]
  - accountant [3]
  - student [4]
- status: BOOLEAN - If the account has been activated, and a password set.

## Subject_enrollment

Stores data about courses a student is taking and in what term/period.

- id: INT
- subject_id: INT
- student_id: INT
- academic_period_id: INT- in what term did the student take the course.
- finished: INT- (if the subject has already been done or not)

## School_transactions

This is for us. Contains the money paid by schools to use our product. The product for now is to be charged per month.

- id:
- school_id: INT
- Date: date of payment
- period : For how many months did the person pay for
- end_date: last day to pay, system is gonna close if not paid by this date.
  each time a school pays a new row will be added to extend the use period. The backend will calculate if the school has still access.

## Accounting

This stores data about in school finances: tuition fees, making invoices, ....

- id: INT
- student_id: INT
- amount: SIGNED FLOAT (va etre positif(chaque fois que la personne paie) et negatif(charge sur l'eleve))
- date: DATE(REQUIRED)
- due_date: DATE[NULL]
- <del>type</del>: (don't really need it since amount is a signed(+-) float)
- item: VARCHAR(255) - (What the person is paying for(books, minerval, frais administratif))
- academic_period_id

## Academic_periods

Term/ semester info

- id:
- start_date: date
- end_date: date
- type: INT(1)[REQUIRED] (indicates if it's a term or semester)
- school_id

## Academic_enrollment

This determines if a student is enrolled in a specif term. For instance, you can be enrolled in the Fall term and not study during the winter term.

- id:
- student_id:
- academic_period_id:
- grade: INT. what grade the student is in (11th grade, 12th grade, etc.). I think it needs to be REQUIRED almost every school has graded system; even in universities there is 1st year, 2nd until you finish. SO it is REQUIRED.

Note: don't need a school_id here because academic_period already has one. An admin will just query this table using the academic_period_id related to his school.

## Marks

- id:
- subject_id:
- student_id:
- mark: FLOAT(REQUIRED)
- academic_period_id: This will enable us to sort marks according to academic period. For example, fetch all students data in a term or sum all his point to get the average
- assessments_id:

## Assessments

This stores data about the tests, quizzes and exams made

- id:
- subject_id:
- type(INT)[REQUIRED]: [quiz, test, exam]

## Discipline

Points de discipline

- id:
- student_id:
- academic_period_id:
- points: INT
- infraction: TEXT
- invigilator: user_id -> Who deducted the student his marks.

## Grade

Contains streams(les classes i.e 7A, 7B, scientifique A ou B)

- id
- school_id
- stream_name
