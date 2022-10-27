# Database Schema

## Schools:

- id: int - auto
- name:
- motto: words that describe the school's values
- type: int because we can have multiple types of schools (elementary and secondary)
- email: text (addresse e-mail de l'ecole qui sera sur le bulletin, dans le compte de l'ecole)
- logo:
- website:

## Grading

- id: int - auto-increment
- school_id: int - auto-increment
- max: max and min are intervalles
- min:
- grade: string --(A+, A)
- gpa: int or float

## Students

- id: int - (auto-increment) (because it always has to be different)
- first_name: The student's first name
- last_name: The student's last name
- DOB: int
- Gender:
- email: Can be used to create a school account (ex:xxx@uottawa.ca)
- image:
- adress:
- tel: int - (optional)
- uniqueID: string(unique) utiliser pour reinitialiser ton mot de passe
- password:
- status: bool (The status determines if the account is existing/active or not)

## Subject_info

- id:
- teacher_id:
- room_id: int
- Subject_id:
- start: date
- end: date
- archived: bool (Is the course fnished or not)
- language: The different languages the school's gonna be offered in

## Users(employee at the school)

- id:
- first_name:
- last_name:
- DOB:
- email:
- adress:
- password:
- account_type: int
- status: bool (If the user's email is still active/existing or not)

## Subject_enrollment

- id:
- subject_id:
- finished: bool (if the suject has already been done or not)

## School_transactions

- id:
- school_id:
- Date: date of payment
- period : For how many months did the person pay for
- end_date: last day the payment system is gonna close

## Accounting

- id:
- student_id:
- amount: float (va etre positif(chaque fois que la personne paie) et negatif(charge sur l'eleve))
- date:
- due_date:
- type: (don't really need it)
- item: string (What the person is paying for(books, minerval, frais administratif))

## Academic_periods

- id:
- start_date: date
- end_date: date
- type: bool (indicates if it's a term or semester)

## Academic enrollement

The student is only gonna see their grade for the time period he was enrolled in (so if a student wants to check their grades they won't see anything for the summer)

- id:
- student_id:
- subject_id:
- academic_period_id:
- grade: int(optional) what grade the student is in (11th grade, 12th grade, etc.)

## Marks

- id:
- subject_id:
- student_id:
- mark: float
- academic_period_id:
- assessments_id:

## Assessments

- id:
- assessment_id:
- subject_id:
- type:

## Discipline

- id:
- student_id:
- academmic_period_id:
- points:
- infraction:
- vigilator: user_id
