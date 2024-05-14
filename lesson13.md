<!-- .slide: id="lesson13" -->

# Basic Frontend - Spring 2024

Lesson 13, Tuesday, 2024-05-14

---

### Recap: Objects

```js
let me = {
    name: "Olof",
    hasGlasses: true,
    address: {
        city: "Berlin",
        country: "Germany",
    },
    introduce: function() {
        console.log("Hi, my name is " + this.name);
    },
    isWorking: function() {
      let now = new Date();
      return now.getHours() > 10 || now.getHours() < 18;
    },
};
```

* can you name all the properties in this object?
* and its keys?
* and its values?
* and its functions?

---

<!-- .slide: id="loops" -->

# Loop

---

### The problem

Output your name to `console.log` two times.

```js
console.log('Bob');
console.log('Bob');
```

<!-- .element: class="fragment" -->

Output your name to `console.log` 14207 times.

<!-- .element: class="fragment" -->

```js
// huh ????
```

<!-- .element: class="fragment" -->

---

### Loops

We use loops to run the same code in our programs repeatedly.

More generally, a loop is a way to repeat an action multiple times as long as a certain condition is `true`.

---

### Loops: cake recipe

Let's say I want to bake a cake:

<div style="display: flex;">

![scale](images/scale.webp) <!-- .element: style="width: 400px"-->

<div>
Cake recipe:<br>

- 6 eggs
- 3 cups of sugar
- 5 cups of flour
</div>
</div>

---

### Loops: cake recipe

We take an empty bowl and keep our ingredients ready.

We need 5 cups of flour.

1. What's the action that we need to repeat?
1. For how long do we need to repeat it?

---

### Loops: cake recipe

1. The action we need to repeat is adding a cup of flour to the bowl
1. We repeat it 5 times

---

### Loops: cake recipe

We can distinguish different parts in a loop:

- initialization: a starting point
- condition: a test to see if the loop should stop
- update: changes the value checked by the condition
- action: what we want to repeat

---

### Loops: cake recipe

- initialization: no flour in the bowl (`cupsOfFlour = 0`)
- condition: did we put less than 5 cups of flour? (`cupsOfFlour < 5`)
- update: cups of flour in the bowl (`cupsOfFlour++`)
- action: add flour to the bowl

---

### While loop

Let's see how to make an actual loop in JavaScript.

A `while` loop repeats its body while its `condition` is `true`:

```js
while (condition) {
  // body is executed while "condition" is true
  console.log('Hello from while loop');
}
```

---

### While loop

```js
let cupsOfFlour = 0; // initialization
while (cupsOfFlour < 5) {
  // condition
  console.log('Take a cup of flour and put it in the bowl'); // action
  cupsOfFlour++; // update
  console.log('There are now ' + cupsOfFlour + ' cups of flour in the bowl');
}
```

---

### While loop

A while loop might execute zero to unlimited times:

```js
let isHungry = false; // we just ate
while (isHungry) {
  eat(); // this is never reached!
}
```

---

### While loop

Always make sure that a `while` loop's condition is eventually set to `false`.
Otherwise your loop will run infinitely.

```js
let bitesOfChocolate = 0;
while (bitesOfChocolate < 10) {
  console.log('Bites of chocolate: ' + bitesOfChocolate);
  console.log('Still hungry.');
}
// this code will print "Bites of chocolate: 0" and
//"Still hungry" until your laptop runs out of battery,
// you close the browser, you reboot or the universe ends
```

---

### Task

Let's `console.log` the numbers from 1 to 5 using a `while` loop.

---

### Counting - solution

Quiz: Let's `console.log` the numbers from 1 to 5 using a `while` loop.

```js
let i = 1; // initialize i with 1
while (i <= 5) {
  // repeat this loop until we reach 5
  console.log(i);
  i++; // update i at every step
}
```

---

### Quiz

What will this loop output?

```js
let i = 0;
while (i < 2) {
  console.log(i);
}
```

