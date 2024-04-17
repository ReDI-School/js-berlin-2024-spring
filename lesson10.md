<!-- .slide: id="lesson10" -->

# Basic Frontend - Spring 2024

Lesson 10, Thursday, 2024-04-18

---

### Recap: getElementById

* What is `getElementById`?
* When do we use it?
* What does it return?
* How do we find out which properties we can set/get?

---

### MAJOR TWIST

`string`, `boolean`, `number`, `undefined` and `null` are primitive data types

`object` is a non-primitive data type


However - even primitive data types can have properties in JavaScript. <!-- .element: class="fragment" -->

---

### Example

```js
let greeting = "Hello";
let price = 1/3;

greeting.replace('e', 'a'); // returns "Hallo"
price.toFixed(2)            // returns "0.33"
```

We can use the `toFixed()` method on numbers to round to get a string with fewer digits after the decimal point.

---

# Project

---

### Option 1

Let's write a number guessing game! Let the computer guess a secret number between 1 and 100:

```js
let secretNumber = Math.floor(Math.random() * 100) + 1;
```

Create a game web page where your user can guess any number between 1 and 100. The game must tell the user whether they guessed too high or too low. Once the user guesses the secret number, the game is over.

BONUS: Also print the user's previous guesses

---

### Option 2

Let's write a web shop! Choose **two** products of your liking and let the user select the amount they want to buy. Compute the total cost.

BONUS: Also offer express shipping for a small extra fee.

---

### Sample solutions

[guessing game](preject/numberguess.html)

[web store](preject/webstore.html)
