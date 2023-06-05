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
```

Output:

```
Sum : 8
Difference : 2
Product : 15
Quotient : 1.6666666666666667
Remainder : 2
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