<!-- .slide: id="lesson8" -->

# Basic Frontend - Fall 2023

Lesson 8, Thursday, 2023-10-12

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

### Other analogies?

Can you think of other analogies for arrays?

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
- a set of random numbers
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

### Task 1

- Step 1: Create an array with your 3 top friends
- Step 2: Say "hello" on console to each friend, e.g.:

```plaintext
hello Alice
hello Bob
hello Carol
```

---

### Task 1: solution

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

### Task 1

Create an array of friends (any number more than 3).

You and your friends wanna go to a show (costs 7 euros each ticket). It is the birthday of the last friend, so you want to gift them.

It will go like this:

- The first friend will pay half of the total price.
- The remaining will pay the other half.
- The last person pays nothing.

Print the results in the console.

---

Example: my friends are Harald, Sevtap, Akram and Abdo. The output should be:

```
"Harald pays 14"
"The others pay 7 each"
"Congratulations Abdo! You pay nothing"
```

---

### Task 1 - Solution

```js
let friends = ['Harald', 'Sevtap', 'Akram', 'Abdo', 'Mell'];
let total = friends.length * 7;
let half = total / 2;
let halfDividedByRest = half / (friends.length - 2); // the remainder number of friends is always the total minus 2 (the first and last friend)

console.log(friends[0] + ' pays ' + half);
console.log('The others pay ' + halfDividedByRest + ' each');
console.log(
  'Congratulations ' + friends[friends.length - 1] + '! You pay nothing'
);
```

---

### Task 2

Let's say your last friend had a fight with you and now you want to update your array and **change their name to a generic "Karen"**.
Using your previously created array, update it with the new friend.

Then, you met a new friend and want to **add** them to your list. Update your array and log:

`Welcome, <person name> to our group of friends!`

---

### Task 2 - Solution

```js
friends[friends.length - 1] = 'Karen'; // update last item to be "Karen"
console.log('New friends: ' + friends);

friends.push('Obama'); // add a new item to the end of the array. Our friend calls "Obama"
console.log(
  'Welcome, ' + friends[friends.length - 1] + ' to our group of friends!'
);
```
