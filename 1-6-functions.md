# Functions

Functions are reusable chunks of code. These are useful if you want to perform the same operation at many different parts in the code. A function can be written using the following syntax.

```ts
function name(args) {
    // code this function should execute
}
```

## Arguments (`args`)

You can pass in any arguments (args) to a function. They can be passed in two ways - pass by value and pass by reference. This is inconsistent between languages. [Here is *what I think is* a good read on this topic.](https://stackoverflow.com/a/34971934/14984918)

// TODO: Explain how JS uses pass by value and pass by reference


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

// TODO: `return` keyword