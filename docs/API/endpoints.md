# API endpoints

The following document outlines the following:

- The guidelines for naming our API endpoints
- The request methods that should be used depending on the query
- Description of every every endpoint of the app i.e method, data that needs to be sent, and data returned by the endpoints

## Naming

Every Api endpoint must be named in the plural if it is used to access one entity in the database. For example `https://app.com/users/1/` endpoint is used to fetch data about a specific user.

### Request.body :

This is used when sending data from the user(front-end) to the backend. For example, if you want to update a student's name. You send a PATCH request to the server with a name property as the database field you want to update and the its new value.

```json
{
  //field: value,
  "name": "Root"
}
```

### **Response**: JSON

Every endpoint should return data to the user to indicate if the query succeeded or not. It should send HTTP status code and a JSON object with either a error property with a message or a succes property with a success message or the data requested.

If the endpoint is for retrieving data, it should send back a success property with just a `success: true `. If it

```json
{
  "success": true
}
```

or if the query failed

```json
{
  "error": "Failed to update name"
}
```

---

## Users

| Method    | Endpoint       | req.body                                                                                                                                                               | Auth level  | Description                                        |
| --------- | -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- | -------------------------------------------------- |
| `GET`     | /api/users/:id |                                                                                                                                                                        | All user    | Fetch data about a specific user(student or staff) |
| `POST `   | /users/        | Required: <ul><li>first_name</li><li>last_name</li><li>DOB</li><li>gender</li><li>account_type</li></ul>Optional: <ul><li>tel</li><li>email</li><li>address</li> </ul> | Root, Admin | Creates a new user/student account                 |
| `PATCH`   | /api/users/:id | field : newValue                                                                                                                                                       | Root, Admin | Used to update one user field/data in the database |
| `DELETE ` | /api/users/:id |                                                                                                                                                                        | Root, Admin | Delete a user given his ID                         |

---

## Schools

| Method   | Endpoint         | Req body                                                                                                 | Auth level | Description                                          |
| -------- | ---------------- | -------------------------------------------------------------------------------------------------------- | ---------- | ---------------------------------------------------- |
| `GET`    | /api/schools/    |                                                                                                          | All users  | Fetch data about a specific school                   |
| `POST`   | /schools/        | Required: <ul><li>name</li><li>email</li></ul> Optional<ul><li>type</li><li>Logo</li><li>motto</li></ul> | Root       | create a new school                                  |
| `PATCH`  | /api/schools/:id | field:newvalue                                                                                           | Root       | Used to update one school field/data in the database |
| `DELETE` | /api/schools/:id |                                                                                                          | Root       | Delete a school by using his ID                      |

## Grading scale

| Method   | Endpoint         | Req body                                                             | Auth level | Description                             |
| -------- | ---------------- | -------------------------------------------------------------------- | ---------- | --------------------------------------- |
| `GET`    | /api/grading/    |                                                                      | All users  | contain grade of a specific school      |
| `POST`   | /grading/        | Required:<ul><li>max</li><li>min</li><li>grade</li><li>gpa</li></ul> | Root,Admin | enter the max and min grade of a school |
| `PATCH`  | /api/grading/:id | field:newvalue                                                       | Root,Admin | update a school grade                   |
| `DELETE` | /api/grading/:id |                                                                      | Root,Admin | Delete a school grading                 |

##

## subject_info

| Method | Endpoint              | Request.body                                                                              | Auth level  | Description                      |
| ------ | --------------------- | ----------------------------------------------------------------------------------------- | ----------- | -------------------------------- |
| `GET`    | /api/subject_info/:id |                                                                                           | all users   | Give info about specific subject |
| `POST`   | /api/subject_info/    | language, start_date, end_date, name, description, course_number, subject_code, school_id | admin, root | create a new subject             |
| `PATCH`  | /api/subject_info/:id | field:new_value                                                                           | admin, root | update a subject                 |
| `DELETE` | /api/subject_info/:id |                                                                                           | root, admin | remove a subject                 |

