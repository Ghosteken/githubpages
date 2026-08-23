# Part 2 — Core JavaScript Live-Coding Examples

Pure JavaScript fundamentals — no HTML, no CSS, no website. Just type these into the browser console (press F12, click "Console") or a scratch `.js` file and run them.

Keep this part **separate** from Part 3 (the portfolio demos). This part is about learning the JavaScript language itself.

Examples 1–10 cover the core fundamentals in order of difficulty. Examples 11–20 are a bit more challenging — use them with students who finish early, or as a second pass once the basics feel solid. Every example also includes a short **Variants** section — two extra versions of the same idea, in case one class needs a different angle than another, or a fast finisher wants more to try.

---

## Example 1 — Variables

**Concept:** A variable is a labeled box that stores a value so you can use it later.

**Starting code:**
```javascript
let name = "Daniel";
console.log("Hello " + name);
```

**Expected output:**
```
Hello Daniel
```

**Explain it simply:** Think of `let name = "Daniel"` as putting the word "Daniel" into a box labeled `name`. Whenever we say `name` after that, JavaScript swaps in whatever is in the box. The `+` glues two pieces of text together.

**Live modifications:**
1. Change the value:
   ```javascript
   let name = "Sarah";
   ```
   → Output becomes `Hello Sarah`. Only the thing inside the box changed — the rest of the code didn't need to change at all.
2. Change the message too:
   ```javascript
   let name = "Michael";
   console.log("Welcome " + name);
   ```
   → Output becomes `Welcome Michael`.
3. Use two variables:
   ```javascript
   let firstName = "Daniel";
   let lastName = "Osei";
   console.log("Hello " + firstName + " " + lastName);
   ```
   → Output becomes `Hello Daniel Osei`.

**"What if?" questions (ask before you run it):**
- "What do you think will happen if I change `Daniel` to your name?"
- "What happens if I forget the quotation marks around Daniel?" (it becomes an error — JavaScript thinks `Daniel` is a variable name, not text)
- "Can someone predict the output before I press enter?"

**Challenge:** Create a variable called `city` with the name of your city, then print `"I live in "` followed by that variable.

**Variants to try:**
- **Variant A — a number instead of a string:** `let score = 100; console.log(score);` → `100` (no quotes needed for numbers).
- **Variant B — two variables, two lines:** `let city = "Lagos"; let country = "Nigeria"; console.log(city); console.log(country);` → prints `Lagos` then `Nigeria` on separate lines.

---

## Example 2 — Strings

**Concept:** A string is just text — always wrapped in quotation marks.

**Starting code:**
```javascript
let greeting = "Good morning!";
console.log(greeting);
console.log(greeting.length);
```

**Expected output:**
```
Good morning!
13
```

**Explain it simply:** Anything in quotes is a string. Strings have handy built-in tools called "properties" and "methods" — `.length` counts how many characters are in the string (including spaces and the `!`).

**Live modifications:**
1. Change the text:
   ```javascript
   let greeting = "Hi!";
   ```
   → `.length` changes from `13` to `3`.
2. Make it uppercase:
   ```javascript
   console.log(greeting.toUpperCase());
   ```
   → Output: `GOOD MORNING!`
3. Combine two strings:
   ```javascript
   let firstWord = "Java";
   let secondWord = "Script";
   console.log(firstWord + secondWord);
   ```
   → Output: `JavaScript`

**"What if?" questions:**
- "What do you think `.length` will print for `'Hi!'`?"
- "What happens if I add a space inside the quotes — does it count?"
- "What happens if I use `.toLowerCase()` instead?"

**Challenge:** Make a variable with your favorite food as a string, print it in all uppercase letters, and print how many characters it has.

**Variants to try:**
- **Variant A — a longer sentence:** `let bio = "I love JavaScript!"; console.log(bio.length);` → `18` (spaces and punctuation count too).
- **Variant B — combine `.toUpperCase()` with concatenation:** `let word = "fun"; console.log("This is so " + word.toUpperCase() + "!");` → `This is so FUN!`

---

## Example 3 — Numbers and Arithmetic

**Concept:** JavaScript can store numbers and do math with them, just like a calculator.

**Starting code:**
```javascript
let x = 5;
let y = 3;
console.log(x + y);
```

**Expected output:**
```
8
```

**Explain it simply:** No quotation marks around numbers — that's how JavaScript knows `5` is a number and not text. `+` adds them together like normal math.

**Live modifications:**
1. Try a different operator:
   ```javascript
   console.log(x - y);
   console.log(x * y);
   console.log(x / y);
   ```
   → Outputs: `2`, `15`, `1.666...`
2. Change the numbers:
   ```javascript
   let x = 10;
   let y = 4;
   ```
   → All the answers above change too.
