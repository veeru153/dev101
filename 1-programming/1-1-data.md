# Data

In the last part, we looked at how programming and data are related to one another. To summarize, a program is taking some data as an input, processing it and providing information as an output.

To process this data, a program needs to be able to understand the kind of data it is. This part explains how a program works with data. We won't go deep into the technical stuff just yet. This is just a brief overview of the data types and data structures. I will try to keep the theoretical part as language agnostic as possible. However, the code snippets and their explanations will mostly use JS/TS.

## Storing Data / Variables

Before we look at the different types of data, it would be beneficial to know how data is stored in a program. You will store mostly store data in variables. A variable will become an alias which will point to the data you need. In the below example, `x` is the variable for `"some-data"`. Instead of explicitly using `"some-data"` directly, you can simply refer to it by using `x`.

```ts
x = "some-data";
```

Since we will be using code snippets a lot starting now, it is helpful to know comments and how to use them. Anything after `//` is a comment and is not considered code. Any block of code contained inside `/* ... */` is also a comment but these can be multiline as well.

```ts
// This is a comment.

/* 
 * This is also a comment. But
 * this can be multiline as well.
 */

// You can also use the first 
// style to make multiline comments. 
```

In JS, to make variables, you either use `const` or `let` depending on whether you want to reassign variables. (There is a third way by using `var` but it isn't considered good practice so we'll skip over that).

### `const`

Short for constant, the values in these variables stays constant in the block the variable is declared in. (Blocks and scopes are important and will be discussed later. Just assume block = entire code for now).

These variables **cannot** be reassigned. The following code will **not** work and will throw an error.

```ts
const x = "abc";
x = "xyz";
```

### `let`

Variables created with `let` can be reassigned throughout the block of code. The following code is now valid.

```ts
let x = "abc";
// Beyond this point, the value stored in x is "abc"
...
x = "xyz";
// Beyond this point, the value stored in x is "xyz"
```

### Declaring vs Defining Variables

Declaring variables refers to the act of creating a variable (without a value).
Defining variables refers to the act of setting a value to a variable.

```ts
let x;        // Declaring x
x = 1;        // Defining x

const y = 2;  // Defining y
```

### Naming Conventions

Your variables should follow the following rules for them to be considered valid:
- the variable can only contain letters, numbers, underscores (_), and a dollar sign ($)
- the variable cannot start with a number

There are different formats you could use while writing variables. The most common ones are:
- camelCase
- snake_case
- SCREAMING_SNAKE_CASE

The choice is based on personal preference. It is better to be consistent in a project. In this series (and my personal preference) is to use:
- SCREAMING_SNAKE_CASE: for the most common constant variables (constants used everywhere in a project)
- camelCase: for everything else

Also, please use meaningful variable names. This is especially useful when working in a team as a simple `x` may not convey the significance of that variable and what data is contained inside it but something like `sum` or `total` explains that this variable contains the sum of some values. This also makes the code **self-documenting** and allows any one to understand what the code does without writing a bunch of comments.


## Data Types

As mentioned before, a program needs to know what type of data it is dealing with in order to provide the correct output. This is done by defining data types. Data types inform the program that it is currently working with numbers or text or an image and allows it to perform the correct actions (or display an error if the program does not handle the data correctly, more on errors later).

In general, you will be working with the following data types:
- Numbers - Integers, Decimals, etc.
- Strings - Text 
- Booleans - True or False

This list is **language agnostic** and each language has a different way of actually declaring the data types (some have none and they infer the type from the data but that is beyond the current scope). There are advanced data types as well but we'll take a look at those later.

### Numbers

Numbers are... well numbers. They can be integers or decimal point numbers. The common operations that can be performed with numbers are math operations.

### Strings

Strings refer to text. They are called "strings" because they are made up of a *string* of characters. A single element of a string is called a character. Strings are used to store any data that needs to be stored as text (names, addresses, etc.). The common operations that one can perform on a string are:

- string matching - checking if string matches another string
  - are `"abcd"` and `"abcd"` equal? - Yes!
  - are `"abcd"` and `"abc"` equal? - No!
- checking substring - checking if the string contains a particular string inside of it 
  - does `"abcd"` contain `"b"`? - Yes!
  - does `"abcd"` contain `"bc"`? - Yes!
  - does `"abcd"` contain `"be"`? - No!
- string transformation - modifying the string based on requirements
  - converting `"  abcd  "` to uppercase - `"  ABCD  "`
  - trimming extra whitespace from `"  abcd  "` - `"abcd"`
  - concatenating strings `"Hello"` and `" World!"` - `"Hello World!"`
  - replacing substring `"Hello"` in `"Hello World!"` with `"Hi"` - `"Hi World!"`

### Booleans

Booleans refer to truthy or falsy values. The most common way of representing these values are `true` or `false`. 

Any non-zero value is considered truthy. Non-zero values include all numbers except `0`, non-empty strings, etc. Conversely, a value of `0` or an empty string `""` are considered falsy values. This may seem confusing but experiment with this and it'll make sense. We will discuss more about these ahead.

They are most commonly used as flags and direct the flow of a program based on a condition. (We'll take a look at conditions and other logic soon.) You will usually only check if a value is true or not (or conversely, is false or not) in your programs.

## `typeof`

The `typeof` keyword can be used to obtain the *type of* of a data.

```ts
typeof 1;            // number
typeof "a string";   // string
typeof true;         // boolean
```

## Primitive and Non-Primitive Data Types

The data types discussed above are all **primitive** data types. These data types are immutable (the value cannot be modified without creating a new value). The notion of immutability has to do with how memory is handled by a language. **This can be considered an advanced topic** but I will try to explain it in an easier way. [Here is what I think is a good read on this topic if you are interested in reading more.](https://stackoverflow.com/a/52242541/14984918)

The memory on the computer consists of blocks. Each block has an address. Think of it as an apartment complex. Each apartment has an address and there are people living inside that apartment. Consider the following: John Smith lives in Apartment 101. You need to deliver a letter addressed to John Smith. You use the address provided (101) to get to John Smith and then deliver the address to them. 

Whenever you define a variable, for a computer, you are allocating some memory for the defined value. The variable contains the address of this memory block, i.e. the variable points to this memory block.

When you modify a value of a primitive data type, the following happens internally:

- you get the value using the address stored in the variable
- you modify the value
- you place the value inside a new block of memory
- you place the address inside the target variable

**Non-primitive** data types on the other hand ARE mutable, i.e. the value stored inside the memory block can be modified directly. The modified value stays in the same memory block. In JS, the object data type is the only non-primitive data type.

As developers, it can be helpful to know how this works. This information will be more useful when we work with functions later on.