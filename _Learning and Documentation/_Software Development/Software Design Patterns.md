
**Design patterns** are reusable solutions to common software design problems. 

They provide a way to structure code that promotes - reusability, maintainability, and scalability.

**Creational Patterns**:

- **Factory Method**: Creates objects without specifying the exact class to create.

```js
class Product {
    constructor(name) {
        this.name = name;
    }
}

class ProductFactory {
    createProduct(name) {
        return new Product(name);
    }
}

const factory = new ProductFactory();
const product = factory.createProduct("New Product");

```

**Singleton**: Ensures that a class has only one instance and provides a global point of access to it.

```js
class Singleton {
    constructor() {
        if (!Singleton.instance) {
            Singleton.instance = this;
        }
        return Singleton.instance;
    }
}

const instance1 = new Singleton();
const instance2 = new Singleton();
console.log(instance1 === instance2); // Output: true

```

**Structural Patterns**:

- **Decorator**: Adds new functionality to an object dynamically without altering its structure.
```js
class Coffee {
    cost() {
        return 5;
    }
}

class MilkDecorator {
    constructor(coffee) {
        this.coffee = coffee;
    }

    cost() {
        return this.coffee.cost() + 2;
    }
}

const coffeeWithMilk = new MilkDecorator(new Coffee());
console.log(coffeeWithMilk.cost()); // Output: 7

```

**Behavioral Patterns**:

- **Observer**: Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

```js
class Subject {
    constructor() {
        this.observers = [];
    }

    addObserver(observer) {
        this.observers.push(observer);
    }

    notifyAll() {
        this.observers.forEach(observer => observer.update());
    }
}

class Observer {
    update() {
        console.log("Observer updated");
    }
}

const subject = new Subject();
const observer1 = new Observer();
const observer2 = new Observer();

subject.addObserver(observer1);
subject.addObserver(observer2);

subject.notifyAll(); // Output: "Observer updated", "Observer updated"

```


[PDF on Design Patterns](https://www.cs.rpi.edu/academics/courses/spring21/csci2600/handout-files/files_15_04/DesignPatterns.pdf) 

Created: March 7th 2024
Related: [[Software Development Overview]], [[Programming Paradigms]], #algorithm_design #design_patterns #quickread 
