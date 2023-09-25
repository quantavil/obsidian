
```js
let luckyNum;

console.log(luckyNum); //undefined

  

luckyNum = null; //Expliclity represent empty value using null

luckyNum = 'Tweety-Swee';//string

// The semi-colon ; is optional in javascript, The javascript parser will add it automatically

  

const name = 'jeff'; // can't reassign later

// name = 'mick'; // TypeError: Assignment to constant variable.

  

var bad = 'avoid var unless you are smart';
```

### Scope
1. **Global Scope:**
    - Variables declared outside of any function or block have global scope.
    - They are accessible from anywhere in your JavaScript code, including inside functions and blocks.
    - Global variables have a lifetime that extends throughout the entire execution of the script.

Example of global scope:

```js
var globalVariable = "I'm global";

function foo() {
  console.log(globalVariable); // Accessing the global variable inside a function
}

foo(); // Outputs: "I'm global"
console.log(globalVariable); // Outputs: "I'm global"

```

In this example, `globalVariable` is declared in the global scope, so it can be accessed both inside and outside the `foo` function.

2. **Local Scope:**
    - Variables declared inside a function or block have local scope.
    - They are only accessible within the function or block where they are declared.
    - Local variables have a limited lifetime; they exist only as long as the function or block is executing.

```js
function bar() {
  var localVar = "I'm local";
  console.log(localVar); // Accessing the local variable inside the function
}

bar(); // Outputs: "I'm local"

console.log(localVar); // This will result in an error because localVar is not defined in the global scope

```

3.  **Block-level scope.**
It's important to note that JavaScript also supports block-level scope with the introduction of `let` and `const` in ES6. Variables declared with `let` and `const` have block scope, meaning they are confined to the block (e.g., a loop or an `if` statement) where they are declared.

```js
if (true) {
  let blockVar = "I'm inside a block";
  console.log(blockVar);
}

console.log(blockVar); // This will result in an error because blockVar is not defined in this scope

```
In this example, `blockVar` is declared within the `if` block and is not accessible outside of that block due to block-level scope.

The `var` keyword in JavaScript behaves in a way that can sometimes lead to unexpected or "weird" behavior due to its function-level scope and hoisting

**Hoisting:** Variables declared with `var` are hoisted to the top of their containing function or global scope. This means that the variable declarations are moved to the top of the scope during the compilation phase, but their assignments remain where they are in the code. This can lead to situations where a variable is accessible before it's declared.

```js
function hoistingExample() {
  console.log(x); // Outputs: undefined
  var x = 10;
}

hoistingExample();

```