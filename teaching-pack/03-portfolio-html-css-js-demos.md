# Part 3 — HTML + CSS + JavaScript Portfolio Interactions

This section is **completely separate** from Part 2. Part 2 taught pure JavaScript. This part shows JavaScript **controlling a real webpage** — the instructor's own portfolio site (`index.html`, `css/style.css`, `js/script.js`).

**Runnable files:** every demo below also exists as an actual, openable set of files in [`portfolio-demos/`](portfolio-demos/) — one folder per demo, each a full working copy of the real site plus that demo's JavaScript already wired up to a "▶ Run Demo" button. Open any folder's `index.html` straight in a browser (no server needed) to show it live, then edit its `js/demo.js` in front of the class. See [`portfolio-demos/README.md`](portfolio-demos/README.md) for the folder map.

**Big idea to repeat throughout:** HTML creates the element → CSS styles the element → JavaScript makes the element interactive.

Students' own websites will have different HTML — that's fine. For every demo, the underlying *concept* (find an element, then do something to it) works the same no matter what the element is called.

---

## Demo 1 — Change Text on the Page

**This JavaScript is interacting with this HTML element:** the `<h1>` inside the `#home` section.

**Relevant HTML** (in `index.html`, inside `<section id="home">`):
```html
<h1>Ben Carter</h1>
```

**Relevant JavaScript** (type this into the browser console while the site is open):
```javascript
document.querySelector("#home h1").textContent = "Hello everyone!";
```

**How JavaScript finds the element:** `document.querySelector("#home h1")` searches the whole page for an `<h1>` that lives inside the element with `id="home"`. It returns that one element.

**Result:** The big heading on the page instantly changes from "Ben Carter" to "Hello everyone!" — no page reload needed.

**Live modifications:**
- Change the text to your own name: `.textContent = "Welcome to my site!"`
- Try `.textContent = ""` — the heading disappears (empty text is still valid text).
- Swap `.textContent` for `.innerHTML = "<em>Hello everyone!</em>"` to show HTML tags can be injected too (briefly mention this is more powerful but also riskier — save for a later lesson).

**How students apply this to their own site:** Any heading, paragraph, or button label can be targeted the same way — they just need to know its `id`, `class`, or tag name and use `document.querySelector(...)` or `document.getElementById(...)`.

---

## Demo 2 — Button Click Interaction

**This JavaScript is interacting with this HTML element:** the "View My Work" button in the hero section.

**Relevant HTML** (inside `.hero-actions`):
```html
<a href="#projects" class="btn btn-primary">View My Work</a>
```

**Relevant JavaScript:**
```javascript
document.querySelector(".btn-primary").addEventListener("click", function () {
    alert("Thanks for checking out my projects!");
});
```

**How JavaScript finds the element:** `.btn-primary` is a CSS class already on the button, so `document.querySelector(".btn-primary")` grabs it. `addEventListener("click", ...)` tells the browser "run this function whenever someone clicks this element."

**Result:** Clicking the button now pops up a message *in addition to* jumping down to the Projects section.

**Live modifications:**
- Change the alert text.
- Swap `alert(...)` for `console.log(...)` to show a quieter version of the same idea.
- Attach the listener to `.btn-secondary` ("Get In Touch") instead, to show the same code pattern works on a different button.

**How students apply this to their own site:** Any button or link on their page can react to clicks the same way — find it, then `addEventListener("click", ...)`.

---

## Demo 3 — Show / Hide the About Section

**This JavaScript is interacting with this HTML element:** the paragraph inside `#about`.

**Relevant HTML:**
```html
<section id="about" class="section">
  <h2 class="section-title">About Me</h2>
  <p class="section-text">...</p>
</section>
```

**Relevant JavaScript:**
```javascript
document.querySelector(".section-text").style.display = "none";
```

then to bring it back:
```javascript
document.querySelector(".section-text").style.display = "block";
```

**How JavaScript finds the element:** `.section-text` is the class on the About paragraph, so `querySelector` grabs the first match on the page.

**Result:** The paragraph disappears completely from the layout (not just invisible — the space it took up collapses too), then reappears when set back to `"block"`.

**Live modifications:**
- Build a toggle instead of two separate lines:
  ```javascript
  let text = document.querySelector(".section-text");
  text.style.display = text.style.display === "none" ? "none" : "none";
  ```
  (Simplify for beginners — better to show the two-line version above, or the `classList.toggle` version in Demo 4.)
- Try hiding `.skills-list` instead, to prove the same trick works on any element.

**How students apply this to their own site:** Any section, image, or paragraph can be shown/hidden the same way — this is the foundation for menus, "read more" buttons, and collapsible FAQs.

---

## Demo 4 — Change Styles with JavaScript (and why we use classes instead)

**This JavaScript is interacting with this HTML element:** the `<h1>` in `#home`, and the CSS variables in `:root`.

**Relevant HTML:**
```html
<h1>Ben Carter</h1>
```

**Relevant CSS** (`css/style.css`):
```css
:root {
  --color-accent: #2f6fed;
}
```

**Relevant JavaScript — the "quick and messy" way:**
```javascript
document.querySelector("#home h1").style.color = "red";
document.querySelector("#home h1").style.fontSize = "80px";
```

**Relevant JavaScript — the better way (add/remove a class instead):**
```css
/* add this rule to style.css first */
.highlight {
  color: red;
  font-size: 80px;
}
```
```javascript
document.querySelector("#home h1").classList.add("highlight");
```

**How JavaScript finds the element:** same `querySelector` as Demo 1. `.style.color` sets one CSS property directly; `.classList.add("highlight")` instead turns *on* a whole CSS class that was already defined in the stylesheet.

**Result:** Both approaches turn the heading red and huge — but the class version keeps all the styling *rules* inside CSS, where they belong, and JavaScript's only job is deciding *when* to apply them.

**Live modifications:**
- Toggle it back off: `.classList.remove("highlight")`
- Use `.classList.toggle("highlight")` so one line switches it on AND off each time it runs.
- Point out `--color-accent` in the CSS and explain that changing that one variable would change the accent color everywhere on the site — a preview of Demo 5.

**How students apply this to their own site:** Direct `.style.x = ...` is fine for quick experiments, but the professional habit is: write the *look* in CSS as a class, then let JavaScript flip that class on and off.

---

## Demo 5 — Simple Dark / Light Mode Toggle

The portfolio doesn't have a theme toggle yet — this is a live "let's build it together" exercise.

**This JavaScript will interact with this HTML element:** the whole page (`document.body`), plus new CSS we add.

**Step 1 — add a "dark mode" rule to `css/style.css`:**
```css
body.dark-mode {
  --color-bg: #1f2430;
  --color-text: #ffffff;
}
```

**Step 2 — add a button to `index.html`** (anywhere in the header is fine):
```html
<button id="themeToggle">🌙 Dark Mode</button>
```

**Step 3 — the JavaScript** (`js/script.js`):
```javascript
document.getElementById("themeToggle").addEventListener("click", function () {
    document.body.classList.toggle("dark-mode");
});
```

**How JavaScript finds the element:** `getElementById("themeToggle")` grabs the new button by its `id`. Clicking it toggles a class on `<body>` — same `classList.toggle` idea from Demo 4, just applied to the whole page instead of one heading.

**Result:** Clicking the button switches the page's background and text color instantly, because the CSS variables (`--color-bg`, `--color-text`) that every element already uses get overridden.

**Live modifications:**
- Change the button text to switch too: `this.textContent = document.body.classList.contains("dark-mode") ? "☀️ Light Mode" : "🌙 Dark Mode";`
- Add more variables to the `.dark-mode` rule (e.g. `--color-accent`) to change more colors at once.

**How students apply this to their own site:** This is the key lesson — **JavaScript doesn't do the styling itself.** It just adds or removes a class; CSS decides what that class actually looks like. Any student can copy this exact three-step pattern on their own site regardless of their HTML structure.

---

## Demo 6 — Project Card Interaction

**This JavaScript is interacting with this HTML element:** the three `.card` elements inside `#projects .grid`.

**Relevant HTML** (one of three cards):
```html
<article class="card">
  <h3>Landing Page Redesign</h3>
  <p>...</p>
  <a href="#" class="card-link">View Project →</a>
</article>
```

