<!-- .slide: id="lesson7" -->

# Basic Frontend - Fall 2023

Lesson 7, Tuesday, 2023-10-10

---

### Agenda

- Recap: Functions
- Practice with functions

---

### Recap

Name the concepts we have seen so far:

```js
function min(a, b) {
  if (a <= b) {
    return a;
  }
  return b;
}

min(1, 2);
```

Function definition, parameters, return value, function call, function arguments
<!-- .element: class="fragment" -->

---

### Quiz

What do we see on the console?

```js
console.log(42);
let x = 42;
console.log(x);
function y() { return 42; }
console.log(y());
```

42 42 42
<!-- .element: class="fragment" -->

---

### Brain teaser

Using only the `min` function we've seen so far, how can we find the minimum of three numbers?
(Note: In just one line of code. No if statements allowed!)

```js
let smallest = min(1, min(2, 3));
```
<!-- .element: class="fragment" -->

---

### onclick

Most HTML elements have an `onclick` attribute that can be used to execute JavaScript code when the element is clicked.

```html
<button onclick="console.log('I was clicked');">
    Click me!
</button>
```

Writing code inside HTML's `onclick` attribute is tedious. Can you think of something we learned that can help us?

---

Let's call a function inside `onclick`!

HTML:
```html
<button onclick="handleButtonClick()">Click me!</button>
```

JavaScript:
```js
function handleButtonClick() {
  console.log("The button was clicked!");
}
```

---

### Changing the color of a web page

You can use the variable `document.body.style.backgroundColor` to change the background color of the web page.

```js
// changes the background color to red
document.body.style.backgroundColor = "red";
```

---

### Task 1

Let's create a webpage with three buttons, "red", "green", "blue".

When you press the button, set `document.body.style.backgroundColor` to that color.

BONUS:

* When the color is already set to that color, set it back to empty string.
* Solve the task with only one single `function` and one single `if/else` statement.

---

### Task 2

Let's create a webpage with one button. When you click the button, it should count how many times you clicked it and log that number to the console.

Example: If you click the button 3 times, the console should show `You clicked 3 times`.

---

### Bonus: Task 3

Let's play rock-paper-scissors! `Math.random()` is a function that returns a random number between 0 and 1. It's built into JavaScript. Copy/paste the function `randomMove` to your code. Create three buttons, "rock", "paper", "scissors". When you click one of the buttons, call `randomMove()` to get a random move. Then compare the two moves and set
the page background color to green if you won, red if you lost, and yellow if it's a tie.

```js
function randomMove() {
  let randomNumber = Math.random();
  if (randomNumber < 0.33) {
    return "rock";
  } else if (randomNumber < 0.66) {
    return "paper";
  } else {
    return "scissors";
  }
}
```

<!-- .slide: style="font-size:80%" -->

---

### Bonus Bonus Task 3

Write to console how many times you won, lost, and tied.

---

### Solution Task 1

HTML:

```html
<button onclick="setColor('red')">red</button>
<button onclick="setColor('green')">green</button>
<button onclick="setColor('blue')">blue</button>
```

JavaScript:

```js
function setColor(color) {
  if (document.body.style.backgroundColor === color) {
    document.body.style.backgroundColor = "";
  } else {
    document.body.style.backgroundColor = color;
  }
}
```

---

### Solution Task 2

HTML:

```html
<button onclick="count()">Click me!</button>
```

JavaScript:

```js
let clickCount = 0;
function count() {
  clickCount += 1;
  console.log("You clicked " + clickCount + " times");
}
```
