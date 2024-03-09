<!-- .slide: id="lesson11" -->

# Basic Frontend - Fall 2023

Lesson 11, Tuesday, 2022-10-24

---

### Recap: Objects

```js
let me = {
    name: "Owen",
    address: {
        country: "Germany",
        city: "Berlin"
    }
};

console.log(me.name)
console.log(me.address.city)
me.name = "Hasan"
console.log(me.name)
```

* What's the result?

```js
Ownen
Berlin
Hasan
```
<!-- .element: class="fragment" -->

---

### Recap: Exercise

Using your "me" object, create a method to introduce yourself (using console.log). Create a object within that represents your address.

```js
me.introduce();
// "Hi, my name is Owen"
console.log(me.address.city); // "Berlin"
console.log(me.address.country); // "Germany"
```

---

### Solution

```js
let me = {
    name: "Owen",
    introduce: function() {
        console.log("Hi, my name is " + this.name);
    },
    address: {
        city: "Berlin",
        country: "Germany"
    }
};

me.introduce();
console.log(me.address.city);
console.log(me.address.country);
```

---

### "this" in JavaScript

In JavaScript, ```this```  is a special keyword that refers to the object that the current function is a method of.

---

### Example

```js
let person = {
    name: "Hasan",
    greet: function() {
        console.log("Hello, my name is " + this.name);
    }
};

person.greet();
```

* What's the result?

```js
Hello, my name is Hasan
```
<!-- .element: class="fragment" -->

---

### Exercise

Create an object car with properties ```company``` and ```model```. Add a method ```describe``` that prints out something like the following:

```js
"I drive a {company} {model}"
```

---

### HTML and Javascript

HTML (Structure): HTML provides the basic structure of a webpage. It defines elements like headings, paragraphs, images, and more. It's like the skeleton of a webpage.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Page</title>
</head>
<body>
    <h1 id="greeting">Hello, World!</h1>
<body>
</html>
```
---

### HTML and Javascript

Javascript (Interactions): Javascript enables interactivity on a webpage. It allows you to respond to events like clicks, input, and more. JavaScript can change the content, style, and behavior of the webpage dynamically.

```js
function changeText() {
  document.getElementById("greeting").textContent = "Hi!";
}
```

---

### Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Page</title>
</head>
<body>
    <h1 id="greeting">Hello, World!</h1>
    <button onclick="changeText()">Click Me</button>

    <script>
        function changeText() {
            document.getElementById("greeting").textContent = "Hi, there!";
        }
    </script>
</body>
</html>

```

---

### Onclick Event

The ```onclick``` event is a specific type that happens when a user clicks on an element, like a button, link, or image.

---

### Example

```html
<button onclick="sayHello()">Click Me</button>
```

In this example, When a user clicks the button, it triggers the sayHello function

```js
function sayHello() {
    alert('Hello, World!');
}
```


---

### Changing the background color

The browser provides a variable `document.body.style.backgroundColor`.

We can assign a value to `document.body.style.backgroundColor` to change the background color of our HTML page.

```js
// change the current color:
document.body.style.backgroundColor = "red";
// print the current color to console
console.log("The current color:", document.body.style.backgroundColor);
```

---

### Task

Create a webpage with three buttons, "red", "green", "blue".

When you press the button, set `document.body.style.backgroundColor` to that color.

BONUS:

* If you press the button again, change the color back to white.
* Solve the task with only one single `function` and one single `if/else` statement.

---

### Solution

HTML:
```html
<button onclick="changeColor('red')">red</button>
```

JS:
```js
function changeColor(color) {
    if (document.body.style.backgroundColor === color) {
        document.body.style.backgroundColor = "white";
    } else {
        document.body.style.backgroundColor = color;
    }
}
```

---

### Manipulate HTML Elements from JavaScript

Let's say we have a HTML element:

```html
<div>Total Price: 0 EUR</div>
```

Wouldn't it be nice if we could dynamically change that from JavaScript?

---

<!-- .slide: id="get-element" -->

### document.getElementById

One way to obtain a variable pointing to a HTML element is `document.getElementById()`:

HTML:

```html
<div id="totalPrice">Total Price: 0 EUR</div>
```

JavaScript

```js
let priceDiv = document.getElementById("totalPrice");
```

---

`priceDiv` is a variable, and its type is `object`.

How do we know which properties/methods the object has?

We could try the browser's developer tools.

Or we could check MDN:

https://developer.mozilla.org/en-US/docs/Web/API/HTMLDivElement


---

Let's try some properties, see what happens:

```js
let priceDiv = document.getElementById("totalPrice");
// choose from below:
// priceDiv.textContent = "Hi from JavaScript";
// priceDiv.hidden = true;
// priceDiv.style.backgroundColor = "red";
// priceDiv.remove();
```

---

### Task 1

In HTML, create a `div` element and a `button`.

When the user clicks the button, set the background color of the `div` to red.

---

### Task 2

In HTML, create a `button` and a `div` element.

When the user clicks the button, update the `textContent` of the `div` element with the amount of times the user has clicked the button.

Example: "You clicked 12 times"

---

### Task 3

We're creating a web shop selling hummus (or chocolate, or eba and egusi soup)!

Create a number input field in HTML that lets the user choose the amount of hummus:

```html
Choose the amount of hummus servings:
<input type="number" id="amount" min="0" value="0" oninput="amountChanged()">
```

Use the `valueAsNumber` property of the number input to get the amount that the user selected in your `amountChanged` function. Output the total price the user has to pay to a `div` element.

---

### Task 4 (Bonus)

Extend your webshop to sell two products (e.g. hummus _and_ chocolate).

Every product has a different price. Update the total price in the `div` element every time the user changes the amount of hummus and chocolate.

---

### Task 5 (Bonus)

There's a special sale - if the user buys products for more than 20 EUR, they get 10% discount.

---

### Solution Task 1

HTML:

```html
<button onclick="changeColor()">Click me!</button>
<div id="myDiv">Hello</div>
<script>
    function changeColor() {
        let myDiv = document.getElementById("myDiv");
        myDiv.style.backgroundColor = "red";
    }
</script>
```

---

### Solution Task 2

```html
<button onclick="count()">Click me!</button>
<div id="myDiv">You clicked 0 times</div>
<script>
    let clickCount = 0;
    function count() {
        clickCount += 1;
        let myDiv = document.getElementById("myDiv");
        myDiv.textContent = "You clicked " + clickCount + " times";
    }
</script>
```

---

### Solution Task 3

```html
<input type="number" id="amount" min="0" value="0" oninput="amountChanged()">
<div id="priceDiv">0 EUR</div>
<script>
    let hummusPrice = 5;
    function amountChanged() {
        let amountElement = document.getElementById("amount");
        let priceDiv = document.getElementById("priceDiv");
        let amount = amountElement.valueAsNumber;
        let totalPrice = hummusPrice * amount;
        priceDiv.textContent = totalPrice + " EUR"
    }
</script>
```