---

## subject_enrollment

| Method    | Endpoint                    | Req body                                                                                                                  | Auth level  | Description                                                   |
| --------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------- | ----------- | ------------------------------------------------------------- |
| `GET`     | /api/subject_enrollment/:id |                                                                                                                           | Root, Admin | Fetch data about the subject a student is taking              |
| `POST `   | /subject_enrollment/        | Required: <ul><li>subject_id</li><li>student_id</li><li>academic_period_id</li></ul> Optional: <ul><li>finished</li></ul> | Root, Admin | Assign a new subject to a student                             |
| `PATCH`   | /api/subject_enrollment/:id | field : newValue                                                                                                          | Root, Admin | Used to update a student's subject field/data in the database |
| `DELETE ` | /api/subject_enrollment/:id |                                                                                                                           | Root, Admin | Delete a subject given its ID                                 |

---

## school_transactions

| Method    | Endpoint                     | Req Body                                                                           | Auth level  | Description                                                             |
| --------- | ---------------------------- | ---------------------------------------------------------------------------------- | ----------- | ----------------------------------------------------------------------- |
| `GET`     | /api/school_transactions/:id |                                                                                    | Root, Admin | Fetch data about the transactions made by the school to us              |
| `POST `   | /school_transactions/        | Required: <ul><li>school_id</li><li>Date</li><li>period</li><li>end_date</li></ul> | Root, Admin | Create a school and its transactions profile                            |
| `PATCH`   | /api/school_transactions/:id | field : newValue                                                                   | Root, Admin | Used to update the total transactions school field/data in the database |
| `DELETE ` | /api/school_transactions/:id |                                                                                    | Root, Admin | Delete the school transactions given his ID                             |

---

## accounting

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## academic_periods

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## academic_enrollment

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## marks

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## assessements

| Method | Endpoint             | Request_body    | Auth level  | Description                                      |
| ------ | -------------------- | --------------- | ----------- | ------------------------------------------------ |
| `GET`    | /api/assessments/:id |                 | all user    | Give info about assessment which will take place |
| `POST`   | /api/assessments/    | type            | root, admin | create a new assessment                          |
| `PATCH`  | /api/assessments/:id | field:new_value | root, admin | update an assessment                             |
| `DELETE` | /api/assessments/:id |                 | root, admin | delete an assessment                             |

## discipline

| Method   | Endpoint            | Req body                                                                   | Auth level | Description                                   |
| -------- | ------------------- | -------------------------------------------------------------------------- | ---------- | --------------------------------------------- |
| `GET`    | /api/discipline/    |                                                                            | All users  | fetch data about student discipline           |
| `POST`   | /api/discipline/    | Required:<ul><li>points</li><li>invigilators</li><li>infractions</li></ul> | Root,Admin | add how many points to withraw from a student |
| `PATCH`  | /api/discipline/:id | field:newvalue                                                             | Root,Admin | update a student discipline                   |
| `DELETE` | /api/discipline/:id |                                                                            | Root,Admin | delete a student dscipline                    |

##

## streams

| Method    | Endpoint          | Req Body                                                  | Auth level  | Description                                                  |
| --------- | ----------------- | --------------------------------------------------------- | ----------- | ------------------------------------------------------------ |
| `GET`     | /api/streams/:id  |                                                           | Root, Admin | Fetch data about the grades or academic levels of the school |
| `POST `   | /streams/         | Required: <ul><li>school_id</li><li>stream_name</li></ul> | Root, Admin | Creates an academic level's profile                          |
| `PATCH`   | /api/streams/:id  | field : newValue                                          | Root, Admin | Used to update an academic level field/data in the database  |
| `DELETE ` | /api/streamss/:id |                                                           | Root, Admin | Delete the academic level given its ID                       |
