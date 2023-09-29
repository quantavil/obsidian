
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
// 1. Function: A reusable block of code that performs a specific task.It will always Hoisted up to the top of the file i.e. 'use anywhere in the file'
// Use it for Declaration for Global code 
function greet(name) {
  return `Hello, ${name}!`;
}

// 2. Parameters: Variables that function accepts as input (placeholders).
// In this case, 'name' is a parameter of the 'greet' function.

// 3. Return Value: The value a function gives back after its execution.
// 'greet' returns a greeting message.

// 4. Function Expression: Assigning a function to a variable or constant.It will not be created until it encounter in the code, so any code above it cannot reference this function
// Use it for Expression for  Local code 
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

## Spread

```javascript
// Example object
const sourceObject = { a: 1, b: 2 };

// Example 1: Using Object.assign to combine objects
const targetObject1 = { c: 3 };
const combinedObject1 = Object.assign(targetObject1, sourceObject);

console.log(combinedObject1);
// Output: { c: 3, a: 1, b: 2 }

// Note: Object.assign modifies the targetObject1 in place and returns the modified object.


// Example 2: Using the spread operator (...) to combine objects
const targetObject2 = { c: 3 };
const combinedObject2 = { ...targetObject2, ...sourceObject };

console.log(combinedObject2);
// Output: { c: 3, a: 1, b: 2 }

// Note: The spread operator (...) creates a new object with the combined properties of targetObject2 and sourceObject.


// Additional Note: Using spread operator for array concatenation
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

const concatenatedArray = [...arr1, ...arr2];
console.log(concatenatedArray);
// Output: [1, 2, 3, 4, 5, 6]
```

In this code:

1. `Object.assign`: It combines objects by modifying the target object in place. It takes a target object and one or more source objects, copies the properties from the source objects to the target object, and returns the modified target object.

2. Spread operator (`...`): It creates a new object or array by spreading the properties or elements of one or more source objects or arrays. It does not modify the source objects or arrays. When used with objects, it combines properties into a new object. When used with arrays, it concatenates the arrays.

## Optional Chaining

```javascript
// optional chaining (`?.`) is used to safely access properties or call methods when the preceding object is potentially undefined or null

const person = {
  name: 'John',
  address: {
    city: 'New York',
    zipcode: '10001'
  }
};

// Using optional chaining to access nested properties:
const zipcode = person?.address?.zipcode; // If any part is null or undefined, zipcode will be undefined

console.log(zipcode); // Output: '10001' if all properties exist, otherwise undefined

// Without optional chaining, accessing nested properties could lead to errors:
// const zipcodeWithoutOptionalChaining = person.address.zipcode; // This may throw an error if address is undefined.

// We can also use optional chaining with methods:
const greeting = person?.sayHello?.(); // If sayHello is a function, it will be called; otherwise, greeting will be undefined

console.log(greeting); // Output: Result of the function if it exists, otherwise undefined

// Examples:
const arr = [1,2,3];
arr?.[0]; 

function foo (a,b) { }
foo?.(1,2);

```

Optional chaining (`?.`) helps prevent "TypeError" exceptions when you try to access properties or call methods on potentially undefined or null values. If any part of the chain is undefined or null, the result is automatically set to undefined, making your code safer and more resilient.

## Truthy and Falsy values in JavaScript 

```javascript
// Truthy values (evaluate to true in a boolean context)
const truthyValues = [
  true,                // The boolean value true
  42,                  // A non-zero number
  -42,                 // A non-zero negative number
  3.14,                // A non-zero float
  'Hello',             // A non-empty string
  '0',                 // A string with content, even if it's '0'
  [],                  // An empty array (arrays are objects)
  {},                  // An empty object (object literals are objects)
  function() {},       // A non-empty function (functions are objects)
  new Date(),          // An instance of Date
  Symbol('foo'),       // A Symbol (added in ES6)
  /regex/,             // A non-empty regular expression
  infinity,
  -infinity
];

// Falsy values (evaluate to false in a boolean context)
const falsyValues = [
  false,               // The boolean value false
  0,                   // The number zero
  -0,                  // Negative zero
  0n,                  // BigInt zero
  NaN,                 // Not-a-Number
  '',                  // An empty string
  null,                // The special value null
  undefined,           // The special value undefined
];

// Test truthy values in a loop
console.log("Truthy values:");
for (const value of truthyValues) {
  if (value) {
    console.log(value);
  }
}

// Test falsy values in a loop
console.log("\nFalsy values:");
for (const value of falsyValues) {
  if (!value) {
    console.log(value);
  }
}
```