3. Put numbers in quotes (on purpose, to show a surprise):
   ```javascript
   let x = "5";
   let y = "3";
   console.log(x + y);
   ```
   → Output: `53` (text glued together, not added!)

**"What if?" questions:**
- "What do you think will happen if I change 5 to 20?"
- "What happens if I put the numbers inside quotation marks?"
- "Can you predict the output of `x * y` before I run it?"

**Challenge:** Create two variables holding your age and a friend's age, then print their total.

**Variants to try:**
- **Variant A — the remainder operator:** `console.log(10 % 3);` → `1` (10 divided by 3 leaves a remainder of 1 — great for "is this number even?" checks later).
- **Variant B — order of operations:** `console.log(2 + 3 * 4);` → `14`, not `20` — JavaScript does multiplication before addition, just like in math class.

---

## Example 4 — Booleans

**Concept:** A boolean is a value that can only be `true` or `false` — like answering a yes/no question.

**Starting code:**
```javascript
let isRaining = true;
console.log(isRaining);
console.log(5 > 3);
```

**Expected output:**
```
true
true
```

**Explain it simply:** Booleans are how computers make decisions. `5 > 3` is a question — "is 5 greater than 3?" — and JavaScript answers it with `true` or `false`.

**Live modifications:**
1. Flip the value:
   ```javascript
   let isRaining = false;
   ```
   → Output: `false`
2. Try a different comparison:
   ```javascript
   console.log(5 === 5);
   console.log(5 === 6);
   console.log(10 < 2);
   ```
   → Outputs: `true`, `false`, `false`
3. Compare two variables:
   ```javascript
   let age = 15;
   let minimumAge = 13;
   console.log(age >= minimumAge);
   ```
   → Output: `true`

**"What if?" questions:**
- "What do you think `5 === 6` will print?"
- "What happens if I change `>` to `<`?"
- "What happens if the two numbers are equal — what will `===` say?"

**Challenge:** Create a variable `hasHomework` set to `true` or `false`, then print it.

**Variants to try:**
- **Variant A — comparing two strings:** `console.log("cat" === "cat");` → `true` — `===` works on text too, not just numbers.
- **Variant B — the `!` (not) operator:** `let isWeekend = false; console.log(!isWeekend);` → `true` — `!` flips a boolean to its opposite.

---

## Example 5 — `if` / `else`

**Concept:** `if`/`else` lets your program make a decision and choose which code to run.

**Starting code:**
```javascript
let score = 50;

if (score >= 50) {
    console.log("You passed!");
} else {
    console.log("Try again!");
}
```

**Expected output:**
```
You passed!
```

**Explain it simply:** JavaScript checks the condition inside the `( )`. If it's `true`, it runs the code inside the first `{ }`. If it's `false`, it skips down to `else` and runs that code instead.

**Live modifications (Starting Code → Modification → New Result → Explanation):**

*Experiment 1:* Change the score.
```javascript
score = 30;
```
→ New result: `Try again!` — because `30 >= 50` is now `false`, so JavaScript runs the `else` block instead.

*Experiment 2:* Change the condition.
```javascript
if (score >= 90) {
```
→ Ask: "If score is 50, will this still say 'You passed'?" (No — 50 is not ≥ 90.)

*Experiment 3:* Change the message.
```javascript
console.log("Amazing job, you passed!");
```
→ Same logic, different wording — shows that the message is just text we choose.

*Experiment 4:* Ask a student to pick their own score and predict which branch runs before you type it in.

**"What if?" questions:**
- "What do you think will happen if I change 50 to 30?"
- "What happens if we remove the `else` part completely?"
- "Can someone suggest another score we could test?"

**Challenge:** Write an `if`/`else` that prints `"You can watch a movie"` if `age` is 13 or older, and `"Ask a parent first"` otherwise.

**Variants to try:**
- **Variant A — comparing a name instead of a number:** `let name = "Sam"; if (name === "Sam") { console.log("Hi Sam!"); } else { console.log("Who are you?"); }` → `Hi Sam!`
- **Variant B — no `else` at all:** `let temperature = 35; if (temperature > 30) { console.log("It's hot!"); }` → prints `It's hot!`, but if the condition were false, nothing would print — there's no fallback message.

---

## Example 6 — Functions

**Concept:** A function is a reusable block of code you can run whenever you want, just by calling its name.

**Starting code:**
```javascript
function sayHello() {
    console.log("Hello there!");
}

sayHello();
```

**Expected output:**
```
Hello there!
```

**Explain it simply:** Writing `function sayHello() { ... }` is like writing a recipe — it doesn't cook anything by itself. Typing `sayHello();` is what actually "runs the recipe."

**Live modifications:**
1. Call it more than once:
   ```javascript
   sayHello();
   sayHello();
   sayHello();
   ```
   → Prints `Hello there!` three times.
2. Change what's inside:
   ```javascript
   function sayHello() {
       console.log("Hey! Welcome to class!");
   }
   ```
   → The message changes everywhere it's called.
3. Forget to call it:
   ```javascript
   function sayHello() {
       console.log("Hello there!");
   }
   // sayHello(); is missing
   ```
   → Nothing prints at all — a great "aha" moment.

**"What if?" questions:**
- "What happens if I call `sayHello()` three times in a row?"
- "What happens if I never call the function at all?"
- "Who can tell me what this line does: `sayHello();`?"

**Challenge:** Write a function called `sayGoodbye` that prints `"See you tomorrow!"`, then call it.

**Variants to try:**
- **Variant A — a function that does a calculation:** `function printSquare() { console.log(4 * 4); } printSquare();` → `16`
- **Variant B — two different functions called in sequence:** `function sayHi() { console.log("Hi!"); } function sayBye() { console.log("Bye!"); } sayHi(); sayBye();` → prints `Hi!` then `Bye!`

---

## Example 7 — Function Parameters

**Concept:** Parameters let you pass information *into* a function, so it can behave differently each time.

**Starting code:**
```javascript
function greet(name) {
    console.log("Hello " + name + "!");
}

greet("Daniel");
```

**Expected output:**
```
Hello Daniel!
```

**Explain it simply:** `name` inside the parentheses is a placeholder — an empty box waiting to be filled in. Whatever we type inside `greet( ... )` when we call it gets dropped into that box.

**Live modifications:**
1. Call it with a different value:
   ```javascript
   greet("Sarah");
   ```
   → Output: `Hello Sarah!`
2. Call it multiple times with different names:
   ```javascript
   greet("Michael");
   greet("Amaka");
   ```
   → Two separate greetings print.
3. Add a second parameter:
   ```javascript
   function greet(name, timeOfDay) {
       console.log("Good " + timeOfDay + ", " + name + "!");
   }

   greet("Daniel", "morning");
   ```
   → Output: `Good morning, Daniel!`

**"What if?" questions:**
- "What do you think will change if I call `greet('Sarah')` instead of `greet('Daniel')`?"
- "What happens if I call `greet()` with nothing inside the parentheses?" (prints `Hello undefined!` — great teaching moment)
- "Can someone predict what a second parameter would do before I add one?"

**Challenge:** Write a function `addNumbers(a, b)` that prints the sum of `a` and `b`, then call it with two numbers of your choice.

**Variants to try:**
- **Variant A — a single number parameter:** `function double(num) { console.log(num * 2); } double(5);` → `10`
- **Variant B — three parameters at once:** `function introduce(name, age, city) { console.log(name + " is " + age + " and lives in " + city); } introduce("Tomi", 15, "Abuja");` → `Tomi is 15 and lives in Abuja`

---

## Example 8 — Arrays

**Concept:** An array is a single variable that holds an ordered *list* of values.

**Starting code:**
```javascript
let fruits = ["apple", "banana", "mango"];
console.log(fruits);
console.log(fruits[0]);
```

**Expected output:**
```
[ 'apple', 'banana', 'mango' ]
apple
```

**Explain it simply:** Square brackets `[ ]` create a list. Each item has a position number called an "index" — but counting starts at `0`, not `1`. So `fruits[0]` is the *first* item.

**Live modifications:**
1. Get a different item:
   ```javascript
   console.log(fruits[1]);
   console.log(fruits[2]);
   ```
   → Outputs: `banana`, `mango`
2. Add a new item:
   ```javascript
   fruits.push("orange");
   console.log(fruits);
   ```
   → `[ 'apple', 'banana', 'mango', 'orange' ]`
3. Change an item:
   ```javascript
   fruits[0] = "pineapple";
   console.log(fruits);
   ```
   → `[ 'pineapple', 'banana', 'mango' ]`

**"What if?" questions:**
- "What do you think `fruits[1]` will print?"
- "What happens if I ask for `fruits[10]`, but there's no 10th item?" (prints `undefined`)
- "What happens if we `.push()` a new item — where does it go?"

**Challenge:** Create an array of your three favorite games or shows, then print the second one in the list.

**Variants to try:**
- **Variant A — an array of numbers:** `let scores = [90, 85, 100]; console.log(scores[2]);` → `100`
- **Variant B — checking the array's length:** `let fruits = ["apple", "banana", "mango"]; console.log(fruits.length);` → `3`

---

## Example 9 — Loops

**Concept:** A loop repeats a block of code automatically, instead of you copy-pasting it over and over.

**Starting code:**
```javascript
for (let i = 0; i < 3; i++) {
    console.log("Hi number " + i);
}
```

**Expected output:**
```
Hi number 0
Hi number 1
Hi number 2
```

**Explain it simply:** `let i = 0` starts a counter at 0. `i < 3` is the rule — keep looping *while this is true*. `i++` means "add 1 to i" after each lap. When `i` reaches 3, `3 < 3` is `false`, so the loop stops.

**Live modifications:**
1. Change how many times it loops:
   ```javascript
   for (let i = 0; i < 5; i++) {
   ```
   → Now it prints 5 lines instead of 3.
2. Loop over an array instead:
   ```javascript
   let fruits = ["apple", "banana", "mango"];
   for (let i = 0; i < fruits.length; i++) {
       console.log(fruits[i]);
   }
   ```
   → Prints each fruit on its own line.
3. Start the counter somewhere else:
   ```javascript
   for (let i = 1; i < 3; i++) {
   ```
   → Now it only prints `Hi number 1` and `Hi number 2` — it skips 0.

**"What if?" questions:**
- "What do you think will happen if I change 3 to 5?"
- "What happens if I start `i` at 1 instead of 0?"
- "What happens if I forget `i++` — can anyone guess?" (it loops forever — a fun, slightly scary demo, be ready to stop it)

**Challenge:** Write a loop that prints the numbers 1 through 10.

**Variants to try:**
- **Variant A — counting down instead of up:** `for (let i = 5; i > 0; i--) { console.log(i); }` → prints `5, 4, 3, 2, 1`.
- **Variant B — skipping by 2s:** `for (let i = 0; i <= 10; i += 2) { console.log(i); }` → prints `0, 2, 4, 6, 8, 10`.

---

## Example 10 — Combining Simple Concepts

**Concept:** Real programs mix variables, functions, arrays, loops, and `if`/`else` together. This example combines everything from Examples 1–9.

**Starting code:**
```javascript
let students = ["Daniel", "Sarah", "Michael"];

function greetStudent(name) {
    if (name === "Daniel") {
        console.log("Welcome back, " + name + "!");
    } else {
        console.log("Hello, " + name + "!");
    }
}

for (let i = 0; i < students.length; i++) {
    greetStudent(students[i]);
}
```

**Expected output:**
```
Welcome back, Daniel!
Hello, Sarah!
Hello, Michael!
```

**Explain it simply:** This walks through the `students` array one name at a time (the loop), hands each name to the function `greetStudent` (a parameter), and the function decides *which* message to print (the `if`/`else`). Every piece we learned separately is now working together.

**Live modifications:**
1. Add a new student to the array:
   ```javascript
   let students = ["Daniel", "Sarah", "Michael", "Amaka"];
   ```
   → The loop automatically greets the new student too — no other code needs to change.
2. Change the special name:
   ```javascript
   if (name === "Sarah") {
   ```
   → Now Sarah gets the "Welcome back" message instead of Daniel.
3. Add a `console.log` counting students:
   ```javascript
   console.log("Total students: " + students.length);
   ```
   → Prints the count before or after the greetings, depending on where you place it.

**"What if?" questions:**
- "What do you think happens if I add a name to the array — do I need to change the loop?"
- "What happens if no name matches the `if` condition?"
- "Can someone predict the full output before I run it, line by line?"

**Challenge:** Add a 4th student to the array and add a second special greeting for a different name using `else if`.

**Variants to try:**
- **Variant A — foods instead of students:** loop over `let foods = ["pizza", "sushi", "tacos"];` printing `"I like " + foods[i] + "!"` for each — same loop pattern, different data.
- **Variant B — pass/fail scores:** loop over `let scores = [80, 40, 95];`, using `if (scores[i] >= 50)` inside the loop to print `"Pass"` or `"Fail"` for each score.

---

## Example 11 — `else if` (More Than Two Choices)

**Concept:** `else if` lets a program choose between *more than two* paths, checked in order from top to bottom.

**Starting code:**
```javascript
let grade = 75;

if (grade >= 90) {
    console.log("Grade: A");
} else if (grade >= 70) {
    console.log("Grade: B");
} else if (grade >= 50) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}
```

**Expected output:**
```
Grade: B
```

**Explain it simply:** JavaScript checks each condition top to bottom and stops at the *first* one that's `true`. `75 >= 90` is false, so it moves down. `75 >= 70` is true, so it prints `"Grade: B"` and skips everything below — it never even looks at the other conditions.

**Live modifications:**
1. Change the grade to `95`:
   ```javascript
   let grade = 95;
   ```
   → Output: `Grade: A` — the very first condition now matches.
2. Change the grade to `40`:
   ```javascript
   let grade = 40;
   ```
   → Output: `Grade: F` — none of the `if`/`else if` conditions matched, so it falls through to the final `else`.
3. Add a new tier between B and C:
   ```javascript
   } else if (grade >= 60) {
       console.log("Grade: C+");
   ```

**"What if?" questions:**
- "What do you think happens if two conditions could both technically be true — which one wins?"
- "What happens if I put the `grade >= 50` check ABOVE the `grade >= 70` check? Would B ever print?"
- "Can someone predict the output for grade = 68 before I run it?"

**Challenge:** Write your own `if`/`else if`/`else` chain that prints a weather suggestion based on a `temperature` variable (e.g. "Wear a coat" below 10, "Nice day" between 10–25, "Stay hydrated" above 25).

**Variants to try:**
- **Variant A — different grade cutoffs:** change the tiers to A ≥ 85, B ≥ 65, C ≥ 45, else F, and re-test with `grade = 70`.
- **Variant B — age categories:** `let age = 14; if (age < 13) { console.log("Kid"); } else if (age < 18) { console.log("Teen"); } else { console.log("Adult"); }` → `Teen`

---

## Example 12 — Comparing and Combining Conditions (`&&` and `||`)

**Concept:** `&&` ("and") requires BOTH conditions to be true. `||` ("or") only needs ONE of them to be true.

**Starting code:**
```javascript
let age = 15;
let hasPermission = true;

if (age >= 13 && hasPermission) {
    console.log("You can join the coding club!");
} else {
    console.log("Sorry, you can't join yet.");
}
```

**Expected output:**
```
You can join the coding club!
```

**Explain it simply:** `&&` is like a strict bouncer — it only lets you in if *every* condition checks out. Here, both `age >= 13` (true) and `hasPermission` (true) have to be true for the whole thing to pass.

**Live modifications:**
1. Make one condition false:
   ```javascript
   let hasPermission = false;
   ```
   → Output: `Sorry, you can't join yet.` — even though age is fine, `&&` needs BOTH to be true.
2. Switch `&&` to `||`:
   ```javascript
   if (age >= 13 || hasPermission) {
   ```
   → Now even with `hasPermission = false`, it still passes because age alone satisfies `||`.
3. Make both false:
   ```javascript
   let age = 10;
   let hasPermission = false;
   ```
   → With `||`: still false, since neither condition is true. With `&&`: also false.

**"What if?" questions:**
- "What do you think `&&` needs to print true — one condition or both?"
- "What happens if I change `&&` to `||` but keep both variables the same?"
- "Can someone come up with a real-life example of an 'and' rule and an 'or' rule?"

**Challenge:** Write an `if` statement using `&&` that checks whether someone can go on a school trip — they need `hasPermissionSlip` to be `true` AND `hasPaid` to be `true`.

**Variants to try:**
- **Variant A — `||` with two ways to qualify:** `let hasCoupon = true; let isMember = false; if (hasCoupon || isMember) { console.log("Discount applied!"); }` → prints, because only one of the two needs to be true.
- **Variant B — combining three conditions:** `if (age >= 13 && hasPermission && !isBanned) { console.log("Access granted"); }` — show that `&&` chains work with more than two conditions too.

---

## Example 13 — Array Methods Beginners Can Handle (`includes`, `indexOf`, `join`)

**Concept:** Arrays come with small built-in tools ("methods") that answer common questions without writing a loop.

**Starting code:**
```javascript
let pets = ["dog", "cat", "hamster"];

console.log(pets.includes("cat"));
console.log(pets.indexOf("hamster"));
console.log(pets.join(", "));
```

**Expected output:**
```
true
2
dog, cat, hamster
```

**Explain it simply:** `.includes("cat")` asks "is 'cat' anywhere in this list?" and answers `true`/`false`. `.indexOf("hamster")` asks "what position is 'hamster' at?" (remember, counting starts at 0). `.join(", ")` glues every item into one single string, separated by whatever you put in the parentheses.

**Live modifications:**
1. Search for something not in the list:
   ```javascript
   console.log(pets.includes("fish"));
   console.log(pets.indexOf("fish"));
   ```
   → `false` and `-1` (JavaScript uses `-1` to mean "not found — there's no such index").
2. Change the joiner:
   ```javascript
   console.log(pets.join(" - "));
   ```
   → `dog - cat - hamster`
3. Add a pet and re-check:
   ```javascript
   pets.push("parrot");
   console.log(pets.includes("parrot"));
   ```
   → `true`

**"What if?" questions:**
- "What do you think `.indexOf()` returns when something ISN'T in the array?"
- "What happens if I search for 'Cat' with a capital C instead of 'cat'?" (returns false/-1 — JavaScript is case-sensitive)
- "Can someone predict what `.join('')` with nothing between the quotes would print?"

**Challenge:** Make an array of 4 classmates' names. Use `.includes()` to check if your own name is in it, and `.join(" & ")` to print them all as one sentence.

**Variants to try:**
- **Variant A — `.includes()` on numbers:** `let scores = [70, 85, 90]; console.log(scores.includes(85));` → `true`
- **Variant B — `.join()` on numbers:** `let scores = [70, 85, 90]; console.log(scores.join(" + "));` → `70 + 85 + 90` (a string, not a calculation!)

