
# Programming conventions

### 1. Naming - Camel case

we will be using camel case for naming variables in the back-end

```javascript
const fetchStudentName = async(arguments...) =>{
    // code ...
}
```

Link: https://en.wikipedia.org/wiki/Camel_case

### 2. **Every function does one thing/function**

Every function should only do one thing and every functionality in the app should be done by one function. This reduces reliance on one function and less code per function reducing the number of bugs. Smaller code is easier to read and understand. This is why function names should be well picked using action verbs and object being affected.

```javascript
function updateStudentName();
function updateStudentTelephone();
function updateStudentMark();
```

### 3. [JS Docs](https://google.github.io/styleguide/jsguide.html#jsdoc)

Always document your code. A function description should be included at the top of your function stating :

1. what it does
1. what are the arguments it takes, their types and which ones are required
1. return data and data types


```javascript
/*
 * Updates student's name
 * @param {number} id - student's number
 * @param {string} name - Student's new name
 * @param {string} [name] - Student's new name                     //now name is optional
 * @param {string} [name=No name] - Student's new name             //Name is optional and has a default value of 'No name'
 * @returns {boolean} whether the operation was successful or not
 *
 */
async function updateStudentName(id: number, name: string){
    // code ...
    return true
}
```

### 4. Make all functions asynchronous.

This will ensure that no function will block the program execution

```javascript
const deleteMark = (markId) =>{
    // code ...
}
```
