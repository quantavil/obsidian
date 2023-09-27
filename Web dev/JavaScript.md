
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

## Pass by Value & Pass by Reference


```javascript
// Pass by Value

let a = 10; // 'a' stores a primitive value (number)
let b = a;  // 'b' receives a copy of the value stored in 'a'

a = 20;     // Changing 'a' doesn't affect 'b'

console.log(a); // Output: 20
console.log(b); // Output: 10 (unchanged)

// Pass by Reference

let obj1 = { name: "Alice" }; // 'obj1' stores a reference to an object
let obj2 = obj1;              // 'obj2' now references the same object as 'obj1'

obj1.name = "Bob";            // Changing 'obj1' also changes 'obj2'

console.log(obj1.name); // Output: "Bob"
console.log(obj2.name); // Output: "Bob" (both are references to the same object)
```

In this code:

- **Pass by Value:**
  - When you assign a primitive value (e.g., number, string) to another variable, a copy of the value is made.
  - Changes to one variable do not affect the other.

- **Pass by Reference:**
  - When you assign an object (or an array) to another variable, you are actually copying a reference to the same object.
  - Changes made to the object through one variable are reflected when accessed through the other variable because both reference the same underlying object.



## This

```javascript
// 'this' in JavaScript

// 1. Global Object: In a browser, the global object is 'window'.
console.log(this === window); // 'this' refers to the global object

// 2. Regular Function and 'this': 'this' refers to the object that calls the function.
const person = {
  name: "Alice",
  greet: function () {
    console.log(`Hello, ${this.name}!`);
  },
};
person.greet(); // 'this' inside 'greet' refers to 'person' object

// 3. Arrow Function and 'this': 'this' retains the context of the surrounding code.
const person2 = {
  name: "Bob",
  greet: () => {
    console.log(`Hello, ${this.name}!`);
  },
};
person2.greet(); // 'this' inside arrow function still refers to the global object 'window'

// 'bind' method to set 'this'

// 4. Using 'bind' to set 'this' explicitly
const person3 = {
  name: "Charlie",
  greet: function () {
    console.log(`Hello, ${this.name}!`);
  },
};
const greetFunction = person3.greet.bind(person3); // 'bind' sets 'this' to 'person3'
greetFunction(); // 'this' inside 'greet' now refers to 'person3'

// Summary:

// - 'this' in JavaScript refers to different objects depending on the context.
// - Arrow functions capture the 'this' value from their surrounding code.
// - 'bind' allows you to explicitly set the 'this' value for a function.
// - In a browser, the global object is 'window'.

// 5. Accessing 'window' object properties
console.log(window.innerWidth); // Accessing 'innerWidth' property of 'window' object
```

In this code:

- `'this' in JavaScript`:
  - `this` can refer to the global object, which is `window` in a browser.
  - Inside a regular function, `this` refers to the object that calls the function.
  - Inside an arrow function, `this` retains the context of the surrounding code.

- `'bind' method to set 'this'`:
  - The `bind` method allows you to explicitly set the value of `this` for a function. It creates a new function with the specified `this` value.

- `Summary`:
  - The code summarizes the behavior of `this`, arrow functions, and `bind`.

- `Accessing 'window' object properties`:
  - It shows an example of accessing a property (`innerWidth`) of the global object (`window`).

This code demonstrates how `this` behaves in different contexts, how arrow functions capture `this`, and how `bind` can be used to set `this` explicitly. It also mentions that in a browser, the global object is typically referred to as `window`.

## Object

```javascript
// Object Literal

// 1. Object Literal: Creating an object using curly braces.
const personLiteral = {
  name: "Alice",
  age: 25,
};

// 2. Properties: Key-value pairs in an object.
console.log(personLiteral.name); // Accessing the 'name' property

// Object Constructor

// 3. Object Constructor: Creating an object using a constructor function.
function PersonConstructor(name, age) {
  this.name = name;
  this.age = age;
}

// 4. Creating an instance using the constructor.
const personConstructor = new PersonConstructor("Bob", 30);

// 5. Properties: Properties are defined using 'this' inside the constructor.
console.log(personConstructor.age); // Accessing the 'age' property
```

