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
| `POST`   | /api/grading/    | Required:<ul><li>max</li><li>min</li><li>grade</li><li>gpa</li></ul> | Root,Admin | enter the max and min grade of a school |
| `PATCH`  | /api/grading/:id | field:newvalue                                                       | Root,Admin | update a school grade                   |
| `DELETE` | /api/grading/:id |                                                                      | Root,Admin | Delete a school grading                 |

##

## subject_info

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## subject_enrollment

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## school_transactions

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

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

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## discipline

| Method   | Endpoint            | Req body                                                              | Auth level | Description                                   |
| -------- | ------------------- | --------------------------------------------------------------------- | ---------- | --------------------------------------------- |
| `GET`    | /api/discipline/    |                                                                       | All users  | fetch data about student discipline           |
| `POST`   | /api/discipline/    | Required:<ul><li>points</li><li>invigilators</li><li>infractions</li> | Root,Admin | add how many points to withraw from a student |
| `PATCH`  | /api/discipline/:id | field:newvalue                                                        | Root,Admin | update a student discipline                   |
| `DELETE` | /api/discipline/:id |                                                                       | Root,Admin | delete a student dscipline                    |

##

## streams

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |
