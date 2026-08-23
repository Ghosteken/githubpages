# Part 4 — Beginner Q&A and Practice

A standalone practice document. Everything stays beginner-level and matches what's covered in Parts 1–3.

---

## Section A — Multiple Choice

1. What is JavaScript mainly used for on websites?
   A. Creating the structure
   B. Styling the website
   C. Adding behavior and interaction
   D. Storing files

2. Which language is used to create the structure of a webpage?
   A. CSS
   B. HTML
   C. JavaScript
   D. Python

3. Which language is used to style a webpage (colors, fonts, layout)?
   A. HTML
   B. CSS
   C. JavaScript
   D. SQL

4. How do you add JavaScript to an HTML page?
   A. Using a `<style>` tag
   B. Using a `<script>` tag
   C. Using a `<js>` tag
   D. JavaScript can't be added to HTML

5. Which keyword is used to create a variable in modern JavaScript?
   A. `var`
   B. `let`
   C. `int`
   D. `variable`

6. What will `console.log("5" + 3)` print?
   A. `8`
   B. `53`
   C. `35`
   D. An error

7. What data type is `true`?
   A. String
   B. Number
   C. Boolean
   D. Array

8. What symbol starts a single-line comment in JavaScript?
   A. `#`
   B. `//`
   C. `<!--`
   D. `**`

9. What does `console.log()` do?
   A. Deletes a variable
   B. Prints a message to the console
   C. Creates a new webpage
   D. Styles an element

10. What is `let age = 15;` an example of?
    A. A function
    B. A loop
    C. A variable
    D. An array

11. Which of these is a valid array?
    A. `let fruits = ("apple", "banana");`
    B. `let fruits = {"apple", "banana"};`
    C. `let fruits = ["apple", "banana"];`
    D. `let fruits = <apple, banana>;`

12. What is the index of the first item in an array?
    A. 1
    B. 0
    C. -1
    D. There is no index

13. What does an `if` statement do?
    A. Repeats code many times
    B. Stores a value
    C. Runs code only when a condition is true
    D. Prints text to the console

14. What is a function mainly used for?
    A. Storing a single number
    B. Styling text
    C. Reusable blocks of code you can run whenever needed
    D. Creating HTML elements

15. In `function greet(name) { ... }`, what is `name`?
    A. A loop
    B. A parameter
    C. A boolean
    D. A comment

16. What does a `for` loop do?
    A. Runs a block of code one time
    B. Repeats a block of code multiple times
    C. Stores multiple values
    D. Creates a function

17. Which event fires when a user clicks a button?
    A. `"load"`
    B. `"click"`
    C. `"scroll"`
    D. `"hover"`

18. What does `document.getElementById("title")` do?
    A. Creates a new element with id `title`
    B. Deletes the element with id `title`
    C. Finds and returns the element with id `title`
    D. Changes the page's title bar

19. What does `.textContent` let you do to an element?
    A. Change its color
    B. Change the text inside it
    C. Delete it from the page
    D. Move it on the page

20. What best describes an "object" in very simple terms?
    A. A single number
    B. A list of values in order
    C. A collection of related information stored as labeled properties
    D. A type of loop

---

## Section B — True or False

1. JavaScript can respond when a user clicks a button.
2. HTML is responsible for styling colors and fonts.
3. A variable declared with `let` can never change its value.
4. Strings must be wrapped in quotation marks.
5. `5 === "5"` and `5 == "5"` always behave exactly the same way.
6. Arrays can hold more than one value in a single variable.
7. A function only runs when it is called (invoked).
8. `console.log()` shows a message to the website's visitors, not just the developer.
9. Loops are useful for repeating a task without writing the same code many times.
10. `if`/`else` lets a program choose between two different actions.

---

## Section C — Predict the Output

For each snippet, predict what will print before running it.

**C1.**
```javascript
let x = 5;
let y = 3;
console.log(x + y);
```

**C2.**
```javascript
let name = "Alex";
console.log("Hi " + name + "!");
```

**C3.**
```javascript
let a = 10;
let b = 4;
console.log(a > b);
```

**C4.**
```javascript
let colors = ["red", "green", "blue"];
console.log(colors[1]);
```

**C5.**
```javascript
let score = 40;
if (score >= 50) {
    console.log("Pass");
} else {
    console.log("Fail");
}
```

**C6.**
```javascript
for (let i = 0; i < 3; i++) {
    console.log(i);
}
```

**C7.**
```javascript
function double(num) {
    console.log(num * 2);
}
double(6);
```

---

## Section D — Find the Problem

Each snippet has one beginner-level mistake. What's wrong?

**D1.**
```javascript
let age = 15
console.log(age)
```

**D2.**
```javascript
let name = Daniel;
console.log(name);
```

**D3.**
```javascript
if score >= 50 {
    console.log("Pass");
}
```

**D4.**
```javascript
function greet(name) {
console.log("Hello " + name);

greet("Sam");
```

**D5.**
```javascript
let fruits = ["apple", "banana", "mango"];
console.log(fruits[3]);
```

**D6.**
```javascript
for (let i = 0; i < 5, i++) {
    console.log(i);
}
```

---

## Section E — Small Coding Challenges

1. Create a variable containing your name.
2. Print your age using `console.log()`.
3. Add two numbers together and print the result.
4. Create an `if`/`else` statement that checks whether a number is even or odd... but keep it simple: just check if a variable called `isSunny` is `true` or `false` and print a matching message.
5. Create a function that says hello (no parameters needed).
6. Create a function that takes a `name` parameter and greets that person.
7. Create an array containing three of your favorite foods.
8. Print each item in your foods array using a loop.
9. Create a variable that stores a boolean, then use it in an `if` statement.
10. Write JavaScript that would make a button with `id="myButton"` change some text on the page to `"You clicked me!"` when clicked. (You may write this as if the HTML already has that button — you don't need to include the HTML.)

---
---

# ANSWER KEY

## Section A — Multiple Choice

1. **C** — JavaScript adds behavior and interaction; HTML is structure, CSS is style.
2. **B** — HTML.
3. **B** — CSS.
4. **B** — `<script>` tag.
5. **B** — `let` (modern, preferred way to declare variables).
6. **B** — `"53"` — because one value is text, `+` glues the two strings together instead of adding numbers.
7. **C** — Boolean.
8. **B** — `//` starts a single-line comment.
9. **B** — Prints a message to the console — a tool for developers to check what their code is doing.
10. **C** — A variable.
11. **C** — Square brackets `[ ]` create arrays.
12. **B** — Index `0` is the first item.
13. **C** — Runs code only when a condition is true.
14. **C** — A reusable block of code.
15. **B** — A parameter — a placeholder that receives a value when the function is called.
16. **B** — Repeats a block of code multiple times.
17. **B** — `"click"`.
18. **C** — Finds and returns the element with that id.
19. **B** — Changes the text inside the element.
20. **C** — A collection of related information stored as labeled properties (e.g. `{ name: "Ben", age: 16 }`).

## Section B — True or False

1. **True** — that's the whole point of event listeners like `addEventListener("click", ...)`.
2. **False** — CSS handles styling; HTML handles structure.
3. **False** — `let` variables *can* be reassigned a new value later (only `const` can't be reassigned, and that's beyond this course's scope, so just know `let` is changeable).
4. **True** — strings always need quotation marks (single or double).
5. **False** — `===` checks both value AND type (so `5 === "5"` is `false`); `==` only checks value and would say `true`. Beginners should stick to `===`.
6. **True** — that's exactly what arrays are for.
7. **True** — writing a function doesn't run it; calling it (`functionName()`) does.
8. **False** — `console.log()` only shows in the developer console, not on the actual webpage visitors see.
9. **True** — that's the main benefit of loops.
10. **True** — that's exactly what `if`/`else` is for.

## Section C — Predict the Output

- **C1.** `8`
- **C2.** `Hi Alex!`
- **C3.** `true`
- **C4.** `green` (index `1` is the *second* item, since counting starts at 0)
- **C5.** `Fail` (because `40 >= 50` is `false`)
- **C6.**
  ```
  0
  1
  2
  ```
- **C7.** `12` (6 multiplied by 2)

## Section D — Find the Problem

- **D1.** Not actually an error — missing semicolons still work in JavaScript, but it's best practice to add `;` at the end of each line: `let age = 15;` / `console.log(age);`
- **D2.** `Daniel` needs quotation marks — as written, JavaScript thinks `Daniel` is the name of a variable that doesn't exist, causing an error: `let name = "Daniel";`
- **D3.** The condition needs parentheses: `if (score >= 50) {`
- **D4.** Missing closing curly brace `}` after the `console.log` line, before `greet("Sam")` is called:
  ```javascript
  function greet(name) {
      console.log("Hello " + name);
  }

  greet("Sam");
  ```
- **D5.** The array only has indexes `0`, `1`, and `2` (three items) — there's no `fruits[3]`, so this prints `undefined`.
- **D6.** A `for` loop uses semicolons `;` to separate its three parts, not a comma: `for (let i = 0; i < 5; i++) {`

## Section E — Small Coding Challenges (sample answers)

1.
   ```javascript
   let myName = "Jordan";
   ```
   *Explanation:* Stores text in a variable. *Result:* Nothing prints yet — the value is just stored.

2.
   ```javascript
   let age = 16;
   console.log(age);
   ```
   *Explanation:* `console.log` prints the value of `age`. *Result:* `16`

3.
   ```javascript
   let num1 = 8;
   let num2 = 5;
   console.log(num1 + num2);
   ```
   *Explanation:* `+` adds two numbers. *Result:* `13`

4.
   ```javascript
   let isSunny = true;
   if (isSunny) {
       console.log("Let's go outside!");
   } else {
       console.log("Bring an umbrella!");
   }
   ```
   *Explanation:* Since `isSunny` is `true`, the `if` block runs. *Result:* `Let's go outside!`

5.
   ```javascript
   function sayHello() {
       console.log("Hello!");
   }
   sayHello();
   ```
   *Explanation:* Defines then calls the function. *Result:* `Hello!`

6.
   ```javascript
   function greet(name) {
       console.log("Hello, " + name + "!");
   }
   greet("Maya");
   ```
   *Explanation:* `name` is filled in with `"Maya"` when called. *Result:* `Hello, Maya!`

7.
   ```javascript
   let foods = ["pizza", "sushi", "tacos"];
   ```
   *Explanation:* Square brackets create a list of three strings. *Result:* Nothing prints yet — the array is just stored.

8.
   ```javascript
   for (let i = 0; i < foods.length; i++) {
       console.log(foods[i]);
   }
   ```
   *Explanation:* Loops from `0` up to (but not including) the array's length, printing each item. *Result:*
   ```
   pizza
   sushi
   tacos
   ```

9.
   ```javascript
   let hasPet = true;
   if (hasPet) {
       console.log("You have a pet!");
   }
   ```
   *Explanation:* Boolean controls whether the message prints. *Result:* `You have a pet!`

10.
    ```javascript
    document.getElementById("myButton").addEventListener("click", function () {
        document.getElementById("myButton").textContent = "You clicked me!";
    });
    ```
    *Explanation:* Finds the button, listens for a click, then changes its own text when clicked. *Result:* The button's label changes to "You clicked me!" the moment it's clicked.
