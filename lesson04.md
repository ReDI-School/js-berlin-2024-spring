<!-- .slide: id="lesson4" -->

# Basic Frontend - Spring 2024

Lesson 4, Tuesday, 2024-03-26

---

### Recap

Name the operators:

```js
&&
<
===
||
+
**
>=
```

---

### Recap

Name the operators:

```js
&&    // logical AND
<     // less than
===   // strict equality
||    // logical OR
+     // addition
**    // exponentiation
>=    // greater than or equal
```

---

# Recap

| Group                | Operators                          | Example                                              |
| -------------------- | ---------------------------------- | ---------------------------------------------------- |
| Numerical Operators  | `+` `-` `*` `/` `**`               | `5 + 4 * 3`<br/>`7 / 2 - 2`<br/>`"Hello" + " World"` |
| Comparison Operators | `===` `!==` `<` `>` `<=` `>=`      | `30 !== 25`<br/>`20 >= 18`                           |
| Logical Operators    | <code>&#124;&#124;</code> `&&` `!` | `true && !false`                                     |

---

<!-- .slide: id="if" -->

# Conditional Statements

---

### Conditional Statements

Up until now, we wrote code line by line.

But what if I want to run some code only if a certain condition is true or false? For example, only run code when the user is logged in?

![if](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals/cookie-choice-small.png)<!-- .element height="200px" style="position: fixed; left: 30%" -->

---

### If statement

```js
if (condition) {
  // block of code that
  // will run ONLY if
  // condition is true
}
```

---

### If statements

```js
if (condition) {
  // your code here
}
```

- `condition` must be a boolean
- The code in the block is executed only if the boolean is `true`
- If the boolean is `false`, the code block is _not_ executed

---

### if Statements - Examples

```js
if (food === "pizza") {
  document.body.textContent = "My favorite food is pizza!";
}
```

```js
if (temperature > 20) {
  document.body.textContent = "Yay, it's warm again!";
}
```

```js
if (canSpeakFrench) {
  // same as: canSpeakFrench === true
  document.body.textContent = "Bonjour!";
}
```

---

### if statements - quiz

What does the code below show on the HTML page?

```js
let language = "German";
if (language === "German") {
  document.body.textContent = "Guten Tag";
}
if (language === "French") {
  document.body.textContent = "Bonjour";
}
```

`"Guten Tag"`

<!-- .element: class="fragment" -->

---

### if statements - quiz

What does the code below show on the HTML page?

```js
let language = "Spanish";
if (language === "German") {
  document.body.textContent = "Guten Tag";
}
if (language === "French") {
  document.body.textContent = "Bonjour";
}
if (language !== "German" && language !== "French") {
  document.body.textContent = "Good day";
}
```

`"Good day"`

<!-- .element: class="fragment" -->

---

### Code Blocks: {}

Code blocks contain the code between `{` and `}`, and should be indented for better readability:

```js
if (language === "German") {
  // In VSCode, you can indent code by pressing the "Tab" key,
  // or right-click and choose "Format Document"
  document.body.textContent = "Guten Tag";
}
```

---

### Code Blocks: {}

All variables defined in code blocks only exist inside the block (technical term: “block scope”)

```js
let name = "John Doe";
if (name === "John Doe") {
  let greeting = "Hi dude";
}
if (name === "Mary Doyle") {
  let greeting = "Hello my dear";
}
document.body.textContent = greeting; // ERROR!
```

---

### Code Blocks: {}

Correct solution:

```js
let name = "John Doe";
let greeting;
if (name === "John Doe") {
  greeting = "Hi dude";
}
if (name === "Mary Doyle") {
  greeting = "Hello my dear";
}
document.body.textContent = greeting; // "Hi dude"
```

---

### Quiz

What does the code below show on the HTML page?

```js
let food = "broccoli";
if (food === "pizza") {
  document.body.textContent = "yum yum";
}
```

Solution: Nothing, since the condition in the `if` is `false`

<!-- .element: class="fragment" -->

---

### Quiz

What does it output?

```js
let age = 42;
if (age >= 18) {
  document.body.textContent = "you are allowed to drive a car";
}
if (age < 18) {
  document.body.textContent = "you are not allowed to drive a car";
}
```

Solution: First condition is `true`, so it outputs "you are allowed to drive a car"

<!-- .element: class="fragment" -->

---

# Task

Define a variable `hour` and set it to `17`. Make an `if` statement that outputs `good day` to the body of your page, if `hour` is less than 18.

Now change `hour` to `19` and run the code again. What changed?

---

# Task

Harald invented a game where the player with the highest score wins. The score is the player's shoe size plus five multiplied by the number of times you ate pizza in the last month.

1. Create variables for the shoe size and number of pizza eaten for you and a person next to you
1. Calculate the scores for you and your neighbor
1. Decide who wins, output the winner and their score to the `body` of your HTML. Remember: there can be a draw (both players with the same score).

---