In this code:

- **Object Literal** is created using curly braces `{}` to define key-value pairs (properties).

- **Properties** are the key-value pairs inside an object, and they can be accessed using dot notation (e.g., `personLiteral.name`).

- **Object Constructor** is created using a constructor function. Properties are defined inside the constructor using `this`.

- An instance of an object is created using the `new` keyword followed by the constructor function (e.g., `const personConstructor = new PersonConstructor("Bob", 30)`).

- Properties in the constructor are accessed in the same way as in the object literal (e.g., `personConstructor.age`).

## OOPs

Certainly! Here's a concise explanation of JavaScript Object-Oriented Programming (OOP) concepts with inline comments:

```javascript
// 1. Class: A blueprint for creating objects
class Car {
  constructor(make, model) { // 4. Constructor: A special method to initialize object properties
    this.make = make;
    this.model = model;
  }
}

// 2. Object: Instances created from a class
const myCar = new Car("Toyota", "Camry");

// 3. Prototype Chaining: Objects inherit properties and methods from their prototype
Car.prototype.start = function() {
  console.log(`${this.make} ${this.model} is starting.`);
};

myCar.start(); // Outputs: "Toyota Camry is starting."


// 5. Instance Method: Functions defined within a class, operate on instance properties
Car.prototype.drive = function() {
  console.log(`${this.make} ${this.model} is driving.`);
};

myCar.drive(); // Outputs: "Toyota Camry is driving."

// 6. Static Method: A method called on the class itself, not on instances
class MathUtils {
  static square(x) {
    return x * x;
  }
}

const result = MathUtils.square(5); // Call static method directly

// 7. Encapsulation: Bundling data (properties) and methods (functions) into a single unit (class)
//   - Private properties and methods can be simulated using closures
// Encapsulation: Data hiding by making variables private
function Book(title, author) {
  // Private variables
  let _title = title;
  let _author = author;

  // Public method to get the book title
  this.getTitle = function() {
    return _title;
  };

  // Public method to set the book title
  this.setTitle = function(newTitle) {
    _title = newTitle;
  };
}

const myBook = new Book("The Great Gatsby", "F. Scott Fitzgerald");
console.log(myBook.getTitle()); // Output: The Great Gatsby


// 8. Inheritance: A mechanism where a class can inherit properties and methods from another class
class ElectricCar extends Car {
  constructor(make, model, batteryCapacity) {
    super(make, model); // Call the parent class constructor
    this.batteryCapacity = batteryCapacity;
  }

  charge() {
    console.log(`Charging ${this.make} ${this.model}'s ${this.batteryCapacity} kWh battery.`);
  }
}

const myElectricCar = new ElectricCar("Tesla", "Model 3", 75);

// 9. Polymorphism: Objects of different classes can be treated as objects of a common parent class
function startCar(car) {
  car.start();
}

startCar(myCar);           // Works with a regular Car
startCar(myElectricCar);    // Also works with an ElectricCar

// 10. Abstraction: Hiding complex implementation details and showing only essential features
//   - Abstract classes and methods are not directly instantiable

// 11. Getter/Setter: Methods used to access and modify object properties with controlled behavior
class Temperature {
  constructor(celsius) {
    this.celsius = celsius;
  }

  get fahrenheit() {
    return (this.celsius * 9/5) + 32;
  }

  set fahrenheit(value) {
    this.celsius = (value - 32) * 5/9;
  }
}

const temp = new Temperature(25);
console.log(temp.fahrenheit); // Accessing the getter
temp.fahrenheit = 68;         // Using the setter to update Celsius
console.log(temp.celsius);    // Checking the Celsius value
```

These are fundamental OOP concepts in JavaScript that help organize code and create reusable, structured, and maintainable programs.