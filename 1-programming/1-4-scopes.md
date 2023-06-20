# Scopes

It would be helpful to understand scopes before we begin to understand control flows. We may also use functions without formally introducing them. A function is piece of code that can be reused over and over again. We'll go over them in detail later.

In most cases, we don't want to loop over the entirety of our program. That is where scopes come in. They as they act as boundaries for the data contained within them. 

There are two main scopes - the Global Scope, and the Local Scope.

## Global Scope

As the name suggests, any data contained in the global scope can be used through out the file it is written in. These should be used only when required as handling too many variables can also be a nuisance. 

In JS, the `var` keyword typically had the global scope unless it was defined inside a function in which it had the local scope (the function scope, explained below). Pretty confusing, right? This is the reason why `let` and `const` were introduced later on. 

## Local Scope

The local scopes limits the declaration and definition of a variable to a localized block. The boundaries of a block is defined with squiggly brackets `{}` most of the time. Any variable declared and/or defined inside a local scope is only valid inside that scope. 

There *can* be two subcategories to the local scope in JS - the Block Scope, and the Function Scope. The boundaries of the block scope are the boundaries of a block. The boundaries of the function scope are the boundaries of the function. Originally, JS only had the global and the function scopes. The block scope was added later and makes JS feel similar to other languages. 

## Demonstrations

The code snippet below demonstrates the two scopes. 

Note: `console.log() prints whatever you give it to the console/terminal.`

```ts
let x = 1;              // Defined in Global Scope

if (x == 1) {           // if x is one
    x = 2;
    let y = 3;          // Defined in Local (Block) Scope
    console.log(y);     // Prints 3
    y = 4;
}

console.log(x);         // Prints 2
console.log(y);         // Error - y is not defined
```

Output:

```
3
2
...
console.log(y); 
            ^

ReferenceError: y is not defined
```

Let's also see how `var` would work in this case.

```ts
var x = 1;              // Defined in Global Scope

if (x == 1) {
    x = 2;
    var y = 3;          // Defined in Local (Block) Scope
    console.log(y);     // Prints 3
    y = 4;
}

console.log(x);         // Prints 2
console.log(y);         // Prints 4
```

Output:

```
3
2
4
```

To understand the `var` mess, let's look at the function scope as well.

```ts
var x = 1;

function main() {
    x = 2;
    var y = 3;          // Defined in Local (Function) Scope
    console.log(y);     // Prints 3
    y = 4;
}
main();
// We defined the function above and we called the function here 
// (to execute the lines of code present in the function)

console.log(x);         // Prints 2
console.log(y);         // Error - y is not defined
```

Output: 

```
3
2
...
console.log(y); 
            ^

ReferenceError: y is not defined
```

Both `let` and `const` would work similar to how they do in the block scope, there is a difference in how a `var` behaves which can lead to confusion in a large codebase. Throughout this series, we stick to using `let` and `const` as they are modern and more consistent.