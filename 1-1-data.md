# Data

In the last part, we looked at how programming and data are related to one another. To summarize, a program is taking some data as an input, processing it and providing information as an output.

To process this data, a program needs to be able to understand the kind of data it is. This part explains how a program works with data. We won't go deep into the technical stuff just yet. This is just a brief overview of the data types and data structures. I will try to keep the theoretical part as language agnostic as possible. However, the code snippets and their explanations will mostly use JS/TS.

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
  - are `"abcd"` and `"abcd"` equal? - Yes!
  - are `"abcd"` and `"abc"` equal? - No!
- checking if the string contains a particular substring 
  - does `"abcd"` contain `"b"`? - Yes!
  - does `"abcd"` contain `"bc"`? - Yes!
  - does `"abcd"` contain `"be"`? - No!

### Booleans

Booleans refer to truthy or falsy values. The most common way of representing these values are `true` or `false`. They are most commonly used as flags and direct the flow of a program based on a condition. (We'll take a look at conditions and other logic soon.)
You will usually only check if a value is true or not (or conversely, is false or not) in your programs.


## Data Structures

We have discussed a bit about data and the types of data that you can expect to work with while programming. However, data in the real world is usually structured. Let's consider a few examples:

- A shopping list contains a list of all the items that one needs to buy - Fruits, Cola, Chips, Chocolate, etc.
- A menu at a cafe contains the list of items the cafe sells with the price of each item

| Drink | Price |
|---|---|
| Espresso | 2.49 |
| Tea | 2.49 |
| Bubble Tea | 2.99 |
| Water | 0.99 |

Similar to the real world, you can organize and structure data while writing programs which makes it easier to work with. There are some data structures which are common to all languages but there is usually a way for you to make a custom blueprint (with a Class, we'll discuss these later). Some of the more common and baisc data structures include arrays/lists, sets, and maps. We'll take a look at these one by one. We will also use some code snippets here and it is okay to not understand some keywords at the moment.

### Arrays / Lists
Arrays or Lists are one dimensional data structures. As the name suggests, you can use these to store data as a list. There are some key differences between the two but that depends on the language you are using. In JS, these can be considered the same. We will call these arrays from here on. You will use code similar to the one written below to make an array.

```ts
const shoppingList = ["fruits", "cola", "chips", "chocolate"]
```

Notice the double quotes? This an array of strings. This is important to note as some languages will not allow you store data of different types in an array but others do. In JS, you are allowed to store different data types in arrays (but it is not recommended).

The most common operations performed on/with arrays are iterating, searching, and sorting. Almost all languages provide a way to carry these operations automatically but it is good to know how and when to use these operations.

- Iterating: You can visit each element in an array and perform certain action on that particular object. Say you make a list of times recorded on a stopwatch - `[3, 4, 5, 2, 6, 7]` - but the stopwatch was ahead by 1 second. You can iterate and reduce the values by 1. (Again, note the data types).

- Searching: Want to see if your shopping list contains Eggs? You can go over all elements one by one and see if the list contains eggs (or you could use the search feature provided by the language).

- Sorting: Revisit the stopwatch times. Want to sort the timings? Go over the values and swap them, or create a new array with the sorted values, or use the sorting feature provided by the language. (Sorting can be performed manually using algorithms and there are many sortin algorithms each with their pros and cons. At this stage, algorithms can be a little hard to work with. We'll explore these later)

The usage of operations on arrays will be discussed later on once we start writing programs.

### Sets

A Set is another one-dimensional data structure. Consider this like an array which does not allow duplicates. Making a shopping list with a set makes more sense as listing the same item multiple times makes no sense (unless you really like it in which case, go ahead but please use an array). However, stopwatch timings can be the same and we need a data structure which allows duplicates for that which is where using an array makes more sense.

You can make a set with

```ts
const shoppingList = new Set(["fruits", "cola", "chips", "chocolate"]);
```
or
```ts
const shoppingList = new Set();
shoppingList.add("fruits");
shoppingList.add("cola");
shoppingList.add("chips");
shoppingList.add("chocolate");
```

Trying to add the same data again will not work as a set can only contain unique values.

### Stacks
// TODO
### Queues
// TODO
### Maps
Maps are key-value pairs. Recall the menu example from before. That menu can be stored as a map where the name of the drink is the key and the price is the value. The types of all keys should be the same ideally. The types of all values can be different, but should be the same for consistency. For the sake of simplicity, we will keep the types of the values the same. To create the above menu as a map, you would use code similar to the ones written below. Ignore the syntax and keywords (like `new`) for now. We'll discuss that soon. The first line creates an empty map. The `.set` sets the value (`2.49`) for a key (`"espresso"`). Again, note the data types of the keys and the values.

```ts
const menu = new Map();
menu.set("espresso", 2.49);
menu.set("tea", 2.49);
menu.set("bubble tea", 2.99);
menu.set("water", 0.99);
```
There is a shorter way of creating a map, similar to how we created a set above but let's stick to this for now. The most common operations performed on a map include storing, fetching, updating, and removing values stored in the map. We'll look at these later when we start writing programs.