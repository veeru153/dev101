# Hands On

We have a basic idea about programming at this point. It would be useful to look at some of these concepts in action. 

## Getting Started

Since this is the first time we are actually writing code, knowing how to run the code and see the results is a must. Since we are focussing on JS/TS (JS for now), we will be using the browser to run the code for now.

- Create a folder and call it anything. We'll be calling it `demo`. The name of the folder is not important. Open it in VSCode.

- Make two files here - `index.html` and `index.js`.

- Copy the contents of the files found [here](./demo/) to these two files.

- With the HTML file open, right click "Open with Live Server". A webpage should open up for you. If not, open a new tab in the browser and navigate to `localhost:5500`. If you see another number instead of `5500` on the bottom left of VSCode, then use that number instead. (This is the PORT number).

- Follow the instructions there to open the console. We'll be using that.

- If you are at this step, you should have seen `Hello World` printed in the console. If not, go through the instructions again to see if you missed anything.

## Understanding the Files

We have created two files - `index.html` and `index.js`. We will be working only in `index.js` (the script) for now. This is the file where you will write all the code. You will see the output in the console. Every time you update and save the script, the contents in the console will update (thanks to the Live Server extension that we installed before).

The HTML file is used to use the JS. We will be looking at HTML a bit later on. Ignore that file for now.

## Exercises

Let's put what we have learned so far to use. By the end of this page, you should have a basic understanding of the core programming concepts.

There are some additional things that we have not discussed so far but are added for you to explore and try on your own. I will be adding resources for the same.

If you need to take a look at a similar snippet for any of the following exercises, go [here](./1-9-hands-on-snippets.md).

### Creating and Printing Data

- Clear the contents of the script and create some variables of your choice. Print the data in the console with the help of `console.log()`.
- You should now be able to see the variables you have created in the script.
- Optionally, also print the data type of the variables alongside it.
- If you are having trouble at this step, revisit the [Data](./1-1-data.md) page.

### Math Operations

- Create as many numbers as you want. Try some basic math operations on them. Also experiment with the `Math` object.
- Revisit the [Math](./1-6-math.md) page if you are having trouble.

### Arrays and Loops

- Create an empty array and call it `numbers`.
- *Push* random numbers to `numbers`. Use the `.push()` method for this. Print `numbers`.
- Loop over `numbers` and print the numbers. You can access the current element by using `arr[i]` where `arr` is the array, and `i` is the index (position) of the current element.
- Loop over `numbers` and print the double of these numbers.
- **NEW** - Loop over this array and make a new array containing the square of the numbers. Use the `.map()` function for this part and print the new array. - [Resource](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- Loop over the numbers array and as long as there in another element in front of the current element and print the sum of the current element and the next element. Try this with both the `for` and the `while` loops.
- Finally, while there are elements in the array, *pop* elements out one by one and print them.
- Revisit [Data Structures](./1-2-data-structures.md) and [Control Flow](./1-5-control-flow.md) if you are having trouble.

### Sets and Maps

- Copy the following array of colors. It contains duplicates:
    ```ts
    const colors = ["red", "blue", "green", "yellow", "red", "pink", "orange", "green", "yellow", "green", "orange", "red", "pink", "red", "black", "green", "blue", "white", "white", "black", "red"];
    ```
- Print the length of this array using the `.length` property.
- Use the `.sort()` method to get the sorted array. Print the array.
- **NEW** - Loop over `colors` using the `.forEach()` method and add the elements into a set. Print the set. - [Resource](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- Loop over `colors` and make a map where the colors are the keys, and how many times they appear in the array are the values.
- **NEW** - Loop over the map using the `.forEach()` method and print the colors which appear more than twice in `colors`. - [Resource](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/forEach)
- Revisit [Data Structures](./1-2-data-structures.md) and [Control Flow](./1-5-control-flow.md) if you are having trouble.

### Strings

- **NEW** - Most string operations are performed using methods that we have not discussed before. Instead of linking every single method that we will use, the documentation of the entire String object is linked instead. Use this opportunity to explore the documentation on your own. - [Resource](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- Note: Strings are immutable on their own. You cannot modify the string directly (in place).
- Copy the following string:
    ```ts
    const lipsum = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
    ```
- Print the length of `lipsum`. Both arrays and strings have the same property for length.
- Split `lipsum`. Use space (`" "`) as the separator. Loop over the array and make a new array where the first character of every word is uppercase. Call this `jibberishArr` and print `jibberishArr`.
- Sort `jibberishArr` and join the array (with spaces) to make a new string. Call it `jibberish`. Print `jibberish`.
- Replace all occurrences of `","` with `""`. Replace all occurrences of `"."` with `"!"`. Print `jibberish`.
- Concatenate `jibberish` to `lipsum`. Keep a space between the two. Call this new string `merged`. Print `merged`. (This can be done two ways - using `+` and using `.concat()`. Try both.)
- Finally, get the substring of the original `lipsum` from `merged`. Call this `recovered`. Print `recovered`.