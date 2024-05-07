<!-- .slide: id="lesson12" -->

# Basic Frontend - Spring 2024

Lesson 12, Tuesday, 2024-05-07

---

### Recap

What do you remember about changing HTML from JavaScript?

---

<!-- .slide: id="arrays" -->

# Array

---

### Arrays

An `array` is a container type that holds multiple values:

```js
// we create an empty array using []
let emptyArray = [];

// we put the values we want in square brackets
// separated by commas
let ages = [19, 33, 25, 40];
let cities = ['London', 'Paris', 'Berlin'];
```

---

Array can hold any type of value:

```js
let prices = [0.99, 1.49];
```

And any quantity:

```js
// I only have one favorite food
let favoriteFoods = ['Pizza'];
// An array holding 26 letters of the alphabet
let alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l']; //TODO
```

---

### Analogy: Bookshelf

A bookshelf can be thought of as an array of books

![bookshelf](images/bookshelf.jpg)

```js
let books = ['Harry Potter', 'The Hobbit', 'Game of Thrones'];
```

---

### Usage

Can you think of use cases for arrays? Where would we use it?

- a todo list
<!-- .element: class="fragment" -->
- a shopping list
<!-- .element: class="fragment" -->
- ingredients in a recipe
<!-- .element: class="fragment" -->
- the students in this class
<!-- .element: class="fragment" -->
- the numbers from 1 to 10
<!-- .element: class="fragment" -->

---

### Accessing elements

We can access elements in the array by number using square brackets "`[]`"

The numbering starts at `0` (think floors of a building):

```js
let books = ['Harry Potter', 'The Hobbit', 'Game of Thrones'];

console.log(books[0]); // "Harry Potter"
console.log(books[1]); // "The Hobbit"

// QUIZ - how do we access "Game of Thrones" ?
```

```js
console.log(books[2]); // "Game of Thrones"
```

<!-- .element: class="fragment" -->

The order of elements in the array matters!

<!-- .element: class="fragment" -->

---

### Bookshelf array

![bookshelf](images/array_bookshelf_0.png)

---

### Invalid elements

```js
let books = ['Harry Potter', 'The Hobbit', 'Game of Thrones'];

console.log(books[0]); // "Harry Potter"
console.log(books[1]); // "The Hobbit"
console.log(books[2]); // "Game of Thrones"
console.log(books[3]); // ???
```

```js
console.log(books[3]); // undefined
```

<!-- .element: class="fragment" -->

---

### Quiz

```js
let friends = ['Alice', 'Bob', 'Carol'];

console.log(friends[1]); // ???
console.log(friends[3]); // ???
```

```js
console.log(friends[1]); // "Bob"
console.log(friends[3]); // undefined
```

<!-- .element: class="fragment" -->

---

### Array vs Object

Both `array` and `object` can store multiple values:

```js
let favoriteNumbersArray = [42, 24];
let favoriteNumbersObject = {
    first: 42,
    second: 24
};
```

Use object if you want to access elements by by key (string), use arrays if you want to access elements by its index (number).

---

### Task 1

- Step 1: Create an array with your 3 top friends
- Step 2: Say "hello" on console to each friend, in the array:

```plaintext
hello Alice
hello Bob
hello Carol
```

---

### Task 1: Solution

```js
let friends = ['Sevtap', 'Carlo', 'Abdullah'];
console.log('hello ' + friends[0]);
console.log('hello ' + friends[1]);
console.log('hello ' + friends[2]);
```

---

### Modifying arrays

We can change any value using brackets:

```js
let friends = ['Alice', 'Bob', 'Carol'];

friends[1] = 'David';
// friends array is now ["Alice", "David", "Carol"]

console.log(friends[1]); // "David"
```

---

### Common operations: array length

We can get the length of an array with the `.length` property:

```js
let friends = ['Alice', 'Bob', 'Carol'];
console.log(friends.length); // 3
```

---

### Appending new values

We can append new values to an array using `.push()`:

```js
let friends = ['Alice', 'Bob', 'Carol'];
console.log(friends.length); // 3

friends.push('David');

console.log(friends.length); // 4
console.log(friends[3]); // David
```

---

### remove a value

