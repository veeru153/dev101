# Control Flow

Now that we have discussed making conditions with the help of comparison and logical operators, we can control the flow of execution of any program. This can be achieved by Branching. Certain repetitive actions can also be performed until a certain condition is met by creating a loop.

## Branching

By branching code, you can make the program perform different operations based on conditions. This can be done in two ways - `if-else` or `switch`.

### `if-else`

The `if-else` block allows you to define the logic if a particular condition is satisfied. We saw an `if` block in the scopes section. Here we understand this in detail. The following snippet demonstrates this.

```ts
const x = 1;
let result = "";

if (x = 1) {
    // code to execute if x is 1:
    result = "x is 1";
} else {
    // code to execute is x is not 1:
    result = "x is NOT 1";
}

console.log(result);
```

Output:

```
x is 1
```

This can be extended to incorporate more conditions by using the `else if` blocks:

```ts
const x = 2;
let result = "";

if (x = 1) {
    // code to execute if x is 1:
    result = "x is 1";
} else if (x = 2) {
    // code to execute if x is 2:
    result = "x is 2";
} else {
    // code to execute is x is not 1 or 2:
    result = "x is not 1 or 2";
}

console.log(result);
```

Output:

```
x is 2
```

Note, the `else` block is **NOT** mandatory. Skipping the `else` block does not break the program.

### `switch`

The `switch` block allows you to achieve the same effect with a slightly different syntax. The following code snippets demonstrates how you can achieve the `if-else-if-else` example from above.

```ts
const x = 2;

switch(x) {
    case 1:
        console.log("x is 1");
        break;
    case 2:
        console.log("x is 2");
        break;
    default:
        console.log("x is not 1 or 2");
        break;
}
```

Output:

```
x is 2
```

We see two new keywords here - `break` and `default`. 
- The `break` keyword is used to *break* the flow and skip the rest of the switch statement. The control is transferred to the end of the `switch` block.
- The `default` keyword acts as a fallback if none of the cases defined before it have been satisfied. This can be considered equal to the `else` block from the `if-else` blocks.

The `switch` is used when there are too many conditions which can make the `if-else` block seem messy. One other difference is the placement of the `break` keyword. The flow never *breaks* until a `break` is encountered. If you choose to omit it completely, all cases will be considered. Try removing the `break` keywords (one at time or all of them, your choice) from the above code snippet and see the results for yourself.


## Looping

Looping allows you loop over *iterables*. Iterables are objects that can be looped over. This can include the characters in a string, the elements of an array, etc. You can also loop using a range (loop from 0 to 10, etc.)

This can be performed in three ways - `for`, `while`, `do-while`

### `for`

The `for` loop lets you loop over piece of code as long as the next element in the iterable exists. You can achieve the following:
- for *all elements of an array*, do something
- for *all characters of a string*, do something
- for *numbers between 0 and 10*, do something

The syntax of a basic `for` loop is:

```ts
for (startingValue; endingCondition; valueUpdater) {
    ...
}
```
The below code prints all the numbers from 1 to 10 by using a `for` loop.

```ts
for (let i = 1; i <= 10; i++) {
    console.log(i);     // We can use the current value of the iterator
}
```

Output:

```
1
2
3
4
5
6
7
8
9
10
```

The below code calculates the sum of all odd numbers between 1 and 10 (both inclusive).

```ts
let sum = 0;

for (let i = 1; i <= 10; i = i + 2) {
    sum = sum + i;
}

console.log(sum);
```

Output:

```
25
```

There are variations of the `for` loop as well - `for-in` and `for-of`. We'll look at these later.

### `while`

The `while` loop continues as long as the condition is met (i.e. the condition is a truthy value). The main difference with the `for` loop is that initial value of the iterator has to be defined outside the `while` loop and the value has to be updated inside the loop. The syntax of a `while` loop is as follows.

```ts
while(condition) {
    ...
}
```

To print all the numbers from 1 to 10 using a `while` loop, you would use the following snippet.

```ts
let i = 1;

while (i <= 10) {
    console.log(i);
    i++;
}
```

Try to make the snippet to calculate the sum of all odd numbers between 1 and 10 (both inclusive) on your own.

If the condition is false by default, the code inside the `while` loop is never executed.

```ts
const x = 1;

while (x <= 0) {
    console.log("x is less than or equal to 0");
}

console.log("x is 1");
```

Output:

```ts
x is 1
```

### `do-while`

The `do-while` loop is similar to the `while` loop. One notable difference is the syntax.

```ts
do {
    ...
} while (condition)
```

To print all the numbers from 1 to 10 using a `do-while` loop, you would use the following snippet.

```ts
let i = 1;

do {
    console.log(i);
    i++
} while (i <= 10);
```

Try to make the snippet to calculate the sum of all odd numbers between 1 and 10 (both inclusive) on your own.

Another important difference is that the code written inside the `do` block is **executed at least once** even if the condition is false by default. This is not the case with the `while` loop as demonstrated above.

```ts
const x = 1;

do {
    console.log("x is less than or equal to 0");
}
while (x <= 0);

console.log("x is 1");
```

Output:

```
x is less than or equal to 0
x is 1
```

### `break` and `continue`

The two commonly used keywords used when making loops are `break` and `continue`. 

We have already looked at `break` when discussing the `switch` block. It works the same way in a loop.

The `continue` keyword is used to skip the execution for the current value of the iterator.

If you were printing the numbers from 1 to 10 but for some reason, wanted to skip the number 5, you can skip it using the `continue` keyword. The code snippet below uses the `for` loop to demonstrate the use of this keyword. It works similarly in the `while` and `do-while` loops.

```ts
for (let i = 1; i <= 10; i++) {
    if (i === 5) {
        continue;
    }
    console.log(i);
}
```

Output:

```
1
2
3
4
6
7
8
9
10
```

Try to write the code for the same using the `while` and `do-while` on your own.

### Infinite Loops

Now that we have discussed how looping works, it is important to look into infinite loops. These arise when the terminating condition is never met. This can be both intentional or unintentional. The problem occurs when this occurs unexpectedly. The sequence of instructions will continue to execute which may result in a slight decrease in performance of the device it is running on. The only way to stop an infinite loop is to terminate the program.