### Nullish coalescing operator
The nullish coalescing operator (`??`) is used to address a specific issue related to falsy values, specifically `null` and `undefined`.

The important difference between them is that:

- `||` returns the first _truthy_ value.
- `??` returns the first _defined_ value.

```js
let height = 0;

alert(height || 100); // 100
alert(height ?? 100); // 0
```
## OOPs


```javascript
// 1. Class: A blueprint for creating objects
class Car {
// 2. Constructor: A special method to initialize object properties
  constructor(make, model) { 
  // Instance variables
    this.make = make;
    this.model = model;
  }
}

// 3. Object: Instances created from a class
const myCar = new Car("Toyota", "Camry");

// 4. Prototype Chaining: Objects inherit properties and methods from their prototype
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
class Car2 {
  constructor(make, model) {
    this._make = make; // Private property
    this._model = model; // Private property
  }

  // Getter method
  get make() {
    return this._make;
  }

  // Setter method
  set make(newMake) {
    this._make = newMake;
  }
}

const myCar = new Car2("Toyota", "Camry");
console.log(myCar.make); // Output: Toyota
myCar.make = "Honda";    // Setter called
console.log(myCar.make); // Output: Honda

```


### Object.getPrototypeOf()

Certainly! `Object.getPrototypeOf()` is a method in JavaScript used to get the prototype (i.e., the internal prototype) of an object. 

```javascript
// Create an object 'person' with a 'name' property
const person = {
  name: 'John'
};

// Create another object 'student' with a 'studentId' property
const student = {
  studentId: '123456'
};

// Set the prototype of 'student' to be 'person', so 'student' inherits properties from 'person'
Object.setPrototypeOf(student, person);

// Retrieve the prototype (internal prototype) of 'student' using 'Object.getPrototypeOf()'
const studentPrototype = Object.getPrototypeOf(student);

// Log the prototype of 'student' to see the inherited properties
console.log(studentPrototype); // Output: { name: 'John' }
```


### Destructuring

Certainly! Destructuring in JavaScript allows you to extract values from objects or arrays into distinct variables. Here's an example with comments:

```javascript
// Example object with properties
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 30,
};

// const firstName = person.firstName
// const lastName = person.lastName
// const age = person.age

// The below code is equivalent to above 3 line
// Destructuring an object
const { firstName, lastName, age:RealAge } = person;


// Given an array 'arr' with three elements: 'foo', 'bar', and 'baz'
const arr = ['foo', 'bar', 'baz'];

// Example 1: Skipping the first two elements and assigning 'c' to the third element
const [,, c] = arr;

// 'c' now contains the value 'baz'
console.log(c); // Output: 'baz'

// Example 2: Assigning 'a' to the first element, 'b' to the second element, and 'c' to the third element
const [a, b, c] = arr;

// 'a' contains 'foo', 'b' contains 'bar', and 'c' contains 'baz'
console.log(a); // Output: 'foo'
console.log(b); // Output: 'bar'
console.log(c); // Output: 'baz'


// Now, firstName, lastName, and age hold the corresponding values
console.log(firstName); // Output: "John"
console.log(lastName);  // Output: "Doe"
console.log(age);       // Output: 30
```

In this code:

1. We have an object called `person` with properties `firstName`, `lastName`, and `age`.
2. We use destructuring to create new variables (`firstName`, `lastName`, and `age`) with the same names as the object's properties.
3. As a result, we can access these values directly using the new variables.

