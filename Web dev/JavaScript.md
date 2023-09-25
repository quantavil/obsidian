
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

1. **Hoisting:** Variables declared with `var` are hoisted to the top of their containing function or global scope. This means that the variable declarations are moved to the top of the scope during the compilation phase, but their assignments remain where they are in the code. This can lead to situations where a variable is accessible before it's declared.

```js
function hoistingExample() {
  console.log(x); // Outputs: undefined
  var x = 10;
}

hoistingExample();

```

2. **Function-Level Scope:** Variables declared with `var` have function-level scope, which means they are not block-scoped. This can lead to unexpected behavior when using `var` inside blocks like `if` statements or loops.
```js
if (true) {
  var y = 20;
}

console.log(y); // Outputs: 20 (even though 'y' was declared inside the 'if' block)

```

**Variable Re-declaration:** Variables declared with `var` can be re-declared within the same scope without generating an error.

```js
var z = 30; var z = 40; // This does not produce an error console.log(z); // Outputs: 40

```

Unlike `let` and `const`, which do not allow re-declaration of variables in the same scope, `var` permits it.

## Function

```js
// 1. Function: A reusable block of code that performs a specific task.
function greet(name) {
  return `Hello, ${name}!`;
}

// 2. Parameters: Variables that function accepts as input (placeholders).
// In this case, 'name' is a parameter of the 'greet' function.

// 3. Return Value: The value a function gives back after its execution.
// 'greet' returns a greeting message.

// 4. Function Expression: Assigning a function to a variable or constant.
const greetExpression = function(name) {
  return `Hello, ${name}!`;
};

// 5. Higher-Order Function: A function that takes other functions as arguments or returns them.
function repeat(func, n) {
  for (let i = 0; i < n; i++) {
    console.log(func(i));
  }
}

// 6. Closure: A function that "remembers" its lexical scope even when executed outside it.
function createCounter() {
  let count = 0;
  return function() {
    return ++count;
  };
}

// Example usage of concepts:
console.log(greet("Alice")); // Output: Hello, Alice!
console.log(greetExpression("Bob")); // Output: Hello, Bob!

function sayHi(index) {
  return `Hi number ${index}`;
}

repeat(sayHi, 3); // Output: Hi number 0, Hi number 1, Hi number 2

const counter = createCounter();
console.log(counter()); // Output: 1
console.log(counter()); // Output: 2
console.log(counter()); // Output: 3

```


- **Function**
  - A reusable block of code that performs a specific task.

- **Parameters**
  - Variables that a function accepts as input (placeholders).
  - In this case, 'name' is a parameter of the 'greet' function.

- **Return Value**
  - The value a function gives back after its execution.
  - 'greet' returns a greeting message.

- **Function Expression**
  - Assigning a function to a variable or constant.
  - 'greetExpression' is a function expression.

- **Higher-Order Function**
  - A function that takes other functions as arguments or returns them.
  - 'repeat' is a higher-order function.

- **Closure**
  - A function that "remembers" its lexical scope even when executed outside it.
  - 'createCounter' returns a closure function that maintains a 'count' variable.

- **Example Usage of Concepts**
  - `console.log(greet("Alice"));` outputs "Hello, Alice!"
  - `console.log(greetExpression("Bob"));` outputs "Hello, Bob!"
  - `repeat(sayHi, 3);` repeats the 'sayHi' function three times with different indices.
  - `const counter = createCounter();` creates a counter using a closure.
  - `console.log(counter());` outputs 1, `console.log(counter());` outputs 2, and so on, maintaining state between calls.

## Memory

```js
// Call Stack

// 1. Function: A reusable block of code.
function greet(name) {
  return `Hello, ${name}!`;
}

// 2. Call Stack: A data structure that keeps track of function calls.
console.log(greet("Alice")); // Push 'greet' onto the call stack
// 'greet' execution finishes, so it's popped off the stack

// Heap Memory

// 3. Heap Memory: A region for dynamically allocated memory.
const person = { name: "Bob", age: 30 }; // Create an object in the heap

// 4. Reference: A pointer to the memory location of an object.
const reference = person; // 'reference' points to the same object in the heap

// 5. Variables: Store references to objects.
const age = person.age; // 'age' stores the age value from the object

// 6. Garbage Collection: Automatic memory management to reclaim unused memory.
person = null; // 'person' no longer references the object in the heap
// The object may be eligible for garbage collection if no references exist

// 7. Stack vs. Heap: Stack stores function call information and primitives,
// while the heap stores dynamically allocated data like objects.

// 8. Stack Overflow: Occurs when the call stack becomes too deep due to recursive function calls.
// Example: Uncomment the line below to trigger a stack overflow.
// function infiniteLoop() { infiniteLoop(); }
// infiniteLoop(); // This would result in a stack overflow error

// 9. Memory Leaks: Happen when memory is not released properly.
// Properly managing references and using garbage collection helps prevent memory leaks.
```

In this code:

- **Call Stack:**
    
    - The call stack is a data structure that keeps track of function calls.
    - When a function is called, it's pushed onto the stack, and when it returns, it's popped off the stack.
    - The call stack ensures the order of execution in JavaScript.
- **Heap Memory:**
    
    - Heap memory is a region for dynamically allocated memory.
    - Objects and data that have a longer lifespan are stored in the heap.
    - Variables in JavaScript store references to objects in the heap.
- **Reference:**
    
    - References are pointers to the memory location of an object in the heap.
    - Multiple variables can reference the same object in the heap.
- **Garbage Collection:**
    
    - Garbage collection is an automatic process that reclaims memory from objects that are no longer reachable.
    - When all references to an object are removed, it becomes eligible for garbage collection.
- **Stack vs. Heap:**
    
    - The stack stores function call information and primitive data types.
    - The heap stores dynamically allocated data like objects and arrays.
- **Stack Overflow:**
    
    - A stack overflow occurs when the call stack becomes too deep, often due to recursive function calls.
- **Memory Leaks:**
    
    - Memory leaks happen when memory is not released properly, typically due to retaining references to objects that are no longer needed.
    - Properly managing references and using garbage collection helps prevent memory leaks.