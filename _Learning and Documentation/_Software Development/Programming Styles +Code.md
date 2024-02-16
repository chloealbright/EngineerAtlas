
Here are some major programming paradigms:

1. **Imperative Programming:**
    
    - **Definition:** Imperative programming focuses on describing how a program operates and changes the program state.
    - **Example:** Procedural programming languages like C, Pascal.
    
**Example**
```js
// Example of imperative programming
function sumOfArray(arr) {
    let sum = 0;
    for (let i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    return sum;
}

console.log(sumOfArray([1, 2, 3, 4, 5])); // Output: 15

```

1. **Declarative Programming:**
    
    - **Definition:** Declarative programming focuses on describing what a program should accomplish without specifying how to achieve it.
    - **Example:** SQL (Structured Query Language) for database queries.

**Example**
```js
// Example of declarative programming using array.reduce()
function sumOfArray(arr) {
    return arr.reduce((sum, num) => sum + num, 0);
}

console.log(sumOfArray([1, 2, 3, 4, 5])); // Output: 15

```

1. **Object-Oriented Programming (OOP):**
    
    - **Definition:** OOP is centered around the concept of "objects" that encapsulate data and behavior.
    - **Example:** Java, Python, C++.
    
**Example**
```js
// Example of object-oriented programming using classes
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        console.log(this.name + ' makes a noise.');
    }
}

class Dog extends Animal {
    speak() {
        console.log(this.name + ' barks.');
    }
}

const dog = new Dog('Buddy');
dog.speak(); // Output: Buddy barks.

```

1. **Functional Programming:**
    
    - **Definition:** Functional programming emphasizes the use of functions as first-class citizens and avoids changing state and mutable data.
    - **Example:** Haskell, Lisp, Scala.

**Example**
```js
// Example of functional programming using higher-order functions
function sumOfArray(arr) {
    return arr.reduce((sum, num) => sum + num, 0);
}

console.log(sumOfArray([1, 2, 3, 4, 5])); // Output: 15

```

1. **Event-Driven Programming:**
    
    - **Definition:** Event-driven programming is based on the occurrence of events, and the program responds to these events.
    - **Example:** GUI programming, JavaScript in web development.

**Example**
```js
// Example of event-driven programming using event listeners
document.getElementById('myButton').addEventListener('click', function() {
    console.log('Button clicked');
});

```

1. **Logic Programming:**
    
    - **Definition:** Logic programming is based on formal logic and involves expressing program logic as a set of statements in logical form.
    - **Example:** Prolog.

**Example**
```js
// Example of logic programming using Prolog.js library
const prolog = require('prolog');

prolog(`
    parent(john, doe).
    parent(jane, doe).
    ancestor(X, Y) :- parent(X, Y).
`);

prolog.query('ancestor(X, doe).', result => console.log(result));

```

1. **Parallel Programming:**
    
    - **Definition:** Parallel programming involves the simultaneous execution of tasks to improve performance.
    - **Example:** CUDA for parallel computing on GPUs.

**Example**
```js
// Example of parallel programming using Web Workers
const worker = new Worker('worker.js');
worker.postMessage('Hello from main thread!');

worker.onmessage = function(event) {
    console.log('Message from worker:', event.data);
};

```

1. **Scripting Languages:**
    
    - **Definition:** Scripting languages are often used for automation and are interpreted rather than compiled.
    - **Example:** Python, Ruby, Bash.

**Example**
```js
// Example of scripting using Node.js
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
    if (err) {
        console.error(err);
        return;
    }
    console.log(data);
});

```

1. **Aspect-Oriented Programming (AOP):**
    
    - **Definition:** AOP aims to modularize cross-cutting concerns, such as logging and security, that affect multiple parts of a program.
    - **Example:** AspectJ.

**Example**
```js
// Example of aspect-oriented programming using AspectJS
const aspect = require('aspectjs');

aspect.before('loggingAspect', function() {
    console.log('Logging before method execution');
});

function myFunction() {
    console.log('Executing main function');
}

aspect.after('loggingAspect', function() {
    console.log('Logging after method execution');
});

myFunction(); // Output: Logging before method execution, Executing main function, Logging after method execution

```

1. **Concurrent Programming:**
    
    - **Definition:** Concurrent programming involves the execution of multiple tasks concurrently, often used in systems with multiple processors or cores.
    - **Example:** Java concurrency, Go.
**Example**
```js
// Example of concurrent programming using Web Workers
// main.js
const worker = new Worker('worker.js');
worker.postMessage('Hello from main thread!');

worker.onmessage = function(event) {
    console.log('Message from worker:', event.data);
};

// worker.js
onmessage = function(event) {
    console.log('Message received in worker:', event.data);
    postMessage('Hello from worker thread!');
};

```

These paradigms are not mutually exclusive, and many programming languages support multiple paradigms. Programmers often choose the paradigm that best fits the requirements of the specific problem they are trying to solve.

Related: #deepdive #javascript 