## Data Structure 

```js
// 1. Arrays: Ordered list of values, indexed by number.
const myArray = [1, 2, 3, 4, 5];

// 2. Objects: Unordered collection of key-value pairs.
const myObject = { name: 'John', age: 30 };

// 3. Strings: Sequence of characters.
const myString = 'Hello, World!';

// 4. Numbers: Numeric data type.
const myNumber = 42;

// 5. Booleans: Represents true or false values.
const isTrue = true;

// 6. Undefined: Represents the absence of a value or uninitialized variable.
let undefinedValue;

// 7. Null: Represents an intentional absence of any object or value.
const nullValue = null;

// 8. Maps: Collection of key-value pairs with unique keys.
const myMap = new Map();
myMap.set('key1', 'value1');
myMap.set('key2', 'value2');

// 9. Sets: Collection of unique values.
const mySet = new Set([1, 2, 3, 4, 5, 5]);

// 10. WeakMaps: Similar to Maps but with weak references, enabling garbage collection.
const myWeakMap = new WeakMap();
const key = {};
myWeakMap.set(key, 'value');

// 11. WeakSets: Similar to Sets but with weak references, enabling garbage collection.
const myWeakSet = new WeakSet();
const weakSetValue = { key: 'value' };
myWeakSet.add(weakSetValue);

// 12. Symbols: Unique and immutable data type, often used as object property keys.
const mySymbol = Symbol('description');

// 13. Promises: Represents a value that might not be available yet but will be in the future.
const myPromise = new Promise((resolve, reject) => {
  // Asynchronous operation
  if (/* condition */) {
    resolve('Success');
  } else {
    reject('Error');
  }
});

// 14. Functions: Reusable blocks of code.
function myFunction(param1, param2) {
  return param1 + param2;
}

// 15. Garbage Collected Data Structures:
//    - Arrays, Objects, Strings, Numbers, Booleans, Maps, Sets, WeakMaps, WeakSets, and Symbols are garbage collected.
//    - Garbage collection is automatic and managed by the JavaScript engine.

```

In addition to the commonly used data structures mentioned earlier, JavaScript also provides some specialized data structures and libraries that you can use:

1. **Typed Arrays**: Typed arrays provide a way to work with binary data directly and efficiently. They include types like `Int8Array`, `Uint8Array`, `Float32Array`, and more for handling specific data formats.

```javascript
const intArray = new Int8Array([1, 2, 3, 4, 5]);
```

2. **Date**: The `Date` object is used for working with dates and times.

```javascript
const currentDate = new Date();
```

3. **RegExp**: The `RegExp` object is used for working with regular expressions, which are powerful for pattern matching in strings.

```javascript
const regex = /pattern/;
```

4. **JSON**: Although not a native JavaScript data structure, JSON (JavaScript Object Notation) is used for data interchange and can be converted to/from JavaScript objects using `JSON.parse()` and `JSON.stringify()`.

```javascript
const jsonData = '{"name": "John", "age": 30}';
const parsedData = JSON.parse(jsonData);
```

5. **Queue and Stack Implementations**: JavaScript doesn't have built-in queue and stack data structures, but you can implement them using arrays or linked lists.

```javascript
// Queue implementation using an array
const queue = [];
queue.push(1);
queue.push(2);
const front = queue.shift();

// Stack implementation using an array
const stack = [];
stack.push(1);
stack.push(2);
const top = stack.pop();
```

6. **Doubly Linked Lists**: You can implement linked lists for more advanced data structures like doubly linked lists when needed.

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
    this.prev = null;
  }
}

class DoublyLinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
  }

  // Implement methods for adding, removing, and manipulating nodes.
}
```

7. **BigInt**: JavaScript introduced BigInts for handling arbitrarily large integers.

```javascript
const bigNumber = BigInt("1234567890123456789012345678901234567890");
```

8. **WeakRef**: JavaScript introduced `WeakRef` for creating weak references to objects, which can be useful for implementing cache or resource management.

```javascript
const weakRef = new WeakRef(someObject);
```


## Sync  
**Synchronous:**
In synchronous code, statements are executed one after the other in a sequential order, blocking the execution until each statement completes.

```javascript
console.log("Step 1");
console.log("Step 2");
console.log("Step 3");
```

**Asynchronous:**
In asynchronous code, some operations are non-blocking, allowing other code to run while waiting for an operation to complete. Common asynchronous operations include timers and network requests.

```javascript
console.log("Step 1");

setTimeout(() => {
  console.log("Step 2 (after 1 second)");
}, 1000);

console.log("Step 3");
```

**Callback Function:**
A callback function is a function passed as an argument to another function. It's executed after the completion of an asynchronous operation or at a specified time.

```javascript
function doSomethingAsync(callback) {
  setTimeout(() => {
    console.log("Async operation completed");
    callback();
  }, 1000);
}

console.log("Step 1");

doSomethingAsync(() => {
  console.log("Step 2 (after async operation)");
});

console.log("Step 3");
```

**Callback Hell (Callback Pyramid):**
Callback hell occurs when you nest multiple callback functions inside each other, making the code hard to read and maintain. This is common in deeply nested asynchronous code.

```javascript
asyncFunc1(() => {
  asyncFunc2(() => {
    asyncFunc3(() => {
      // More nested callbacks...
    });
  });
});
```

To avoid callback hell, you can use techniques like Promises, async/await, or libraries like async.js. These techniques provide better readability and maintainability for asynchronous code.

## Promise

Sure! Here's a concise explanation of Promise, resolve, reject, then/catch, async function, await, and try/catch in JavaScript with code and comments:

```javascript
// 1. Promise: A representation of a potential future value or error.
const myPromise = new Promise((resolve, reject) => {
  // Simulating an asynchronous operation
  const success = true;

  if (success) {
    resolve('Operation successful');
  } else {
    reject('Operation failed');
  }
});

// 2. Resolve and Reject: Functions to fulfill (resolve) or reject a Promise.
myPromise
  .then((message) => {
    console.log('Success:', message);  // Executes when the Promise is resolved
  })
  .catch((errorMessage) => {
    console.error('Error:', errorMessage);  // Executes when the Promise is rejected
  });

// 3. Async Function: A function that returns a Promise implicitly.
async function myAsyncFunction() {
  try {
    const result = await myPromise;  // Await resolves the Promise or throws an error
    console.log('Async result:', result);
  } catch (error) {
    console.error('Async error:', error);
  }
}

// 4. Await: Pauses the async function until a Promise is settled (resolved or rejected).
myAsyncFunction();

// 5. Try/Catch: Used to handle exceptions (errors) in a block of code.
try {
  // Code that may throw an error
  throw new Error('Something went wrong');
} catch (error) {
  console.error('Error caught:', error.message);  // Handle the error
}
```

In this code:
- A Promise is created with a simulated asynchronous operation.
- `then` and `catch` are used to handle the resolved and rejected cases of the Promise.
- `async` function and `await` are used to work with Promises in a more synchronous-like manner.
- `try` and `catch` are used to catch and handle errors that may occur in a block of code.

## Export / Import

```js
// In a module file named "myModule.js":

// Default Export:
const defaultExport = 'I am the default export';

// Named Export:
export const namedExport1 = 'I am a named export 1';
export const namedExport2 = 'I am a named export 2';

// In another JavaScript file:

// Import Default Export:
import defaultExportValue from './myModule.js';
console.log(defaultExportValue); // Outputs: 'I am the default export'

// Import Named Exports:
import { namedExport1, namedExport2 } from './myModule.js';
console.log(namedExport1); // Outputs: 'I am a named export 1'
console.log(namedExport2); // Outputs: 'I am a named export 2'

