# HTML Course Notes (Refined)

## 1. Introduction to Web Development

Building a website typically involves three core technologies, each with a distinct job:

| Technology | Purpose |
|---|---|
| **HTML** | Structure and layout of the page (the skeleton) |
| **CSS** | Styling and visual presentation (colors, spacing, fonts) |
| **JavaScript** | Logic and interactivity (behavior) |

**HTML** stands for **H**yper **T**ext **M**arkup **L**anguage. It is not a programming language — it's a *markup language* used to structure content using tags.

- `index.html` is the default filename a server looks for and loads automatically when someone visits a folder/website (the homepage).
- In VS Code, the **Live Server** extension ("Go Live") lets you preview your HTML file in a browser with auto-refresh as you edit.

---

## 2. HTML Tags, Elements, and Content

An HTML **tag** marks the start or end of a piece of content. Tags usually come in pairs: an opening tag and a closing tag.

```html
<p>This is a paragraph.</p>
```

Breaking this down:

- `<p>` — **opening tag** (starts a paragraph)
- `</p>` — **closing tag** (ends the paragraph, note the `/`)
- `This is a paragraph.` — **content**
- The opening tag + content + closing tag together = an **element**

Some tags are **self-closing** (they don't wrap content and have no closing tag), e.g. `<br>` (line break) and `<hr>` (horizontal rule).

**Important:** HTML is **not case-sensitive** (`<P>` works the same as `<p>`), but lowercase is the standard convention.

**Comments** in HTML are written as:
```html
<!-- This is a comment and won't be displayed on the page -->
```

---

## 3. Basic Document Structure

Every HTML document follows this skeleton:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <p>Hello world</p>
  </body>
</html>
```

| Tag | Explanation |
|---|---|
| `<!DOCTYPE html>` | Tells the browser this document uses HTML5 (must be the very first line) |
| `<html>` | The **root element** of the page — the parent of everything, including `<head>` and `<body>` |
| `<head>` | Contains **metadata** (info *about* the page — not shown directly on the page itself) |
| `<title>` | Sets the text shown on the browser tab |
| `<body>` | Contains all the visible content that gets **rendered** in the browser |

💡 You can view a page's underlying HTML using **Inspect** or **View Page Source** in the browser.

---

## 4. Headings

Headings define the hierarchy/importance of text on a page, from `<h1>` to `<h6>`:

```html
<h1>Most important</h1>
<h2>...</h2>
<h3>...</h3>
<h4>...</h4>
<h5>...</h5>
<h6>Least important</h6>
```

- `<h1>` is typically used once per page for the main title.
- Headings also help structure content for accessibility and SEO.

---

## 5. Text Formatting Tags

| Tag | Purpose |
|---|---|
| `<p>` | Paragraph |
| `<b>` | **Bold** text |
| `<i>` | *Italic* text |
| `<u>` | <u>Underlined</u> text |
| `<big>` | Increases text size |
| `<small>` | Decreases text size |
| `<sub>` | Sub<sub>script</sub> (e.g. H₂O) |
| `<sup>` | Super<sup>script</sup> (e.g. A^B, exponents) |
| `<hr>` | Inserts a horizontal line to separate content/sections |
| `<pre>` | **Preformatted text** — displays text exactly as written, preserving spaces and line breaks (a normal `<p>` collapses extra whitespace into a single space) |

---

## 6. Links and Images

**Anchor tag** — creates a hyperlink:
```html
<a href="https://google.com">Google</a>
```
- `href` = the destination URL
- To open the link in a **new tab**, add `target="_blank"`:
```html
<a href="https://google.com" target="_blank">Google</a>
```
> Note: the correct value for opening a new tab is `_blank` (not `_main`).

**Relative file paths** — to link to a file inside a folder within your project:
```html
<a href="/folder/filename.html">Link text</a>
```

**Image tag** — self-closing, embeds an image:
```html
<img src="/image.png" alt="Random Image">
```
- `src` = the **source** (file path or URL) of the image
- `alt` = alternative text shown if the image fails to load, and read aloud by screen readers

---

## 7. Semantic vs Non-Semantic Tags

**Semantic tags** clearly describe their *meaning/purpose* just from the tag name — both to developers and to browsers/search engines/screen readers.

**Non-semantic tags** are generic containers that don't describe what they contain.

| Type | Examples | Notes |
|---|---|---|
| Semantic | `<header>`, `<main>`, `<footer>`, `<section>`, `<article>`, `<aside>`, `<nav>` | Improve SEO and accessibility; use these where possible |
| Non-semantic | `<div>`, `<span>` | Used purely for grouping/styling; no inherent meaning |

**Why semantic tags matter:**
- Easier for humans reading the code to understand structure
- Improves a website's **SEO** (Search Engine Optimization)
- Improves accessibility and overall user experience

### Typical page layout using semantic tags:

```html
<body>
  <header>...</header>
  <main>...</main>
  <footer>...</footer>
</body>
```

**Inside `<main>`, you commonly use:**

| Tag | Purpose |
|---|---|
| `<section>` | Groups a distinct section of related content on the page |
| `<article>` | Represents a self-contained, independent piece of content (e.g. a blog post, news article) |
| `<aside>` | Content tangential to the main content — e.g. sidebars, related links, ads |

---

## 8. Div and Span

| Tag | Type | Behavior |
|---|---|---|
| `<div>` | Non-semantic, **block-level** | Takes up the **full width** available; used to group larger chunks of content |
| `<span>` | Non-semantic, **inline** | Takes up **only as much width as its content needs**; used to group small pieces of text/elements inline |

Use `<div>` or `<span>` when you need to group elements together (often for applying CSS styling or JavaScript behavior) but no semantic tag fits.

---

## 9. Block vs Inline Elements

**Block elements** start on a new line and take up the full width of their container:

`<address>` `<article>` `<aside>` `<blockquote>` `<canvas>` `<dd>` `<div>` `<dl>` `<dt>` `<fieldset>` `<figcaption>` `<figure>` `<footer>` `<form>` `<h1>`–`<h6>` `<header>` `<hr>` `<li>` `<main>` `<nav>` `<ol>` `<p>` `<pre>` — and others.

**Inline elements** sit within the flow of text and only take up as much width as needed:

`<a>` `<abbr>` `<acronym>` `<b>` `<bdo>` `<big>` `<br>` `<button>` `<cite>` `<code>` `<dfn>` `<em>` `<img>` `<input>` `<kbd>` `<label>` `<map>` `<object>` `<output>` `<q>` `<samp>` `<script>` `<select>` `<small>` `<span>` `<strong>` `<sub>` `<sup>` `<textarea>` `<time>` `<var>` — and others.

---

## 10. Lists

HTML supports two main types of lists:

| List type | Tag | Marker style |
|---|---|---|
| Unordered list | `<ul>` | Bullets (•) |
| Ordered list | `<ol>` | Numbers (1, 2, 3...) or letters/roman numerals (i, ii...) |

Each item inside either list type uses `<li>` (list item):

```html
<ul>
  <li>Apple</li>
  <li>Orange</li>
</ul>

<ol>
  <li>Apple</li>
  <li>Orange</li>
</ol>
```

---

## 11. Tables

Tables display tabular (row/column) data.

| Tag | Purpose |
|---|---|
| `<table>` | Wraps the entire table |
| `<tr>` | Table **row** |
| `<td>` | Table **data** cell |
| `<th>` | Table **header** cell (bold + centered by default) |
| `<caption>` | Adds a caption/title to the table |
| `<thead>` | Wraps the header row(s) of the table |
| `<tbody>` | Wraps the main body/data rows of the table |

```html
<table>
  <caption>Student Data</caption>
  <thead>
    <tr>
      <th>Name</th>
      <th>Grade</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>A</td>
    </tr>
  </tbody>
</table>
```

**`colspan`** — an attribute on `<td>`/`<th>` used to merge two or more columns into one cell:
```html
<td colspan="2">Merged Cell</td>
```

---

## 12. Forms

Forms collect input/data from users (e.g. sign-up, login, contact/help requests).

```html
<form action="/submit">
  ...form elements go here...
</form>
```

- **`action`** attribute: defines *where* the form's data should be sent when submitted (e.g. a server endpoint).

### Input Element
```html
<input type="text" placeholder="Enter Name">
```
- `type` defines the kind of input (text, checkbox, email, password, etc.)
- `placeholder` shows greyed-out hint text inside the field before the user types

### Label
```html
<label for="nameInput">Name:</label>
<input type="text" id="nameInput">
```
- A `<label>` is tied to an input element (via the `for`/`id` attributes).
- Important for **accessibility** — screen readers announce the label when the input is focused.
- Clicking the label also focuses/activates its linked input.

### Class & ID
| Attribute | Purpose |
|---|---|
| `class` | Groups multiple elements together so they can be styled or selected together (reusable across many elements) |
| `id` | A **unique** identifier assigned to a single element (should not repeat on a page) |

Use `class` when you want to apply the same style/behavior to a whole group of elements; use `id` when targeting one specific, unique element.

### Checkboxes
Used to collect multiple-choice / MCQ-style answers (user can select more than one option):
```html
<input type="checkbox" id="option1">
<label for="option1">Option 1</label>
```

### Select (Dropdown)
Lets a user pick one option from a list:
```html
<select name="options" id="options">
  <option value="1">Option 1</option>
  <option value="2">Option 2</option>
</select>
```

---

## 13. Embedding Media

### Iframe
Used to embed **another website/page inside your page**:
```html
<iframe src="https://www.youtube.com/embed/VIDEO_ID"></iframe>
```
⚠️ Note: not every website allows itself to be embedded this way — some sites block being placed inside an iframe.

### Video
```html
<video src="myvideo.mp4" controls loop autoplay>
  My video
</video>
```

| Attribute | Purpose |
|---|---|
| `controls` | Shows play/pause/volume controls to the user |
| `loop` | Replays the video automatically once it ends |
| `autoplay` | Starts playing the video automatically on page load |

---

## Quick Reference Summary

- **Structure:** `<!DOCTYPE html>` → `<html>` → `<head>` + `<body>`
- **Text:** headings (`<h1>`–`<h6>`), `<p>`, `<b>`, `<i>`, `<u>`, `<pre>`
- **Navigation:** `<a>` with `href` and optional `target="_blank"`
- **Media:** `<img>`, `<video>`, `<iframe>`
- **Layout:** semantic (`<header>`, `<main>`, `<footer>`, `<section>`, `<article>`, `<aside>`) vs non-semantic (`<div>`, `<span>`)
- **Lists:** `<ul>`/`<ol>` with `<li>`
- **Tables:** `<table>`, `<tr>`, `<td>`, `<th>`, `<thead>`, `<tbody>`, `colspan`
- **Forms:** `<form>`, `<input>`, `<label>`, `<select>`, `class` vs `id`