---

## Example 14 — A Function That Returns a Value

**Concept:** So far our functions only printed things. A function can also `return` a value back to whoever called it, so that value can be stored or reused.

**Starting code:**
```javascript
function addNumbers(a, b) {
    return a + b;
}

let total = addNumbers(4, 6);
console.log(total);
```

**Expected output:**
```
10
```

**Explain it simply:** `return` sends a value back out of the function, like handing someone a result. `addNumbers(4, 6)` doesn't print anything by itself — it hands back `10`, which we catch and store inside `total`. Only then does `console.log(total)` print it.

**Live modifications:**
1. Use the returned value directly without storing it:
   ```javascript
   console.log(addNumbers(4, 6));
   ```
   → Still `10` — no `total` variable needed, but we lose the ability to reuse it later.
2. Use the result in more math:
   ```javascript
   let total = addNumbers(4, 6);
   console.log(total * 2);
   ```
   → `20`
3. Remove the `return` keyword (on purpose, to show the difference):
   ```javascript
   function addNumbers(a, b) {
       a + b;
   }
   let total = addNumbers(4, 6);
   console.log(total);
   ```
   → `undefined` — the function calculated something but never sent it back out.

**"What if?" questions:**
- "What's the difference between a function that `console.log`s something and one that `return`s something?"
- "What do you think happens if I remove the word `return`?"
- "Can someone predict what `addNumbers(4, 6) * 2` prints directly, without a variable?"

**Challenge:** Write a function `multiply(a, b)` that returns the product of two numbers, then use its result inside another calculation, like `multiply(3, 4) + 10`.

**Variants to try:**
- **Variant A — return a boolean:** `function isPassing(score) { return score >= 50; } console.log(isPassing(70));` → `true`
- **Variant B — return a string:** `function greet(name) { return "Hello, " + name + "!"; } console.log(greet("Zara"));` → `Hello, Zara!`

---

## Example 15 — Nested Loops and Arrays (a Bit More Challenging)

**Concept:** A loop can be placed inside another loop — the inner loop finishes completely before the outer loop moves to its next step. This is useful for going through a "list of lists."

**Starting code:**
```javascript
let teams = [
    ["Alex", "Sam"],
    ["Jordan", "Casey"]
];

for (let i = 0; i < teams.length; i++) {
    console.log("Team " + (i + 1) + ":");
    for (let j = 0; j < teams[i].length; j++) {
        console.log("  - " + teams[i][j]);
    }
}
```

**Expected output:**
```
Team 1:
  - Alex
  - Sam
Team 2:
  - Jordan
  - Casey
```

**Explain it simply:** `teams` is an array where each item is itself another array (a "team" of names). The outer loop walks through each team; for every team, the inner loop walks through each name inside it. Think of it as a loop for the folders, and inside each folder, a loop for the files.

**Live modifications:**
1. Add a third team:
   ```javascript
   let teams = [
       ["Alex", "Sam"],
       ["Jordan", "Casey"],
       ["Priya", "Liam", "Noah"]
   ];
   ```
   → A "Team 3" section appears automatically, and it correctly lists all 3 names since the inner loop uses `teams[i].length`, not a fixed number.
2. Change the inner loop to count members instead of listing them:
   ```javascript
   console.log("Team " + (i + 1) + " has " + teams[i].length + " members");
   ```
3. Try printing just the first person of every team (no inner loop needed):
   ```javascript
   for (let i = 0; i < teams.length; i++) {
       console.log(teams[i][0]);
   }
   ```

**"What if?" questions:**
- "What do you think happens if one team has 3 people and another only has 2 — does the code still work?"
- "What happens if I swap `i` and `j` inside `teams[i][j]`?" (likely an error or wrong result — great for showing how easy this mix-up is)
- "Can someone predict how many total lines of output there will be before I run it?"

**Challenge:** Create your own array of 3 teams (each with 2–3 names), then print every name across all teams using the nested loop pattern above.

**Variants to try:**
- **Variant A — a small multiplication table:** nest a loop from 1–3 inside a loop from 1–3, printing `i + " x " + j + " = " + (i * j)` for each pair.
- **Variant B — only print the FIRST person of every team:** `for (let i = 0; i < teams.length; i++) { console.log(teams[i][0]); }` — no inner loop needed at all, which is a nice contrast to show inner loops aren't always required.

---

## Example 16 — Template Literals (Backticks)

