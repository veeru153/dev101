# Comparisons and Logic

So far, we have looked at data. However, a program does not simply store data. The real world consists of decision making. These decisions depend on conditions and each condition may lead to a different result.

Similar to the real world, a program usually needs to either take decisions which depend on conditions. You can make conditions by making comparisons and applying logic.

## Comparing Values

We can perform equality checks (is equal, greater/lesser than). The following operators can achieve this result. For these example, let's assume `x = 1`:

- Equality - equal value: `==`

    ```ts
    x == 1          // true
    x == "1"        // true
    x == 2          // false
    ```

- Strict Equality - equal value AND equal type: `===`

    ```ts
    x === 1         // true
    x === "1"       // false
    x === 2         // false
    ```

- Inequality - unequal value: `!=`

    ```ts
    x != 1          // false
    x != "1"        // false
    x != 2          // true
    x != "2"        // true
    ```

- Inequality - unequal value AND unequal type: `!==`

    ```ts
    x !== 1         // false
    x !== "1"       // false
    x !== 2         // true
    x !== "2"       // false
    ```

- Greater than / Greater than or Equal to: `>` / `>=`

    ```ts
    x > 0           // true
    x >= 0          // true
    x > 1           // false
    x >= 1          // true
    x > 2           // false
    x >= 2          // false
    ```

- Less than / Less than or Equal to: `<` / `<=`

    ```ts
    x < 0           // false
    x <= 0          // false
    x < 1           // false
    x <= 1          // true
    x < 2           // true
    x <= 2          // true
    ```

### Mixing Types when Comparing Values
Comparisons must be done between the same types as mixing types may lead to confusing results. Some languages enforce the type rules very strictly. Others, like JS, not so much. When comparing different types in JS, different results may appear based on what types are being compared. A few things to keep in mind are:

- If a number and string are being compared, the string will be converted into a number for comparison.

    ```ts
    1 == "1"        // true
    1 <= "2"        // true
    1 >= "2"        // false
    ```
    
- If a number and string are being compared, and the string is non-numeric, it will be converted to `NaN` which stands for *Not a Number* and yields `false`.

    ```ts
    1 == "a"        // false
    1 <= "a"        // false
    1 >= "a"        // false
    ```

- If two strings are being compared, the strings are compared based on the [ASCII Table](https://www.ascii-code.com/).

    ```ts
    "1" == "a"      // false - they are not equal strings
    "1" >= "a"      // false - "1" (DEC 49) comes before "a" (DEC 97) in the ASCII Table
    "1" <= "a"      // true - "1" (DEC 49) comes before "a" (DEC 97) in the ASCII Table
    ```

It is always better to use strict equality when possible to prevent such cases.

### Truthy / Falsy Values

Recalling from the previous section about the boolean data type

> Any non-zero value is considered truthy. Non-zero values include all numbers except `0`, non-empty strings, etc. Conversely, a value of `0` or an empty string `""` are considered falsy values.

Using comparisons can explain the falsy value part well:

- `0`, `"0"`, `""` are all considered falsy values

    ```ts
    0 == false      // true
    0 === false     // false - they are different types (number, and a boolean)
    "0" == false    // true
    "0" === false   // false - they are different types (string, and a boolean)
    "" == false     // true
    "" === false    // false - they are different types (string, and a boolean)
    ```

- Most other values are considered truthy values. Non-empty strings when compared with `true` yield false but are considered truthy values when using them in an `if/else` block (discussed ahead).

    ```ts
    1 == true       // true
    1 === true      // false - different types
    "a" == true     // false
    "a" === true    // false
    ```

## Logical Operators

Logical operators allow you to get a result of a combination of two booleans. The follow three basic logical operators can be used for this.

### AND - `&&`

Checks multiple conditions and all of them need to be true for the result to be true.

```ts
const x = 1;

(x < 1) && (x > 1)      // false - (x < 1) => false, (x > 1) => false
(x == 1) && (x > 1)     // false - (x == 1) => true, (x > 1) => false
(x == 1) && (x >= 1)    // true - (x == 1) => true, (x => 1) => true
```

### OR - `||`

Checks multiple conditions and all of them need to be true for the result to be true.

```ts
const x = 1;

(x < 1) && (x > 1)      // false - (x < 1) => false, (x > 1) => false
(x == 1) && (x > 1)     // true - (x == 1) => true, (x > 1) => false
(x == 1) && (x >= 1)    // true - (x == 1) => true, (x => 1) => true
```

### NOT - `!`

Returns the opposite of the result of the condition. Essentially, `!true = false` and vice-versa.

```ts
const x = 1;

(x == 1)                // true
!(x == 1)               // false
(x < 1) && (x > 1)      // false
!(x < 1) && (x > 1)     // false
(x < 1) && !(x > 1)     // false
!((x < 1) && (x > 1))   // true
```

## Ternary Operator 

One last operator we will discuss in this is the ternary operator (also known as the conditional operator). This allows you to set a value based on some condition. The following is the syntax for this operator:  `condition ? valueIfTrue : valueIfFalse`.

Let's try to set `result` based on the value of `x`. The values `result` can take are the following two strings:
- `"x is 1"`
- `"x is not 1"`

```ts
let x = 1;
const result = (x == 1) ? "x is 1" : "x is not 1";
// Beyond this point, result = "x is 1"
...
x = 2;
// Beyond this point, result = "x is not 1"
```