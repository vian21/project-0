# API docs

## Methods

Please Read: https://www.freecodecamp.org/news/rest-api-best-practices-rest-endpoint-design-examples/

### GET

Retrieve a specific field value eg. student's name given their ID

### POST

Use post to create a new entry in the database. Post requests should only be used for adding content.

### [PATCH](https://rapidapi.com/blog/put-vs-patch/#put-vs-patch)

update a specific field value.
we don't use PUT requests because PUT requests are meant to overwrite everything. By definition to make a PUT request you would have to send all the fields just to update one. Meanwhile, PATCH lets you send the field you want to update specifically.

### DELETE
Deleting a field in the database