**Concept:** Template literals are a cleaner way to combine text and variables — using backticks `` ` `` and `${ }` instead of lots of `+` signs.

**Starting code:**
```javascript
let name = "Zara";
let age = 15;
console.log(`My name is ${name} and I am ${age} years old.`);
```

**Expected output:**
```
My name is Zara and I am 15 years old.
```

**Explain it simply:** Backticks let you write a sentence normally, and drop variables straight into it using `${ }` — no more gluing pieces together with `+`. It's the same result as `"My name is " + name + " and I am " + age + " years old."`, just easier to read.

**Live modifications:**
1. Change a variable:
   ```javascript
   let name = "Kofi";
   ```
   → Output becomes `My name is Kofi and I am 15 years old.`
2. Add a calculation inside `${ }`:
   ```javascript
   console.log(`Next year I will be ${age + 1}.`);
   ```
   → Output: `Next year I will be 16.`
3. Compare it to the old way side by side:
   ```javascript
   console.log("My name is " + name + " and I am " + age + " years old.");
   console.log(`My name is ${name} and I am ${age} years old.`);
   ```
   → Both lines print the exact same thing — just written differently.

**"What if?" questions:**
- "What do you think happens if I put math, like `${age * 2}`, inside the backticks?"
- "What happens if I forget the `$` and just use `{name}`?" (it prints the literal text `{name}`, not the variable)
- "Which version — `+` or backticks — do you find easier to read?"

**Challenge:** Using backticks, print a sentence combining your name, your age, and your favorite subject, all in one line.

**Variants to try:**
- **Variant A — a multi-line message:** backticks can span multiple lines directly, unlike regular quotes — try writing a 2-line message inside one pair of backticks.
- **Variant B — combine with a function:**
  ```javascript
  function intro(name) {
      return `Hi, I'm ${name}!`;
  }
  console.log(intro("Lea"));
  ```
  → `Hi, I'm Lea!`

---

## Example 17 — The `switch` Statement

**Concept:** `switch` is another way to check one value against several possibilities — a tidy alternative to a long chain of `else if`s when you're comparing the exact same variable each time.

**Starting code:**
```javascript
let day = "Tuesday";

switch (day) {
    case "Monday":
        console.log("Start of the week!");
        break;
    case "Tuesday":
        console.log("Getting into it.");
        break;
    case "Friday":
        console.log("Almost the weekend!");
        break;
    default:
        console.log("Just a regular day.");
}
```

**Expected output:**
```
Getting into it.
```

**Explain it simply:** `switch` compares `day` against each `case` in order. When it finds a match, it runs that block and then `break` stops it from checking any further cases. `default` is the "none of the above" fallback — just like the final `else`.

**Live modifications:**
1. Change the day:
   ```javascript
   let day = "Friday";
   ```
   → Output: `Almost the weekend!`
2. Use a day with no matching case:
   ```javascript
   let day = "Sunday";
   ```
   → Output: `Just a regular day.` (falls through to `default`)
3. Remove a `break` on purpose (to show why it matters):
   ```javascript
   case "Monday":
       console.log("Start of the week!");
       // break; removed
   case "Tuesday":
       console.log("Getting into it.");
       break;
   ```
   → With `day = "Monday"`, it now prints BOTH messages — removing `break` lets it "fall through" into the next case.

**"What if?" questions:**
- "What do you think happens if none of the cases match?"
- "What happens if I remove a `break` — can anyone guess before we try it?"
- "Could this same logic be written with `if`/`else if`? Which do you prefer?"

**Challenge:** Write a `switch` statement on a variable `favoriteColor` with at least 3 cases and a `default`.

**Variants to try:**
- **Variant A — numbers instead of strings:** `switch (grade) { case 1: ... case 2: ... }` using a number variable instead of text.
- **Variant B — grouped cases:** two `case` lines stacked with no code between them (e.g. `case "Saturday": case "Sunday": console.log("Weekend!"); break;`) to match multiple values with one block.

---

## Example 18 — The `while` Loop

**Concept:** A `while` loop repeats code as long as a condition stays true — similar to a `for` loop, but the counter is managed by hand instead of built into one line.

**Starting code:**
```javascript
let count = 0;

while (count < 3) {
    console.log("Count is " + count);
    count = count + 1;
}
```

**Expected output:**
```
Count is 0
Count is 1
Count is 2
```

**Explain it simply:** JavaScript checks `count < 3` before every lap. If it's `true`, it runs the code inside `{ }`, including the line that increases `count`. Once `count` reaches 3, `3 < 3` is `false`, so the loop stops.

**Live modifications:**
1. Change the limit:
   ```javascript
   while (count < 6) {
   ```
   → Now it counts all the way up to 5.
2. Start the counter somewhere else:
   ```javascript
   let count = 2;
   ```
   → Now it only prints `Count is 2`.
3. Remove the line that increases `count` (careful — explain this BEFORE running it):
   ```javascript
   while (count < 3) {
       console.log("Count is " + count);
       // count = count + 1; removed
   }
   ```
   → This creates an infinite loop, because `count` never changes and stays less than 3 forever. Explain why this is risky rather than actually running it live.

