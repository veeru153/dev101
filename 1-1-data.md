# Data

In the last part, we looked at how programming and data are related to one another. To summarize, a program is taking some data as an input, processing it and providing information as an output.

To process this data, a program needs to be able to understand the kind of data it is. This part explains how a program works with data. We won't go into the technical stuff just yet. This is just a brief overview of the data types and data structures.

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

Strings refer to text. They are called "strings" because they are made up of a *string* of characters. Strings are used to store any data that needs to be stored as text (names, addresses, etc.). The common operations that one can perform on a string are:

- string matching - checking if string matches another string
  - are "abcd" and "abcd" equal? - Yes!
  - are "abcd" and "abc" equal? - No!
- checking if the string contains a particular substring 
  - does "abcd" contain "b"? - Yes!
  - does "abcd" contain "bc"? - Yes!
  - does "abcd" contain "be"? - No!

### Booleans

Booleans refer to truthy or falsy values. The most common way of representing these values are `true` or `false`. They are most commonly used as flags and direct the flow of a program based on a condition. (We'll take a look at conditions and other logic soon.)
You will usually only check if a value is true or not (or conversely, is false or not) in your programs.


## Data Structures
