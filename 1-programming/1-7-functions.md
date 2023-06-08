# Functions

Functions are reusable chunks of code. These are useful if you want to perform the same operation at many different parts in the code. A function can be written using the following syntax.

```ts
function name(args) {
    // code this function should execute
}
```

## Arguments (`args`)

You can pass in any arguments (args) to a function. They can be passed in two ways - pass by value and pass by reference. This is inconsistent between languages. The way the values are passed as arguments determine the values of data and variables through out the program. [Here is *what I think is* a good read on this topic.](https://stackoverflow.com/a/34971934/14984918)

### Pass by Value - Primitive Values

In JS, primitive values are passed by value. We can see this for ourselves by using the following code snippet.

```ts
function modifyPrimitiveValues(num, str) {
    console.log("[Inside Function] Before Modification:", num, str);
    num = 2;
    str = "modified data";
    console.log("[Inside Function] After Modification:", num, str);
}

const num = 1;
const str = "original data";

console.log("[Outside Function] Before calling modifyPrimitiveValues():", num, str);
modifyPrimitiveValues(num, str);
console.log("[Outside Function] After calling modifyPrimitiveValues():", num, str);
```

Output:

```ts
[Outside Function] Before calling modifyPrimitiveValues(): 1 original
[Inside Function] Before Modification: 1 original
[Inside Function] After Modification: 2 modified
[Outside Function] After calling modifyPrimitiveValues(): 1 original
```

The value in the global scope stays the same even after we call the function that is supposed to modify this value. This is because when we pass it to the function, the value is copied for use in the function. Even inside the function, the value stays the same unless we explicitly modify it.

### Pass by Reference - Non-Primitive Values

In JS, primitive values are passed by value. We can see this for ourselves by using the following code snippet.

```ts
function modifyArrayElements(arrayToModify) {
    console.log("[Inside Function] Before Modification:", arrayToModify);
    arrayToModify[0] = 4;
    console.log("[Inside Function] After Modification:", arrayToModify);
}

const arr = [1, 2, 3];
console.log("[Outside Function] Before calling modifyArrayElements():", arr);
modifyArrayElements(arr);
console.log("[Outside Function] After calling modifyArrayElements():", arr);
```

Output:

```ts
[Outside Function] Before calling modifyArrayElements(): [ 1, 2, 3 ]
[Inside Function] Before Modification: [ 1, 2, 3 ]
[Inside Function] After Modification: [ 4, 2, 3 ]
[Outside Function] After calling modifyArrayElements(): [ 4, 2, 3 ]
```

The value of the elements in the array are modified in the global scope from inside the function. This is because rather than copying the array, the reference of the array is passed to the function. If we instead update the `arrayToModify` variable, the reference to the outer array is lost and any changes to the array now will only impact the array inside the function. This is demonstrated in the snippet below.

```ts
function modifyArray(arrayToModify) {
    console.log("[Inside Function] Before Modification:", arrayToModify);
    arrayToModify = [5, 6, 7];
    console.log("[Inside Function] After Modification:", arrayToModify);
}

const arr = [1, 2, 3];
console.log("[Outside Function] Before calling modifyArray():", arr);
modifyArray(arr);
console.log("[Outside Function] After calling modifyArray():", arr);
```

Output:

```
[Outside Function] Before calling modifyArray(): [ 1, 2, 3 ]
[Inside Function] Before Modification: [ 1, 2, 3 ]
[Inside Function] After Modification: [ 5, 6, 7 ]
[Outside Function] After calling modifyArray(): [ 1, 2, 3 ]
```

## Why use Functions?

Say you wanted to check if a user is an adult to verify details (such as can they have a drivers license, can they have a bank account, are they allowed to vote, etc.), instead of checking whether the age of the use is greater than 18, you could use a function to write it once and use it anywhere.

The following piece of code:

```ts
const age = 24;
const canUserHaveDriversLicense = age >= 18;
const canUserHaveABankAccount = age >= 18;
const canUserVote = age >= 18;
const isUserLegallyAllowedToDrink = age >= 18;
```

can be written as:

```ts
function isAdult(age) {
    return age >= 18;
}

const canUserHaveDriversLicense = isAdult(age);
const canUserHaveABankAccount = isAdult(age);
const canUserVote = isAdult(age);
const isUserLegallyAllowedToDrink = isAdult(age);
```

## `return`

We have used the `return` keyword in the previous snippet. It *returns* a value to the variable. It can also be used to terminate the function mid way (technically you would be returning `void`). `void` is a keyword that signifies that the function returns no data type. The below snippets show how the `return` keyword can be used to break the flow of execution.

```ts
function processDriversLicenseApplication(age) {
    if (age < 18) {
        // if the age < 18, do not continue and 
        // return the control of flow to the calling function
        console.log("Too Young!")
        return;
    }
    // continue processing application is age >= 18
    console.log("Processing application...");
}

console.log(processDriversLicenseApplication(16));      // Too Young!
console.log(processDriversLicenseApplication(18));      // Processing application...
```

```ts
function getLastNumberAddedBeforeTargetSum(target) {
    let sum = 0;
    let i = 1;

    while (true) {
        // running an endless loop and adding the current value to the sum
        sum += i;
        if (sum >= target) {
            // if sum >= target, return the last number that was added
            // while keeping the sum below the target value
            return i - 1;
        }
        // if sum < target, increment the value
        i++;
    }

}
console.log(getLastNumberAddedBeforeTargetSum(5));      // 2
console.log(getLastNumberAddedBeforeTargetSum(11));     // 4
```