**Relevant JavaScript:**
```javascript
document.querySelectorAll(".card").forEach(function (card) {
    card.addEventListener("click", function () {
        alert("You clicked: " + card.querySelector("h3").textContent);
    });
});
```

**How JavaScript finds the element:** `querySelectorAll(".card")` grabs *all three* project cards as a list. `.forEach` runs the same code on each one, attaching a click listener to every card individually.

**Result:** Clicking any project card pops up an alert naming that specific project — the code figures out *which* card was clicked using `card.querySelector("h3")` inside the listener.

**Live modifications:**
- Instead of `alert`, change the card's own text: `card.querySelector("p").textContent = "Thanks for your interest!"`
- Add a `.selected` CSS class and highlight whichever card was last clicked: `card.classList.add("selected")` (remove it from the others first).

**How students apply this to their own site:** Any repeated group of elements — cards, list items, images — can be looped over with `querySelectorAll` + `forEach`, and each one gets its own working click behavior automatically.

---

## Demo 7 — Simple Contact Form Interaction

**This JavaScript is interacting with this HTML element:** `#contactForm` and its inputs `#name`, `#email`, `#message`.

**Relevant HTML:**
```html
<form class="contact-form" id="contactForm">
  <label for="name">Name</label>
  <input type="text" id="name" name="name" placeholder="Your name" required />

  <label for="email">Email</label>
  <input type="email" id="email" name="email" placeholder="you@example.com" required />

  <label for="message">Message</label>
  <textarea id="message" name="message" rows="4" placeholder="Say hello..." required></textarea>

  <button type="submit" class="btn btn-primary">Send Message</button>
  <p class="form-note" id="formNote"></p>
</form>
```

**Relevant JavaScript (this already exists in `js/script.js`):**
```javascript
const contactForm = document.getElementById('contactForm');
const formNote = document.getElementById('formNote');

contactForm.addEventListener('submit', (event) => {
  event.preventDefault();
  formNote.textContent = "Thanks! This is a demo form — hook it up to a real service to receive messages.";
  contactForm.reset();
});
```

**How JavaScript finds the element:** `getElementById('contactForm')` grabs the whole form; `event.preventDefault()` stops the browser's normal "reload the page" behavior so JavaScript can handle the submission instead.

**Result:** Clicking "Send Message" shows a friendly note and clears the form — without actually sending anything anywhere (there's no backend, which is fine — explain that's a topic for later).

**Live modifications (beginner-safe extra check):**
```javascript
contactForm.addEventListener('submit', (event) => {
  event.preventDefault();

  if (document.getElementById('name').value === "") {
      formNote.textContent = "Please enter your name first!";
  } else {
      formNote.textContent = "Thanks for reaching out!";
      contactForm.reset();
  }
});
```
- Change the empty-name message.
- Add a second check for `#email` using the same `if` pattern (`&&` optional, keep it simple — two separate `if` statements is fine for beginners).

**How students apply this to their own site:** `.value` reads whatever the user typed into an input. Combined with the `if`/`else` from Part 2, students can build simple "did they fill this in?" checks on any form — no server needed. **Do not** introduce real backend validation or data storage here; keep it front-end only.

---

## Demo 8 — Navigation / Hamburger Menu Interaction

**This JavaScript is interacting with this HTML element:** `#navToggle` (the hamburger button) and `#navLinks` (the menu list).

**Relevant HTML:**
```html
<button class="nav-toggle" id="navToggle" aria-label="Toggle menu" aria-expanded="false">
  <span></span><span></span><span></span>
</button>
<ul class="nav-links" id="navLinks">
  <li><a href="#home">Home</a></li>
  ...
</ul>
```

**Relevant JavaScript (this already exists in `js/script.js`):**
```javascript
const navToggle = document.getElementById('navToggle');
const navLinks = document.getElementById('navLinks');

navToggle.addEventListener('click', () => {
  const isOpen = navLinks.classList.toggle('open');
  navToggle.setAttribute('aria-expanded', isOpen);
});
```

**How JavaScript finds the element:** both elements are grabbed by their `id`. `classList.toggle('open')` adds the `open` class if it's missing, or removes it if it's already there — and it *returns* `true`/`false` telling us which happened, which gets saved into `isOpen`.