```

## npm , package.json

Certainly, here's a concise explanation of `npm` and `package.json` in JavaScript, along with code and comments:

1. **npm (Node Package Manager):**
   - `npm` is the package manager for Node.js, used to install, manage, and share JavaScript libraries and tools.
   - It provides a command-line interface to interact with packages and dependencies.

```bash
# Example npm commands:
npm install package-name  # Install a package locally.
npm install -g package-name  # Install a package globally.
npm init  # Create a package.json file for your project.
npm install  # Install dependencies listed in package.json.
npm publish  # Publish your own package to the npm registry.
```

2. **package.json:**
   - `package.json` is a JSON (JavaScript Object Notation) file that contains metadata about a Node.js project, including its dependencies, scripts, and configuration.
   - It's used to document and automate project setup and management.

```json
{
  "name": "my-node-project",
  "version": "1.0.0",
  "description": "A concise description of your project",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",  // Define custom scripts for your project.
    "test": "mocha"
  },
  "dependencies": {
    "express": "^4.17.1",  // Define project dependencies and their versions.
    "axios": "^0.21.4"
  },
  "devDependencies": {
    "mocha": "^9.1.0"  // Define development-only dependencies.
  },
  "author": "Your Name",
  "license": "MIT"
}
```

With `npm` and `package.json`, you can easily manage project dependencies, execute scripts, and share your JavaScript code with others, making it an essential part of modern JavaScript development.

## DOM

Certainly! Below, I'll provide JavaScript code examples with inline comments for each of the deeply explained topics related to the DOM:

1. **Introduction to DOM:**

   ```javascript
   // The DOM represents the structure of an HTML document.
   // It's a hierarchical tree-like structure where each element is a node.
   // Accessing the root of the DOM (the entire HTML document):
   const wholeDocument = document;
   ```

2. **DOM Elements:**

   ```javascript
   // Accessing elements using getElementById (by ID):
   const elementById = document.getElementById('myElementId');
   
   // Accessing elements using querySelector (by CSS selector):
   const elementBySelector = document.querySelector('.myClass');
   
   // Accessing multiple elements using querySelectorAll (returns a NodeList):
   const elementsBySelector = document.querySelectorAll('.myClass');
   ```

3. **DOM Manipulation:**

   ```javascript
   // Modifying element properties:
   const element = document.getElementById('myElementId');
   element.innerHTML = '<p>New content</p>';
   element.textContent = 'Text content';
   element.setAttribute('data-custom', 'value');
   element.style.color = 'red';
   
   // Creating and adding new elements:
   const newElement = document.createElement('div');
   element.appendChild(newElement);
   
   // Removing and replacing elements:
   const parent = document.getElementById('parentElement');
   const oldChild = document.getElementById('childElement');
   parent.removeChild(oldChild);
   ```

4. **Traversing the DOM:**

   ```javascript
   // Navigating between elements:
   const childNode = document.getElementById('childElement');
   const parent = childNode.parentNode;
   const nextSibling = childNode.nextSibling;
   const prevSibling = childNode.previousSibling;
   ```

5. **Events and Event Handling:**

   ```javascript
   // Adding an event listener:
   const button = document.getElementById('myButton');
   button.addEventListener('click', function(event) {
     alert('Button clicked!');
   });
   ```

6. **Event Bubbling and Event Delegation:**

   ```javascript
   // Using event delegation (handling events on parent):
   const parentElement = document.getElementById('parentElement');
   parentElement.addEventListener('click', function(event) {
     if (event.target.tagName === 'LI') {
       alert(`You clicked on list item: ${event.target.textContent}`);
     }
   });
   ```

7. **Forms and Form Elements:**

   ```javascript
   // Form submission and validation:
   const form = document.getElementById('myForm');
   form.addEventListener('submit', function(event) {
     event.preventDefault(); // Prevents the default form submission
     const inputValue = document.getElementById('inputField').value;
     // Validate and process input value
   });
   ```

8. **DOM Style and CSS Manipulation:**

   ```javascript
   // Modifying element styles:
   const element = document.getElementById('myElement');
   element.style.backgroundColor = 'blue';
   element.classList.add('highlight');
   element.classList.remove('highlight');
   ```

9. **Attributes and Data Attributes:**

   ```javascript
   // Accessing and manipulating attributes:
   const element = document.getElementById('myElement');
   const attributeValue = element.getAttribute('data-custom');
   element.setAttribute('data-custom', 'new-value');
   ```


10. **DOM Rendering and Layout:**

   ```javascript
   // Understanding layout and rendering:
   const element = document.getElementById('myElement');
   element.style.width = '100px'; // Changes element width
   element.style.height = '50px'; // Changes element height
   ```

11. **Asynchronous DOM Manipulation:**

   ```javascript
   // Using setTimeout for asynchronous manipulation:
   setTimeout(function() {
     const element = document.getElementById('myElement');
     element.textContent = 'Delayed update!';
   }, 1000); // Updates after 1 second
   ```

12. **Local and Session Storage:**

   ```javascript
   // Storing and retrieving data in local storage:
   localStorage.setItem('username', 'John');
   const storedUsername = localStorage.getItem('username');
   ```

13. **Cross-Browser Compatibility:**

   ```javascript
   // Feature detection for cross-browser compatibility:
   if (typeof localStorage !== 'undefined') {
     // localStorage is supported
     localStorage.setItem('key', 'value');
   } else {
     // Handle the lack of localStorage support
   }
   ```

14. **Security Considerations:**

   ```javascript
   // Sanitizing user input (preventing XSS):
   const userInput = '<script>alert("XSS Attack");</script>';
   const sanitizedInput = document.createElement('div');
   sanitizedInput.innerText = userInput;
   ```

15. **DOM APIs and Methods:**

   ```javascript
   // Using DOM methods and properties:
   const body = document.body;
   const allImages = document.images;
   ```

16. **XMLHttpRequest and Fetch API:**

   ```javascript
   // Fetching data from a server and updating the DOM:
   fetch('https://api.example.com/data')
     .then(response => response.json())
     .then(data => {
       const element = document.getElementById('myElement');
       element.textContent = data.message;
     })
     .catch(error => console.error(error));
   ```

17. **DOM Events Lifecycle:**

   ```javascript
   // Understanding event propagation and handling:
   const parentElement = document.getElementById('parentElement');
   parentElement.addEventListener('click', function(event) {
     event.stopPropagation(); // Stops event from bubbling up
     event.preventDefault(); // Prevents the default action
   });
   ```

18. **Working with iframes:**

   ```javascript
   // Manipulating content within an iframe:
   const iframe = document.getElementById('myIframe');
   const iframeDocument = iframe.contentDocument || iframe.contentWindow.document;
   const iframeElement = iframeDocument.getElementById('iframeContent');
   ```

19. **Web APIs and the DOM:**

   ```javascript
   // Integrating with other web APIs (e.g., Geolocation API):
   if ('geolocation' in navigator) {
     navigator.geolocation.getCurrentPosition(function(position) {
       const latitude = position.coords.latitude;
       const longitude = position.coords.longitude;
       // Use the coordinates
     });
   }
   ```

## Imperative Vs declarative

Imperative and declarative are two programming paradigms that describe different approaches to writing code:

1. **Imperative Code:**
   - **How to Do It:** Imperative code focuses on describing step-by-step instructions to achieve a desired outcome.
   - **Example (Imperative):** In JavaScript, a for loop that iterates through an array and performs specific actions on each element is imperative.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const doubledNumbers = [];
   
   for (let i = 0; i < numbers.length; i++) {
     doubledNumbers.push(numbers[i] * 2);
   }
   ```

2. **Declarative Code:**
   - **What to Do:** Declarative code emphasizes expressing the desired outcome without specifying the step-by-step process.
   - **Example (Declarative):** In JavaScript, using the `map` function to transform elements of an array is declarative.

   ```javascript
   const numbers = [1, 2, 3, 4, 5];
   const doubledNumbers = numbers.map(number => number * 2);
   ```

