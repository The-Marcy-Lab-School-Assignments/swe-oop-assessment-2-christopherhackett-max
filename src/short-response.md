# Section 2 — Short Response

Write your responses directly in this file. Follow markdown formatting guidelines. Check the rubric.md file to see how your short responses will be graded. 

As a quick guide, check the following before submitting:
- [] Answered all parts of every question
- [] No typos or grammar mistakes (use grammarly!)
- [] Accurately uses relevant technical terminology
- [] Uses markdown to enhance readability (preview in VS Code with Command/Control + Shift + V)
- [] Responses are concise and easy to comprehend

---

## Question 1

In your own words, explain what does _encapsulation_ refer to? Why is this concept beneficial when programming? 

Provide a code snippet to illustrate _encapsulation_.

## Response 1

**Encapsulation** is the grouping of data and methods that handle that data into one object. **Encapsulation** is useful when needing to seperate different features or the functionality of your project.

```js
class MenuList {
  #menu;
  constructor() {
    this.#menu = []
  }
  addItem(name, price) {
    const newItem = {name, price}
    this.#menu.push(newItem)
  }
  removeItem(name, amount) {
    this.#menu.forEach((item) => callback)
  }
  viewList() {
    return [...this.#menu]
  }
}

//different file

class Staff {
  constructor(name, role) {
    this.name = name
    this.role = role
  }
  CompleteTask(task) {
    console.log(`${this.name} has completed ${task}!`)
  }
  onBreak() {
    console.log(`${this.name} is on break!`)
  }
}
```
``MenuList``, ``Staff``, and their **properites/methods** are completely separated. This makes your code easier to read, debug, and test.

## Question 2

Explain what the `this` keyword is. Why is the `this` keyword useful?

In the code snippet below, what does `this` refer to?

```js
class Counter {
	constructor() {
		this.count = 0;
	}
  increment() {
    this.count++;
  }
}

const counterA = new Counter();
const counterB = new Counter();

counterA.increment();
counterA.increment();
counterA.increment();

counterB.increment();

console.log(counterA.count);
console.log(counterB.count);
```

## Response 2

The ``this`` keyword refers to the **object** that ``this`` is being invoked on. ``this`` is useful because it gives **functions** and **methods** the ability to access the **properties** and methods of the object that ``this`` refers to. In this snippet, ``this`` refers to the count property of the ``Counter`` class.

## Question 3

In your own words, explain what **polymorphism** means in OOP. Provide an example in code that demonstrates polymorphism.

## Response 3

**Polymorphism** is when different objects can be handled the same because they have the same method names.

```js
class Dog {
  constructor(name, breed, age
    this.name = name,
    this.breed = breed,
    this.age = age,
  );
  speak() {
    console.log('woof!')
  }
}

class Cat {
  constructor(name, breed, age) {
    this.name = name
    this.breed = breed
    this.age = age
  }
  speak() {
    console.log('meow!')
  }
}
```

``speak()`` can be invoked on instances of both ``Cat`` and ``Dog``, even though they are different classes, and the method for each returns something different, because ``speak()`` has the same name for both classes.
## Question 4

You're building a game where players can raise different digital pets: Cats, Dogs, and Birds. All pets have have a `name`, `energy` level, and `happiness` level and can all `sleep`. Cats have the ability to `hunt`, dogs have the ability to `chase`, and birds have the ability to `fly`.

**Part A:** Describe in words how you would use inheritance to organize these classes.

**Part B:** Explain one advantage of using inheritance here instead of creating three completely separate classes.

## Response 4

### Part A:
First, I would create a ``Pet`` class with **properties** for ``name``, ``energy``, and ``happiness``, and a **method** for ``sleep``. Cats, Dogs, and Birds would then be **subclasses** of Pet, **inheriting** those properties and the sleep method. Cats would then have a ``hunt`` method, Dogs would have a ``chase`` method, and birds would have a ``fly`` method.

### Part B:

One advantage of using inheritance in this situation is **code reusability**. Cats, Dogs, and Birds inherit all their properties and the sleep method from the Pet class. Reusing that code saves you from having to write it repeatedly. As well as keeping your code clean.