**Result:** On a narrow/mobile screen, clicking the hamburger button reveals the nav menu (`.open` triggers a CSS rule that expands it); clicking again hides it. `aria-expanded` is updated too, which helps screen readers know the menu's state.

**Live modifications:**
- Shrink the browser window (or open dev tools' device toolbar) so the hamburger button appears, then click it live in front of the class.
- Temporarily comment out the `.classList.toggle('open')` line and show that clicking the button now does nothing — proving that line is what makes the menu open.
- Add `console.log(isOpen)` inside the listener so students see `true`/`false` printed each click.

**How students apply this to their own site:** Any show/hide toggle (menus, dropdowns, accordions) follows this exact three-part pattern: find the button, find the thing to show/hide, toggle a class between them on click.

---

## Appendix — Full Source Files (for reference during teaching)

These are the complete, current contents of the three files that make up the portfolio, exactly as they exist in the project right now. Every demo above pulls from these files — use this appendix if you need to see a piece of code in its full surrounding context, or want to open the real file on screen and point at the matching lines.

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ben Carter — Portfolio</title>
  <link rel="stylesheet" href="css/style.css" />
</head>
<body>
  <header class="site-header">
    <nav class="nav container">
      <a href="#home" class="logo">Ben Carter</a>
      <button class="nav-toggle" id="navToggle" aria-label="Toggle menu" aria-expanded="false">
        <span></span>
        <span></span>
        <span></span>
      </button>
      <ul class="nav-links" id="navLinks">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section id="home" class="hero">
      <div class="container hero-content">
        <p class="eyebrow">Hello, I'm</p>
        <h1>Ben Carter</h1>
        <p class="tagline">Former Sales Rep, Now Chasing Semicolons — Front-End Developer in the Making</p>
        <div class="hero-actions">
          <a href="#projects" class="btn btn-primary">View My Work</a>
          <a href="#contact" class="btn btn-secondary">Get In Touch</a>
        </div>
      </div>
    </section>

    <section id="about" class="section">
      <div class="container">
        <h2 class="section-title">About Me</h2>
        <p class="section-text">
          Placeholder bio: I spent five years exceeding quota and closing deals before trading cold
          calls for cold brews and console logs. These days I build clean, friendly web experiences
          and I'm still weirdly good at follow-up emails. Swap this paragraph out with your real story.
        </p>
      </div>
    </section>

    <section id="projects" class="section section-alt">
      <div class="container">
        <h2 class="section-title">Projects</h2>
        <div class="grid">
          <article class="card">
            <h3>Landing Page Redesign</h3>
            <p>Placeholder: A responsive marketing landing page built with HTML, CSS, and a sprinkle of JS.</p>
            <a href="#" class="card-link">View Project →</a>
          </article>
          <article class="card">
            <h3>Quote Tracker App</h3>
            <p>Placeholder: A small tool for tracking sales quotes, rebuilt as a personal coding exercise.</p>
            <a href="#" class="card-link">View Project →</a>
          </article>
          <article class="card">
            <h3>Portfolio Site</h3>
            <p>Placeholder: This very site — built from scratch to practice layout and responsive design.</p>
            <a href="#" class="card-link">View Project →</a>
          </article>
        </div>
      </div>
    </section>

    <section id="skills" class="section">
      <div class="container">
        <h2 class="section-title">Skills</h2>
        <ul class="skills-list">
          <li>HTML</li>
          <li>CSS</li>
          <li>JavaScript</li>
          <li>Git &amp; GitHub</li>
          <li>Responsive Design</li>
          <li>Figma</li>
          <li>Excel Wizardry</li>
          <li>Cold Emails (retired)</li>
        </ul>
      </div>
    </section>

    <section id="contact" class="section section-alt">
      <div class="container">
        <h2 class="section-title">Contact</h2>
        <p class="section-text">Interested in working together? Reach out below.</p>
        <div class="contact-wrapper">
          <ul class="contact-links">
            <li><a href="mailto:ben.carter@example.com">ben.carter@example.com</a></li>
            <li><a href="#">github.com/bencarter</a></li>
            <li><a href="#">linkedin.com/in/bencarter</a></li>
          </ul>
          <form class="contact-form" id="contactForm">
            <label for="name">Name</label>
            <input type="text" id="name" name="name" placeholder="Your name" required />

            <label for="email">Email</label>
            <input type="email" id="email" name="email" placeholder="you@example.com" required />

            <label for="message">Message</label>
            <textarea id="message" name="message" rows="4" placeholder="Say hello..." required></textarea>

            <button type="submit" class="btn btn-primary">Send Message</button>
            <p class="form-note" id="formNote"></p>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container">
      <p>&copy; <span id="year"></span> Ben Carter. All rights reserved.</p>
    </div>
  </footer>

  <script src="js/script.js"></script>
</body>
</html>
```

### `js/script.js`

```javascript
// Mobile nav toggle
const navToggle = document.getElementById('navToggle');
const navLinks = document.getElementById('navLinks');

navToggle.addEventListener('click', () => {
  const isOpen = navLinks.classList.toggle('open');
  navToggle.setAttribute('aria-expanded', isOpen);
});

navLinks.querySelectorAll('a').forEach((link) => {
  link.addEventListener('click', () => {
    navLinks.classList.remove('open');
    navToggle.setAttribute('aria-expanded', 'false');
  });
});

// Highlight active nav link based on scroll position
const sections = document.querySelectorAll('main section[id]');
const navAnchors = document.querySelectorAll('.nav-links a');

const setActiveLink = () => {
  let currentId = '';
  const scrollPos = window.scrollY + 100;

  sections.forEach((section) => {
    if (scrollPos >= section.offsetTop) {
      currentId = section.id;
    }
  });

  navAnchors.forEach((anchor) => {
    anchor.classList.toggle('active', anchor.getAttribute('href') === `#${currentId}`);
  });
};

window.addEventListener('scroll', setActiveLink);
setActiveLink();

// Footer year
document.getElementById('year').textContent = new Date().getFullYear();

// Contact form (front-end only, no real submission)
const contactForm = document.getElementById('contactForm');
const formNote = document.getElementById('formNote');

contactForm.addEventListener('submit', (event) => {
  event.preventDefault();
  formNote.textContent = "Thanks! This is a demo form — hook it up to a real service to receive messages.";
  contactForm.reset();
});
```

### `css/style.css` (key parts relevant to the demos above — full file has more layout/spacing rules)

```css
:root {
  --color-bg: #ffffff;
  --color-bg-alt: #f6f7f9;
  --color-text: #1f2430;
  --color-text-muted: #5b6472;
  --color-accent: #2f6fed;
  --color-accent-dark: #244fb0;
  --color-border: #e4e7ec;
  --max-width: 1080px;
  --radius: 10px;
  --transition: 0.2s ease;
}

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  color: var(--color-text);
  background: var(--color-bg);
  line-height: 1.6;
}

.btn-primary {
  background: var(--color-accent);
  color: #fff;
}

.card {
  background: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  padding: 24px;
  transition: transform var(--transition), box-shadow var(--transition);
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 24px rgba(31, 36, 48, 0.08);
}

/* Mobile nav — this is what Demo 8's JavaScript is switching on and off */
.nav-toggle {
  display: none; /* hidden on wide screens */
}

@media (max-width: 720px) {
  .nav-toggle {
    display: flex; /* hamburger button appears on narrow screens */
  }

  .nav-links {
    position: absolute;
    top: 64px;
    left: 0;
    right: 0;
    background: var(--color-bg);
    flex-direction: column;
    gap: 0;
    border-bottom: 1px solid var(--color-border);
    max-height: 0;      /* menu is collapsed by default */
    overflow: hidden;
    transition: max-height var(--transition);
  }

  .nav-links.open {
    max-height: 300px;  /* JavaScript adds the .open class to reveal it */
  }
}
```

**Note for Demo 5 (dark/light mode):** the `--color-bg`, `--color-text`, etc. variables above are the exact ones a `body.dark-mode { --color-bg: ...; }` rule would override — every element on the page already reads its colors from these variables, so overriding them in one place changes the whole site at once.
