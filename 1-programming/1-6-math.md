# Math

Math plays a crucial role in programming. Most tasks require a basic knowledge of algebra which is what we will focus on. You will need to know basic arithmetic operations and how to use the `Math` object.

## Basic Math Operations

The basic math operations are addition, subtraction, multiplication, and division. Another commonly used operation is the remainder operation. These work the way you expect them to work.

```ts
const a = 5;
const b = 3;

console.log("Sum :", a + b);
console.log("Difference :", a - b);
console.log("Product :", a * b);
console.log("Quotient :", a / b);
console.log("Remainder :", a % b);
console.log("Exponentiation :", a ** b);
```

Output:

```
Sum : 8
Difference : 2
Product : 15
Quotient : 1.6666666666666667
Remainder : 2
Exponentiation : 125
```

## Self Updating Variables

When a number is being added to a variable (`a = a + 2`), you can use a shorter syntax to achieve the same (`a += 2`). This can be done for most other operators.

```ts
let a = 10;
console.log("Original Value (a) :", a);
a += 2;
console.log("Adding to self (a += 2) :", a);
a -= 4;
console.log("Subtracting from self (a -= 4) :", a);
a *= 2;
console.log("Multiplying to self (a *= 2):", a);
a /= 4;
console.log("Dividing from self (a /= 4) :", a);
```

Output: 

```
Original Value (a) : 10
Adding to self (a += 2) : 12
Subtracting from self (a -= 4) : 8
Multiplying to self (a *= 2): 16
Dividing from self (a /= 4) : 4
```

## Incrementing / Decrementing

Similar to self updating variables, there is a shorter syntax for incrementing (`a = a + 1`). Incrementing can be performed by either `a++` or `++a`. These both achieve the same result (i.e. both increment `a`) but the way the values are updated is slightly different.

The former is known as post-increment. The value is updated AFTER the value is used (i.e. the original value is used). The latter refers to pre-increment. The value is updated BEFORE the value is used (i.e. the incremented value is used.).

The same actions can be performed for decrementing the values as well. These are most commonly used in loops.

```ts
let a = 10;
console.log("Original Value (a) :", a);
console.log("Post-incrementing (a++) : ", a++);     // a is updated AFTER printing
console.log("Current Value (a) :", a);
console.log("Pre-incrementing (++a) : ", ++a);      // a is updated BEFORE printing
console.log("Current Value (a) :", a);
a = 10;
console.log("Resetting Value (a) :", a);
console.log("Pre-decrementing (--a) : ", --a);      // a is updated BEFORE printing
console.log("Current Value (a) :", a);
console.log("Post-decrementing (a--) : ", a--);     // a is updated AFTER printing
console.log("Current Value (a) :", a);
```

Output:

```
Original Value (a) : 10
Post-incrementing (a++) :  10
Current Value (a) : 11
Pre-incrementing (++a) :  12
Current Value (a) : 12
Resetting Value (a) : 10
Pre-decrementing (--a) :  9
Current Value (a) : 9
Post-decrementing (a--) :  9
Current Value (a) : 8
```

## Using the `Math` Object

If you need to use mathematical constants or need to perform advanced calculations (trigonometric functions, exponents, logarithms, etc.), you can use the intrinsic `Math` object. The following code snippet demonstrates some commonly used properties and methods. More details can be found on the [Mozilla Developer Network (MDN) Math docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math). 

```ts
console.log("Maximum :", Math.max(5, 3));
console.log("Minimum :", Math.min(5, 3));
console.log("Absolute :", Math.abs(-5));
console.log("Random (between 0 and 1) :", Math.random())

console.log("Round (to nearest whole number) :", Math.round(1.4));
console.log("Floor (round DOWN to nearest whole number) :", Math.floor(1.4));
console.log("Ceil (round UP to nearest whole number) :", Math.ceil(1.4));

console.log("Exponents :", Math.pow(5, 3));
console.log("Log (base 10) :", Math.log10(10));
```

Output:

```
Maximum : 5
Minimum : 3
Absolute : 5
Random (between 0 and 1) : 0.6295725041608446
Round (to nearest whole number) : 1
Floor (round DOWN to nearest whole number) : 1
Ceil (round UP to nearest whole number) : 2
Exponents : 125
Log (base 10) : 1
```