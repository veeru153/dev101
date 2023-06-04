# Control Flow

Now that we have discussed making conditions with the help of comparison and logical operators, we can control the flow of execution of any program. This can be achieved by Branching. Certain repetitive actions can also be performed until a certain condition is met by creating a loop.

## Branching

By branching code, you can make the program perform different operations based on conditions. This can be done in two ways - `if/else` or `switch/case`.

### `if/else`

The `if/else` block allows you to define the logic if a particular condition is satisfied. We saw an `if` block in the scopes section. Here we understand this in detail. The following snippet demonstrates this.

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

### `switch/case`

## Looping

// TODO - for, while, do-while