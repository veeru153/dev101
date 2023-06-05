# Data Structures

We have discussed a bit about data, storing data, and the types of data that you can expect to work with while programming. However, data in the real world is usually structured. Let's consider a few examples:

- A shopping list contains a list of all the items that one needs to buy - Fruits, Cola, Chips, Chocolate, etc.
- A menu at a cafe contains the list of items the cafe sells with the price of each item

| Drink | Price |
|---|---|
| Espresso | 2.49 |
| Tea | 2.49 |
| Bubble Tea | 2.99 |
| Water | 0.99 |

Similar to the real world, you can organize and structure data while writing programs which makes it easier to work with. There are some data structures which are common to all languages but there is usually a way for you to make a custom blueprint (with a Class, we'll discuss these later). Some of the more common and basic data structures include arrays/lists, sets, and maps. We'll take a look at these one by one. We will also use some code snippets here and it is okay to not understand some keywords at the moment.

## Arrays / Lists
Arrays or Lists are one dimensional data structures. As the name suggests, you can use these to store data as a list. There are some key differences between the two but that depends on the language you are using. In JS, these can be considered the same. We will call these arrays from here on. You will use code similar to the one written below to make an array.

```ts
const shoppingList = ["fruits", "cola", "chips", "chocolate"]
```

Notice the double quotes? This an array of strings. This is important to note as some languages will not allow you store data of different types in an array but others do. In JS, you are allowed to store different data types in arrays (but it is not recommended).

The most common operations performed on/with arrays are iterating, searching, and sorting. Almost all languages provide a way to carry these operations automatically but it is good to know how and when to use these operations.

- Iterating: You can visit each element in an array and perform certain action on that particular object. Say you make a list of times recorded on a stopwatch - `[3, 4, 5, 2, 6, 7]` - but the stopwatch was ahead by 1 second. You can iterate and reduce the values by 1. (Again, note the data types).

- Searching: Want to see if your shopping list contains Eggs? You can go over all elements one by one and see if the list contains eggs (or you could use the search feature provided by the language).

- Sorting: Revisit the stopwatch times. Want to sort the timings? Go over the values and swap them, or create a new array with the sorted values, or use the sorting feature provided by the language. (Sorting can be performed manually using algorithms and there are many sorting algorithms each with their pros and cons. At this stage, algorithms can be a little hard to work with. We'll explore these later)

The usage of operations on arrays will be discussed later on once we start writing programs.

## Sets

A Set is another one-dimensional data structure. Consider this like an array which does not allow duplicates. Making a shopping list with a set makes more sense as listing the same item multiple times makes no sense (unless you really like it in which case, go ahead but please use an array). However, stopwatch timings can be the same and we need a data structure which allows duplicates for that which is where using an array makes more sense.

You can make a set with either of the following code snippets. Both result in the same set. Ignore the syntax and keywords (like `new`) for now. We'll discuss that soon.

```ts
const shoppingList = new Set(["fruits", "cola", "chips", "chocolate"]);
```

```ts
const shoppingList = new Set();
shoppingList.add("fruits");
shoppingList.add("cola");
shoppingList.add("chips");
shoppingList.add("chocolate");
```

Trying to add the same data again will not work as a set can only contain unique values.

## Stacks
Stacks are another one-dimensional, linear data structure which follow the first-in-first-out (FIFO) concept - what enters first is what leaves first. Consider a *stack* of plates. You pick from the top, you add to the top. That's pretty much what a stack does.

Say you have the following stack:

```ts
stack = [2, 3, 4, 5, 6];
```

You want to add (the operation is called *push*) `7` to it. It goes either at the front or at the rear which would result in one of the following.

```ts
result = [7, 2, 3, 4, 5, 6];   // Push to the front, or 
result = [2, 3, 4, 5, 6, 7];   // Push to the rear
```

You can only remove (*pop*) a value from an end as well, the front or the rear. Consider the original stack again. Popping a value from this stack would result in one of the following:

```ts
result = [2, 3, 4, 5];    // Pop from the rear, or
result = [3, 4, 5, 6];    // Pop from the front
```

The implementation of a stack is different across languages. In JS, you can use an array and some of the operations provided out of the box to use it like a stack. 

Although, pushing and popping from both ends have been demonstrated, both pushing and popping should only be done from one end (let's call this the active end) for it to truly be a stack. In further demonstrations, unless explicitly mentioned, the active end will be the rear, i.e. both push and pop operations will happen at the rear.

## Queues
Queues are another one-dimensional, linear data structure. As the name suggests, this a queue like the queue in the bank. People join the queue at one end and the leave from the other. This is the last-in-first-out (LIFO) concept - what enters last is what leaves first.

Say you have the following queue:

```ts
stack = [2, 3, 4, 5, 6];
```

You want to add `7` to it. It goes either at the front or at the rear which would result in one of the following.

```ts
result = [2, 3, 4, 5, 6, 7];   // Add to the rear, or 
result = [7, 2, 3, 4, 5, 6];   // Add to the front
```

You can only remove a value from an end as well, the front or the rear. Consider the original stack again. Popping a value from this stack would result in one of the following:

```ts
result = [3, 4, 5, 6];    // Remove from the front, or
result = [2, 3, 4, 5];    // Remove from the rear
```

The implementation of a queue is different across languages. In JS, you can use an array and some of the operations provided out of the box to use it like a stack. 

Although, adding and removing or elements from both ends have been demonstrated, both adding and removing of elements should only be done from different ends for it to truly be a queue. In further demonstrations, unless explicitly mentioned, the addition will be done at the rear while the removal will be done from the front.

## Maps
Maps are key-value pairs. Recall the menu example from before. That menu can be stored as a map where the name of the drink is the key and the price is the value. The types of all keys should be the same ideally. The types of all values can be different, but should be the same for consistency. For the sake of simplicity, we will keep the types of the values the same. To create the above menu as a map, you would use code similar to the ones written below. The first line creates an empty map. The `.set` sets the value (`2.49`) for a key (`"espresso"`). Again, note the data types of the keys and the values.

```ts
const menu = new Map();
menu.set("espresso", 2.49);
menu.set("tea", 2.49);
menu.set("bubble tea", 2.99);
menu.set("water", 0.99);
```
There is a shorter way of creating a map, similar to how we created a set above but let's stick to this for now. The most common operations performed on a map include storing, fetching, updating, and removing values stored in the map. We'll look at these later when we start writing programs.

---
### A Note on Data Types

All data structures discussed above are **non-primitive** data types in JS. You can freely modify the contents of the data without changing the location of the *object* as these are all considered objects by JS. This can be validated by using the `typeof` keyword.

```ts
typeof [];              // object
typeof new Map();       // object
typeof new Set();       // object
```