Answer: 0, until you run out of battery<!-- .element: class="fragment" -->

---

### Quiz

- How many times will the loop run?

```js
let i = 10;
while (i < 15) {
  console.log(i);
  i++;
}
```

Answer: 5 times <!-- .element: class="fragment" -->

---

### Tasks

- Output your name five times
- Output the squares of the first 10 numbers starting with 1 (1, 4, 9, 16, ...)

---

### Solutions

Output your name five times

```js
let i = 0;
while (i < 5) {
  console.log('Carlo');
  i++;
}
```

---

Squaring the first 10 numbers

```js
let i = 1;
while (i < 11) {
  console.log(i * i); // or i ** 2
  i++;
}
```

---

### loop: recap quiz

1. What can we do with loops?
1. What are the main parts of a loop?
1. Can a loop run 0 times?
1. Can a loop run only 1 time?

---

### loop: recap

- a loop lets us execute a block of code multiple times
- the block is executed as long as certain condition is true
- we normally need a starting point, initializing some variable
- inside the block that is repeated, we usually update some value to make sure that the loop can stop


---

But developers are lazy, we want to write the least amount of code as possible.

Hence, the for loop!

---


<!-- .slide: id="forLoop" -->

# For loop

look at this example, can you explain how do we write a for loop?

```js
for (let counter = 0; counter < 10; counter++){
  console.log(counter);
}
```

---
### For loops

A `for` loop works like a `while` loop, but it's more concise.

```js
for (initialization; condition; update) {
  // loop body
}
```


---

### Anatomy of a for loop

- `for`
- `(`
-  initialization
- `;`
- condition
- `;`
- update

The 3 main parts of the loop are all in one line, separated by semicolons (`;`).

---

### For loop

Let's replace our `while` loop with a `for`:

```js
let i = 1;       // part 1 - *initialize* the counter
while (i < 6) {  // part 2 - *test* the exit *condition*
  console.log(i);// loop body
  i++;           // part 3 - *update* the counter
}

// same code with for loop:
for (let i = 1; i < 6; i++) {
  console.log(i);
}
```

---

### For loop - summary

* A `while` loop executes its body while the condition is `true`.
* A `for` loop *first* runs the **initialization** part, then tests the **condition** part
  and, if it is `true`, executes the body. After every loop, it executes the **update** part.

---

### For vs. while

* We use a `for` loop if we know in advance how often it will be executed.

```js
for (let i = 0; i < 1000; i++) {
  console.log(i);
}
```

* We use a `while` loop if we don't know how many times the loop will be executed.

```js
while (passwordIsWrong) {
  askForPassword();
}
```

---


### Task

use a for loop and output the numbers between 0 and 10 (including both) to the console


```js
for(let i = 0; i < 11; i++){
  console.log(i);
}
```
<!-- .element: class="fragment" -->

---

### Task

use a for loop and output the numbers between 13 and 17 (including both) to the console


```js
for(let i = 13; i <= 17; i++){
  console.log(i);
}
```
<!-- .element: class="fragment" -->

---

### For loops & arrays

For loops and arrays work wonderfully together!

```js
let languages = ["english", "german", "arabic", "russian"]

for (let i = 0; i < languages.length; i++){
  console.log(languages[i]);
}
```

---
### Task

use a for loop to output: hello name! for every one of your friends:


```js
let friends = ['Harald', 'Sevtap', 'Akram', 'Abdo', 'Meli'];
// ????
```


---

### Task

use a for loop and output the numbers between 5 and -3 (including both) to the console


```js
for(let i = 5; i > -4; i--){
  console.log(i);
}
```
<!-- .element: class="fragment" -->

---

### More tasks?

- Output the sum of the first 10 numbers (e.g. 1 + 2 + 3 + ...)
- Output a countdown from 10 to 0 to console (e.g. 10, 9, 8, ...)
    - Bonus: Instead of zero, output "liftoff!"
    - Bonus: Instead of counting down to console.log, write the output to a an HTML page