We can remove the last element from an array `.pop()`:

```js
let fruits = ['Banana', 'Apple', 'Orange', 'Grape'];
console.log(fruits.length); // 4

fruits.pop();

console.log(fruits.length); // 3
console.log(fruits[4]); // undefined
```

`.pop()` also returns the removed element

---

### HTML and Arrays

Every HTML element has a `children` property that returns an array of its children.

```html
<body>
  <div>First</div>
  <div>Second</div>
</body>
```

How can we access the two `div` elements inside the body (without `document.getElementById`?)

---

### HTML and Arrays

```js
let firstDiv = document.body.children[0];
let secondDiv = document.body.children[1];

// firstDiv and secondDiv now point to the two divs inside body
// we can now get/set properties
firstDiv.textContent = "This is the first div";
secondDiv.style.backgroundColor = "green";
```

---

### Task 1

You have an array with your favorite vegetables, e.g:

```js
// this line is given. Do not touch :)
let favoriteVeggies = ['eggplant', 'broccoli', 'potato'];
```

Add some code that replaces 'broccoli' with 'carrot' and some code that adds 'pepper' to the end of `favoriteVeggies`.

After your code ran, the array should look like this:

```js
['eggplant', 'carrot', 'potato', 'pepper']
```

---

### Task 2

You have the following HTML in your body:

```html
<div id="colors">
  <div>red</div>
  <div>yellow</div>
  <div>green</div>
</div>
```

Write some JavaScript code that sets the `backgroundColor` of the three inner `div` elements to the color of their `textContent`. Example: The first `div` should have a red background color.

---

### Task 3

Create an array of 4 friends.

You and your friends want to go to the cinema (costs 7 euros each ticket). It is the birthday of the last friend, so you want to gift the ticket to them.

Payment goes like this:

- The first friend pays half of the total price.
- The last person pays nothing.
- The remaining friends pay the remaining cost equally split between them.

Print the results to the console.

---

Example: Friends are Harald, Sevtap, Akram and Abdo. The output should be:

```plaintext
Harald pays 14
The others pay 7 each
Congratulations Abdo! You pay nothing
```

---

### BONUS: Task 4

Create a `function` called `cinemaCost` that takes an array of friends and outputs the same as in Task 1. The function must work for any amount of friends:

```js
function cinemaCost(friends) {
    // your code here
}
let friends = ['Harald', 'Abdo', 'Sevtap', 'Oerd', 'Meli'];
cinemaCost(friends);
friends.push('Gina');
cinemaCost(friends);
friends.push('Bruna');
cinemaCost(friends);
```

---

### Task 1 - Solution

```js
let favoriteVeggies = ['eggplant', 'broccoli', '**potato**'];
favoriteVeggies[1] = 'carrot';
favoriteVeggies.push('pepper');
```

---

### Task 2 - Solution

```js
let colorElement = document.getElementById("colors");
let children = colorElement.children;
children[0].style.backgroundColor = children[0].textContent;
children[1].style.backgroundColor = children[1].textContent;
children[2].style.backgroundColor = children[2].textContent;
```

---

### Task 3 - Solution

```js
let friends = ['Harald', 'Sevtap', 'Abdo', 'Meli'];
let pricePerTicket = 7;
let totalPrice = 4 * pricePerTicket;
let halfPrice = totalPrice / 2;
let dividedCost = halfPrice / 2; // two friends remaining, split the remaining cost evenly

console.log(friends[0] + ' pays ' + halfPrice);
console.log('The others pay ' + dividedCost + ' each');
console.log(
  'Congratulations ' + friends[3] + '! You pay nothing'
);
```

---

### Task 4 - Solution

```js
function cinemaCost(friends) {
  let pricePerTicket = 7;
  let totalPrice = friends.length * pricePerTicket;
  let halfPrice = totalPrice / 2;
  let dividedCost = halfPrice / (friends.length - 2); // the remainder number of friends is always the total minus 2 (the first and last friend)

  console.log(friends[0] + ' pays ' + halfPrice);
  console.log('The others pay ' + dividedCost + ' each');
  console.log(
    'Congratulations ' + friends[friends.length - 1] + '! You pay nothing'
  );
}
```
