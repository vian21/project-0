# Database Schema

## Schools:
contains data about schools using the app
- id: int - auto
- name:
- motto: words that describe the school's values
- type: int because we can have multiple types of schools (elementary and secondary)
- email: text (addresse e-mail de l'ecole qui sera sur le bulletin, dans le compte de l'ecole)
- logo:
- website:

## Grading
contains the grading scale used by a school. eg 90 -> A+, 80 -> B. etc... Each school has its own grading scale.
- id: int - auto-increment
- school_id: int - auto-increment
- max: max and min are intervalles
- min:
- grade: string --(A+, A)
- gpa: int or float

## <del>Students</del>
Students table has been merged with users table since they are kinda the same. They both contain the same data and by just using one table, it will simplify authentication for us. Instead of checking in both tables or creating 2 different login pages for students and admins/ teachers. We will just create one that everyone wil use.
- id: int - (auto-increment) 
- first_name: The student's first name
- last_name: The student's last name
- DOB: Date
- Gender: INT(2)
- email: Can be used to create a school account (ex:xxx@uottawa.ca)
- image:
- address:
- tel: int - (optional)
- uniqueID: string(unique) utiliser pour reinitialiser ton mot de passe
- password:
- status: bool (The status determines if the account is existing/active or not)

## Subject_info
Contains data about courses offered at a specific school.

- id:
- school_id: in which school the subject is taught
- teacher_id: id of the teacher teaching the subject
- room_id: TEXT(255) -> null. Where the class is taken.
- start: date
- end: date
- archived: bool (Is the course finished or not)
- language: TEXT(255) The different languages the school offers

## Users (Staff and students)

- id:
- first_name:
- last_name:
- DOB:
- email:
- address:
- password:
- account_type: int
- status: bool (If the user's email is still active/existing or not)

## Subject_enrollment
Stores data about courses a student is taking and in what term/period.

- id:
- subject_id:
- student_id
- academic_period_id: in what term did the student take the course.
- finished: bool (if the subject has already been done or not)

## School_transactions
This is for us. Contains the money paid by schools to use our product. The product for now is to be charged per month.
- id:
- school_id:
- Date: date of payment
- period : For how many months did the person pay for
- end_date: last day the payment system is gonna close
each time a school pays a new row will be added to extend the use period. The backend will calculate if the school has still access.

## Accounting
This stores data about in school finances: tuition fees, making invoices, ....
- id:
- student_id:
- amount: SIGNED FLOAT (va etre positif(chaque fois que la personne paie) et negatif(charge sur l'eleve))
- date:
- due_date:
- <del>type</del>: (don't really need it since amount is a signed(+-) float)
- item: string (What the person is paying for(books, minerval, frais administratif))
- academic_period_id

## Academic_periods
Term/ semester info
- id:
- start_date: date
- end_date: date
- type: bool (indicates if it's a term or semester)

## Academic_enrolment

This determines if a student is enrolled in a specif term. For instance, you can be enrolled in the Fall term and not study during the winter term. 

- id:
- student_id:
- academic_period_id:
- grade: INT. what grade the student is in (11th grade, 12th grade, etc.). I think it needs to be REQUIRED almost every school has graded system; even in universities there is 1st year, 2nd until you finish. SO it is REQUIRED.

## Marks

- id:
- subject_id:
- student_id:
- mark: float
- academic_period_id: This will enable us to sort marks according to academic period. For example, fetch all students data in a term or sum all his point to get the average
- assessments_id: 

## Assessments
This stores data about the tests, quizzes and exams made
- id:
- subject_id:
- type(INT): [quiz, test, exam]

## Discipline
Points de discipline
- id:
- student_id:
- academic_period_id:
- points: INT
- infraction: TEXT
- invigilator: user_id -> Who deducted the student his marks.

## streams/ classes
Contains streams(les classes i.e 7A, 7B, scientifique A ou B)
- id
- school_id
- stream_name