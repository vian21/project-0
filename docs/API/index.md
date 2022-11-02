# API docs

## Programming conventions

1. Camel case

we will be using camel case for naming variables in the back-end

```
const fetchStudentName = async(arguments...) =>{

}
```

2. Make all functions asynchronous.

This will ensure that no function will block the program execution

```
const deleteMark = (markId) =>{

}
```

Link: https://en.wikipedia.org/wiki/Camel_case

3. Every function does one thing/function

Every function should only do one thing and every functionality in the app should be done by one function. This reduces reliance on one function and less code per function reducing the number of bugs. Smaller code is easier to read and understand. This is why function names should be well picked using action verbs and object being affected.

```
fn updateStudentName();
fn updateStudentMark();
```

4 JS docs

Always document your code. A function description should be included at the top of your function stating :

1. what it does
1. what are the arguments it takes, their types and which ones are required
1. return data and data types

```

```

## Methods

Please Read: https://www.freecodecamp.org/news/rest-api-best-practices-rest-endpoint-design-examples/

## GET

Retrieve a specific field value eg. student's name given their ID

## POST

Add a field

## UPDATE

update a specific field value

## DELETE