**"What if?" questions:**
- "What's different between how a `for` loop and a `while` loop keep count?"
- "What do you think happens if we forget to increase `count` inside the loop?" (infinite loop — don't run it live!)
- "Could every `for` loop we've written also be written as a `while` loop?"

**Challenge:** Write a `while` loop that prints "Still going!" 4 times.

**Variants to try:**
- **Variant A — counting down:** `let count = 5; while (count > 0) { console.log(count); count = count - 1; }` → prints `5, 4, 3, 2, 1`.
- **Variant B — a while loop searching an array:** use `while` with an index variable to print items of an array one at a time, stopping when the index reaches `array.length`.

---

## Example 19 — Useful String Methods (`slice`, `trim`, `replace`)

**Concept:** Beyond `.length` and `.toUpperCase()`, strings have more built-in methods for grabbing parts of text, cleaning it up, or swapping words.

**Starting code:**
```javascript
let message = "  Hello World  ";

console.log(message.trim());
console.log(message.trim().slice(0, 5));
console.log(message.replace("World", "Class"));
```

**Expected output:**
```
Hello World
Hello
  Hello Class  
```

**Explain it simply:** `.trim()` removes extra spaces from the start and end. `.slice(0, 5)` grabs characters from position 0 up to (but not including) position 5. `.replace("World", "Class")` swaps the first matching piece of text for another.

**Live modifications:**
1. Change the slice range:
   ```javascript
   console.log(message.trim().slice(6, 11));
   ```
   → Output: `World`
2. Replace a different word:
   ```javascript
   console.log(message.replace("Hello", "Hi"));
   ```
   → Output: `  Hi World  `
3. Chain multiple methods together:
   ```javascript
   console.log(message.trim().toUpperCase());
   ```
   → Output: `HELLO WORLD`

**"What if?" questions:**
- "What do you think `.slice(0, 5)` grabs — the first 5 characters, or up to the 5th?"
- "What happens if I don't call `.trim()` first — do the extra spaces mess up `.slice()`?"
- "Can someone predict what chaining `.trim()` and `.toUpperCase()` together will do?"

**Challenge:** Take a messy string like `"   javascript is fun   "`, trim it, and print just the first 10 characters using `.slice()`.

**Variants to try:**
- **Variant A — `.replace()` with your own name:** replace a placeholder name in a sentence with your own, e.g. `"Hello NAME!".replace("NAME", "Zara")`.
- **Variant B — `.slice()` with negative numbers:** `console.log("Hello World".slice(-5));` → `World` — negative numbers count backwards from the end.

---

## Example 20 — Combining Arrays and Objects

**Concept:** Arrays can hold objects, not just strings and numbers — this is how real programs store lists of "things" (students, products, messages) that each have multiple properties.

**Starting code:**
```javascript
let students = [
    { name: "Zara", grade: 90 },
    { name: "Kofi", grade: 75 },
    { name: "Lea", grade: 60 }
];

for (let i = 0; i < students.length; i++) {
    console.log(students[i].name + ": " + students[i].grade);
}
```

**Expected output:**
```
Zara: 90
Kofi: 75
Lea: 60
```

**Explain it simply:** `students` is an array of 3 objects. Each object has a `name` property and a `grade` property. The loop visits each object one at a time (`students[i]`), then reads its properties with a dot (`.name`, `.grade`) — combining everything we've learned about arrays, objects, loops, and dot notation into one example.

**Live modifications:**
1. Add a 4th student to the array:
   ```javascript
   { name: "Tomi", grade: 88 }
   ```
   → The loop automatically includes them — no other code changes needed.
2. Add pass/fail logic inside the loop:
   ```javascript
   for (let i = 0; i < students.length; i++) {
       if (students[i].grade >= 70) {
           console.log(students[i].name + " passed!");
       } else {
           console.log(students[i].name + " needs to retake it.");
       }
   }
   ```
   → Combines objects, arrays, loops, AND `if`/`else` all in one place.
3. Print just the names, not the grades:
   ```javascript
   console.log(students[i].name);
   ```

**"What if?" questions:**
- "What do you think `students[0].grade` would print, without a loop at all?"
- "What happens if one object is missing the `grade` property?" (prints `undefined` for that one)
- "Can someone predict the full output if we add a 4th student with a failing grade?"

**Challenge:** Create your own array of 3 objects representing your favorite movies, each with a `title` and a `rating` property, then loop through and print `"<title> — rated <rating>"` for each one.

**Variants to try:**
- **Variant A — objects with 3 properties instead of 2:** add a `subject: "Math"` property to each student object and print it alongside name and grade.
- **Variant B — finding the highest grade:** track a `highest` variable while looping, updating it with `if (students[i].grade > highest)`, to find the top student by the end of the loop.

