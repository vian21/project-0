# API endpoints

The following document outlines the following:
- The guidelines for naming our API endpoints
- The request methods that should be used depending on the query
- Description of every every endpoint of the app i.e method, data that needs to be sent, and data returned by the endpoints

## Naming
Every Api endpoint must be named in the plural if it is used to access one entity in the database. For example ```https://app.com/users/1/``` endpoint is used to fetch data about a specific user.

## users
### **POST** /users/:id
Description: Fetch data about a specific user(student or staff)

Authorization: Root ,Admin, Staff, Students

### PATCH /users/:id
Description: used to update one user field/data in the database

Auth: Root, Admin

Req.body : **Required**
```json
{
    //field: value,
    "name": "Root"
}
```
**Response**: JSON
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

## /subject