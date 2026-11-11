# EduBoost Bootstrap Template

A beginner-friendly website template for learning **Bootstrap 5.3.3**. It works fully offline, so you do not need internet or a server. Just open it in your browser.

**Pages included:** Home, Login, Sign Up, Dashboard.

> Full guide: [Bootstrap Student Guide (Word)](docs/Bootstrap_Student_Guide.docx)

---

## Table of Contents

1. [What is Bootstrap?](#1-what-is-bootstrap)
2. [Quick Start](#2-quick-start)
3. [Project Structure](#3-project-structure)
4. [How Bootstrap Works (Key Words)](#4-how-bootstrap-works-key-words)
5. [Step-by-Step: Build Your Own Project](#5-step-by-step-build-your-own-project)
6. [Where to Use What (Cheat Sheet)](#6-where-to-use-what-cheat-sheet)
7. [Practice Exercises](#7-practice-exercises)
8. [Common Mistakes and Fixes](#8-common-mistakes-and-fixes)
9. [Helpful Links](#9-helpful-links)
10. [Credits](#10-credits)

---

## 1. What is Bootstrap?

**Bootstrap** is a free collection of ready-made CSS and JavaScript. Instead of writing all the CSS yourself, you add **class names** to your HTML and Bootstrap styles it for you.

Example:

```html
<button class="btn btn-primary">Click me</button>
```

`btn` and `btn-primary` are Bootstrap classes. They turn a plain button into a blue, rounded, styled button.

**Why use it?**
- Saves time: buttons, forms, menus and cards are already designed.
- Responsive: pages look good on phones, tablets and computers.
- Consistent: everything shares one look.

---

## 2. Quick Start

1. Download or clone this project to your computer.
2. Open the folder in **VS Code** (or any code editor).
3. Double-click `index.html` to open it in your browser.
4. Click through the pages: Home, Login, Sign Up, Dashboard.
5. Change something in the code, save, and **refresh the browser** to see the result.

Tip: In VS Code, the **Live Server** extension refreshes the page for you automatically.

---

## 3. Project Structure

```
bootstrap-template/
├── index.html               Home page
├── pages/
│   ├── login.html           Login page
│   ├── signup.html          Sign up page
│   └── dashboard.html       Student dashboard
├── assets/
│   ├── css/
│   │   ├── bootstrap.min.css        Bootstrap styles (do NOT edit)
│   │   ├── bootstrap-icons.min.css  Icon styles (do NOT edit)
│   │   ├── fonts/                   Icon fonts
│   │   └── style.css                YOUR custom styles (edit this one)
│   ├── js/
│   │   └── bootstrap.bundle.min.js  Bootstrap JavaScript (do NOT edit)
│   └── images/                      Photos and favicon
├── docs/
│   └── Bootstrap_Student_Guide.docx
└── README.md
```

**Rule of thumb:** Edit the HTML files and `style.css`. Do not edit files ending in `.min.css` or `.min.js`.

---

## 4. How Bootstrap Works (Key Words)

| Word | Simple meaning | Example |
|------|----------------|---------|
| **Class** | A name you add to an HTML tag to style it | `class="btn"` |
| **Component** | A ready-made piece of UI (navbar, card, modal) | `class="card"` |
| **Utility** | A small class that does one job (spacing, color, alignment) | `mt-3`, `text-center` |
| **Container** | The box that holds your page content and sets side margins | `class="container"` |
| **Grid** | A layout system of 12 columns per row | `row` and `col-md-6` |
| **Breakpoint** | A screen width where the layout changes | `md` = 768px and wider |
| **Responsive** | Layout adapts to screen size | Columns stack on phones |
| **CDN** | A website that hosts Bootstrap files online (not used here, we use local files) | |

### The Grid in 30 seconds

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Left half</div>
    <div class="col-md-6">Right half</div>
  </div>
</div>
```

- A row has **12 columns**.
- `col-md-6` means "take 6 of 12 columns (half) on medium screens and up".
- On small screens (phones), columns stack on top of each other.

### Breakpoints

| Prefix | Screen width | Device |
|--------|--------------|--------|
| (none) | under 576px | Phone |
| `sm` | 576px and up | Large phone |
| `md` | 768px and up | Tablet |
| `lg` | 992px and up | Laptop |
| `xl` | 1200px and up | Desktop |

---

## 5. Step-by-Step: Build Your Own Project

Follow these steps to turn the template into your own project.

### Step 1: Copy the template
Copy the whole `bootstrap-template` folder and rename it (for example `my-portfolio`).

### Step 2: Change the site name and title
In each HTML file, find and change:
- `<title>EduBoost | Home</title>` to your own title.
- `EduBoost` in the navbar and footer to your project name.

### Step 3: Make a new page
1. Copy `pages/login.html` and rename it, for example `pages/about.html`.
2. Delete the content inside `<body>`, but keep the `<script>` line at the bottom.
3. Keep the `<link>` lines in `<head>`. They load Bootstrap.
4. Add your own content, or copy the navbar from `index.html` (remember to fix its link paths).

### Step 4: Check your file paths
Paths depend on where the page is:

| Page location | CSS path |
|---------------|----------|
| Main folder (`index.html`) | `assets/css/bootstrap.min.css` |
| Inside `pages/` | `../assets/css/bootstrap.min.css` |

`../` means "go up one folder".

Every page needs these lines (use `../` if the page is inside `pages/`):

```html
<!-- In <head> -->
<link href="assets/css/bootstrap.min.css" rel="stylesheet">
<link href="assets/css/bootstrap-icons.min.css" rel="stylesheet">
<link href="assets/css/style.css" rel="stylesheet">

<!-- Right before </body> -->
<script src="assets/js/bootstrap.bundle.min.js"></script>
```

Also keep this line in `<head>`. It makes the page work on phones:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Step 5: Add a navbar link to your new page
In the navbar, add one line inside the `<ul class="navbar-nav">`:

```html
<li class="nav-item"><a class="nav-link" href="pages/about.html">About</a></li>
```

### Step 6: Add a component from the Bootstrap docs
1. Go to <https://getbootstrap.com/docs/5.3/components/card/>.
2. Copy the example code.
3. Paste it into your page inside the `<body>`.
4. Save and refresh the browser.

Do **not** copy the CDN `<link>` or `<script>` lines from the docs. This project already loads Bootstrap locally.

### Step 7: Change colors and style
- Use Bootstrap color classes: `btn-success`, `bg-warning`, `text-danger`.
- For your own colors, edit the top of `assets/css/style.css`:

```css
:root {
  --brand: #4f46e5;       /* change this to your main color */
  --brand-dark: #3730a3;  /* darker shade for hover */
}
```

The `btn-brand`, `text-brand` and `bg-brand` classes use these colors.

### Step 8: Replace images
1. Put your picture in `assets/images/`.
2. Update the `src` in your HTML:

```html
<img src="assets/images/my-photo.jpg" class="img-fluid rounded" alt="Describe the picture">
```

`img-fluid` makes the image shrink to fit small screens. Always write an `alt` description.

### Step 9: Test on different screen sizes
1. Open the page in Chrome or Edge.
2. Press **F12** to open Developer Tools.
3. Press **Ctrl + Shift + M** to turn on device mode.
4. Pick a phone or tablet size and check that nothing breaks.

### Step 10: Submit
Check this list before you hand in:
- [ ] All pages open without errors
- [ ] All links work
- [ ] Images show up
- [ ] Looks good on phone and desktop
- [ ] Your name and project title are updated

---

## 6. Where to Use What (Cheat Sheet)

### Layout
| Need | Use | Where |
|------|-----|-------|
| Center content with side margins | `container` | Wrap each page section |
| Full-width content | `container-fluid` | Dashboards, split screens |
| Columns | `row` + `col-*` | Inside a container |
| Space between columns | `g-4` on the row | `<div class="row g-4">` |

### Spacing (scale 0 to 5)
- `m` = margin (outside space), `p` = padding (inside space)
- Sides: `t` top, `b` bottom, `s` start (left), `e` end (right), `x` left and right, `y` top and bottom
- Examples: `mt-3`, `p-4`, `py-5`, `mx-auto` (centers a block)

### Text
| Class | Result |
|-------|--------|
| `fw-bold` | Bold text |
| `text-center` | Centered text |
| `text-muted` | Gray text |
| `display-4` | Very large heading |
| `lead` | Larger intro paragraph |

### Buttons
```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-outline-secondary">Outline</button>
<button class="btn btn-success btn-lg">Big green</button>
<button class="btn btn-danger btn-sm">Small red</button>
```

### Flexbox helpers
| Class | Result |
|-------|--------|
| `d-flex` | Put items side by side |
| `justify-content-between` | Push items to opposite ends |
| `align-items-center` | Center items vertically |
| `gap-2` | Space between items |

### Show or hide by screen size
- `d-none d-md-block` hides on phones, shows on tablets and up.

### Icons
```html
<i class="bi bi-house"></i>
```
Browse names at <https://icons.getbootstrap.com/>.

### Components used in this template

| Component | Found in | What it does |
|-----------|----------|--------------|
| Navbar | `index.html` | Top menu that collapses on phones |
| Hero | `index.html` | Big banner at the top |
| Card | `index.html` | Box with image, title and text |
| Form | `login.html`, `signup.html` | Inputs, labels, buttons |
| Input group | `login.html` | Icon next to an input |
| Offcanvas | `dashboard.html` | Slide-in side menu |
| Dropdown | `dashboard.html` | Click-to-open menu |
| Progress bar | `dashboard.html` | Shows percent complete |
| Table | `dashboard.html` | Rows and columns of data |
| Badge | `index.html` | Small label like "Web" |

---

## 7. Practice Exercises

Do these in order. Each one builds a skill.

1. **Change a column size.** In `index.html`, change `col-md-4` to `col-md-6` in the features section. Refresh and see what happens.
2. **Change a button color.** Replace `btn-brand` with `btn-success` on one button.
3. **Add a fourth card.** Copy one course card and paste it after the last one. Change the title and text.
4. **Change the brand color.** Edit `--brand` in `style.css` and see which parts change.
5. **Add an icon.** Put `<i class="bi bi-star-fill"></i>` inside a button.
6. **Make a new page.** Create `pages/about.html` and link it from the navbar.
7. **Hide on mobile.** Add `d-none d-md-block` to an element and test it at phone size.
8. **Challenge:** Build a personal portfolio page using a navbar, hero, three cards and a contact form.

---

## 8. Common Mistakes and Fixes

| Problem | Likely cause | Fix |
|---------|--------------|-----|
| Page has no styling | Wrong CSS path | Check `assets/` vs `../assets/` |
| Icons show as empty squares | Icon CSS or `fonts/` folder missing | Keep `bootstrap-icons.min.css` and `css/fonts/` together |
| Navbar button or dropdown does nothing | JavaScript not loaded | Add the `bootstrap.bundle.min.js` script before `</body>` |
| Columns do not sit side by side | Missing `row`, or columns not inside it | Use `container` > `row` > `col-*` |
| Layout is tiny on phone | Missing viewport tag | Add the `<meta name="viewport">` line |
| My change does not appear | Browser cache or file not saved | Save the file, then press **Ctrl + F5** |
| My custom style is ignored | `style.css` loaded before Bootstrap | Load `style.css` **after** `bootstrap.min.css` |
| Images are missing | Wrong file name or path | Check spelling and capital letters |

---

## 9. Helpful Links

- [Bootstrap Documentation](https://getbootstrap.com/docs/5.3/getting-started/introduction/) (start here)
- [Grid System](https://getbootstrap.com/docs/5.3/layout/grid/)
- [Components](https://getbootstrap.com/docs/5.3/components/)
- [Forms](https://getbootstrap.com/docs/5.3/forms/overview/)
- [Utilities](https://getbootstrap.com/docs/5.3/utilities/spacing/)
- [Bootstrap Icons](https://icons.getbootstrap.com/)
- [Bootstrap Examples](https://getbootstrap.com/docs/5.3/examples/)
- [Free photos: Unsplash](https://unsplash.com/)

---

## 10. Credits

- Bootstrap 5.3.3 and Bootstrap Icons 1.11.3 (MIT License)
- Photos from Unsplash (Unsplash License)
