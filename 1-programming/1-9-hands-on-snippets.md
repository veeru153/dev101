# Hands On! - Snippets

### Creating and Printing Data

```ts
const a = "Hello";
const b = 12;
const c = false;

console.log(a, typeof a);
console.log(b, typeof b);
console.log(c, typeof c);
```

### Math Operations

```ts
const x = 102;
const y = 13;

console.log(x + y);
console.log(x * y);
console.log(Math.pow(x, y));
console.log(Math.min(x, y));
```

### Arrays and Loops

```ts
console.log("Creating the Array");
const numbers = [];
numbers.push(1);
numbers.push(3);
numbers.push(7);
numbers.push(4);
numbers.push(21);
numbers.push(9);
numbers.push(16);
console.log(numbers);

console.log("- Printing the elements of the array");
for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}

console.log("- Printing the double of the elements of the array");
for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i] * 2);
}

console.log("- Creating a new array of squares");
const squares = numbers.map(num => Math.pow(num, 2));
console.log(squares);

console.log("- Adding adjacent elements - for loop")
for (let i = 0; i < numbers.length - 1; i++) {
    console.log(numbers[i] + numbers[i + 1]);
}

console.log("- Adding adjacent elements - while loop")
let i = 0;
while (i < numbers.length - 1) {
    console.log(numbers[i] + numbers[i + 1]);
    i++;
}

console.log("- Popping numbers");
while (numbers.length !== 0) {
    const num = numbers.pop();
    console.log(num);
}
```

### Sets and Maps

```ts
const colors = ["red", "blue", "green", "yellow", "red", "pink", "orange", "green", "yellow", "green", "orange", "red", "pink", "red", "black", "green", "blue", "white", "white", "black", "red"];

console.log("Length", colors.length);

console.log("- Sorting the array");
const sortedColors = colors.sort();
console.log(sortedColors);

console.log("- Making a set from the array");
const set = new Set();
colors.forEach(color => {
    set.add(color);
})
console.log(set);

console.log("- Making a map from the array");
const map = new Map();
colors.forEach(color => {
    if (map.has(color)) {
        map.set(color, map.get(color) + 1);
    } else {
        map.set(color, 1);
    }
})
console.log(map);

console.log("- Printing the colors that appear more than twice in the array");
map.forEach((value, key) => {
    if (value > 2) {
        console.log(key);
    }
})
```

### Strings

```ts
const lipsum = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.";

console.log("Length", lipsum.length);

console.log("- Making jibberishArr");
const jibberishArr = lipsum.split(" ").map((word => {
    const splitWord = word.split("");
    splitWord[0] = splitWord[0].toUpperCase();
    return splitWord.join("");
}))
console.log(jibberishArr);

console.log("- Making jibberish");
const jibberish = jibberishArr.sort().join(" ");
console.log(jibberish);

console.log("- Replacing characters");
jibberish.replaceAll(",", "");
jibberish.replaceAll(".", "!");
console.log(jibberish);

console.log("- String concatenation");
const merged = lipsum.concat(" ", jibberish);
// or merged = lipsum + " " + jibberish;
console.log(merged);

console.log("- Substrings");
const recovered = merged.substring(0, lipsum.length);
console.log(recovered);
```