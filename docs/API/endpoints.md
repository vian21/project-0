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

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## Grading

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## subject_info

| Method | Endpoint             | Request.body                                                                              | Auth level  | Description                      |
| ------ | -------------------- | ----------------------------------------------------------------------------------------- | ----------- | -------------------------------- |
| GET    | /api/subject_info/:id |                                                                                           | all users   | Give info about specific subject |
| POST   | /api/subject_info/    | language, start_date, end_date, name, description, course_number, subject_code, school_id | admin, root | create a new subject             |
| PATCH  | /api/subject_info/:id | field:new_value                                                                           | admin, root | update a subject                 |
| DELETE | /api/subject_info/:id |                                                                                           | root, admin | remove a subject                 |

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

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |

---

## streams

| Method | Endpoint | Auth level | Description |
| ------ | -------- | ---------- | ----------- |
