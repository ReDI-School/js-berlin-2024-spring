<!-- .slide: id="lesson6" -->

# Basic Frontend - Spring 2024

Lesson 6, Tuesday, 2024-04-04


---


### Recap

What are variables?

---

### Recap: Data

Which data types have we seen so far?

---

### Recap: Data

| Data Type | Example      | Operators                |
| --------- | ------------ | ------------------------ |
| number    | `-0.5`, `42` | `+`, `-`, `*`, `/`, `**` |
| boolean   | `true`       | `&&`, `!`, `\|\|`        |
| string    | `"hello"`    | `+`                      |
| null      | `null`       | `===` `!==`              |
| undefined | `undefined`  | `===` `!==`              |

---

### Recap: Statements

Which statements have we seen so far?

---

```js
if (condition){

} else if (anotherCondition) {

} else {

}
```

---

# Functions

<!-- .slide: id="functions" -->

---

### functions

A function is a reusable block of code:

```js
function sayHello() {
  document.body.textContent = "Hello There!";
}
```


---

### Function definition

There are 3 mandatory parts in a function definition:

1. the `function` keyword
1. the name of the function we are defining, followed by parentheses `()`
1. the function body, surrounded by curly braces


---

The code in the function will only execute when we _call_ the function.
We can call the function like this, using a pair of open and closed parentheses:

```js
sayHello();
```

---

### Function definition and execution

It's important to distinguish between 2 parts when working with functions:

1. function definition (also called function declaration)
1. function execution (calling the function)

---

### Function definition and execution

```js
// this is the function definition.
function sayHello() {
  document.body.textContent = "Hello There!";
}

// this is the function call (execution)
sayHello();
```

We always need to define a function in order to call it.

---

### Function execution

To call (execute) a function we need to write its `name` followed by parenthesis.

---

you can write any amount of code you want in the function:

```js
function sayHello() {
  document.body.textContent = "Hello There";

  document.body.textContent += "... ";

  document.body.textContent += "General Kenobi!";
}

sayHello();
```

---

A function can contain any kind of code:

```js
function checkTemperature() {
  let temperature = 10;
  if (temperature < 0) {
    document.body.textContent = "it's cold outside";
  } else {
    document.body.textContent = "it's not that cold";
  }
}

checkTemperature();
```

---

### Quiz

What's in `textContent` after the following code runs:

```js
function output42() {
  document.body.textContent = "42";
}
```

Answer: Nothing, because we never _call_ the function
<!-- .element: class="fragment" -->

---

### Quiz

What's in `textContent` after the following code runs:

```js
function output42() {
  document.body.textContent += "42";
}

output42();
output42();
```

Answer: "4242"
<!-- .element: class="fragment" -->

---

### Quiz

Where does the "Hey!" appear in your console?

```js
console.log('I go first');

function sayHey() {
    console.log('Hey!');
}

console.log('I go second');
sayHey();
console.log('I go last');
```

Answer: between "I go second" and "I go last"
<!-- .element: class="fragment" -->


---

### Task 1

Write a function that writes your name to the `textContent` of the HTML document's body.
Call the function. What do you see on your web page?

---

## Function parameters and arguments

We have a function that says "Hi Owen", another one that says "Hi Mellina" and a last one that says "Hi Sevtap".

How can we do it without repeating ourselves?

---

### Function parameters and arguments

```js
function sayHiToOwen() {
  console.log('Hi Owen');
}
function sayHiToMellina() {
  console.log('Hi Mellina');
}
function sayHiToSevtap() {
  console.log('Hi Sevtap');
}

sayHiToOwen();
sayHiToMellina();
sayHiToSevtap();
```

---

### Function parameters and arguments

The code works, but we are basically writing the same function 3 times and just changing a string inside.

We want to avoid rewriting nearly identical code.

Functions have the option to accept **parameters** that let us do just that.

---

### Function parameters and arguments

```js
function sayHi(name) {
  console.log("Hi " + name);
}

sayHi('Owen');
sayHi('Mellina');
sayHi('Sevtap');
```

- `name` is a function **parameter**
- "Owen", "Mellina", "Sevtap" are **arguments**. In each function call they will be assigned to the `name` parameter

---

### Multiple parameters

A function can have any number of parameters

```js
function introduce(parameter1, parameter2, parameter3) {
    console.log(parameter1, parameter2, parameter3);
}

introduce("argument1", "argument2", "argument3");
```

Each argument will be assigned to the corresponding parameter in order, from left to right

---

### Multiple parameters

```js
function greetFriend(greeting, name) {
  console.log(greeting + " " + name + ", how are you today?");
}

greetFriend("Olá", "Mellina");
greetFriend("Merhaba", "Sevtap");
```

---

## Returning values

Typically, we use functions to make a calculation. We want to use the result of that calculation outside of the function.

We can use the `return` keyword for that.

---

### Return: example

```js
function giveMe5() {
  return 5;
}

let number = giveMe5();
// number is 5
```

---

### Quiz

What is the value of the variable `result`?

```js
function add(a, b) {
  return a + b;
}

let result = add(3, 5);
```

Result is 8
<!-- .element: class="fragment" -->

---

### Returning values

The `return` keyword exits the function immediately. Any code after the `return` statement will not be executed.

```js
function describeWeather(temperature) {
  if (temperature > 25) {
    return "It's hot";
    // no further code will be executed
  }
  if (temperature < 5) {
    return "It's cold";
    // no further code will be executed
  }
  return "It's nice outside";
  console.log("function finished"); // this will never be reached
}
```

---

### Common mistakes

What is the value of the variable `number`?

```js
function giveMe5() {
  console.log("5");
}

let number = giveMe5();
console.log(number); // ???
```

`undefined`! This function does not have a return value!
<!-- .element: class="fragment" -->

---

### Quiz

What is the value of `result`?

```js
function giveMe5() {
  return 5;
}

let result = giveMe5() * giveMe5();
```

Answer: 25
<!-- .element: class="fragment" -->


---

### Task 2

Write a `min` function that returns the smaller of the two numbers. If the 2 values are the same, it will return the first value.

```js
min(1, 2);    // should return 1
min(100, 99); // should return 99
min(-10, 0);  // should return -10
```

---

### Task 3

Write a function that takes name of a person, their age, and the language they speak, and returns a string that introduces this person.

Example:

Owen, 30, English &#8594; **"Hello! my name is Owen, I am 30 years old and I speak English."**

---

### Bonus Tasks

[Here are some incomplete examples](https://github.com/ReDI-School/js-berlin-2021-fall/tree/main/exercises/2021-10-07)
of using functions. Copy the contents of the file into a script tag, and try
to fix the examples so that they run correctly.

---

### Bonus Bonus Tasks

Want to practice more? Try solving the tasks in [index.html](https://github.com/ReDI-School/js-berlin-2023-fall/tree/main/functions)
