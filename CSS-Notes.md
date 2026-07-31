# 🎨 CSS Course — Complete Notes

> **Cascading Style Sheet** — Build a website in the order: `HTML → CSS → JS/Python`

---

## 📌 Table of Contents
1. [Introduction to CSS](#1-introduction-to-css)
2. [Including Styles](#2-including-styles)
3. [Selectors](#3-selectors)
4. [Color & Background](#4-color--background)
5. [Text Properties](#5-text-properties)
6. [Units in CSS](#6-units-in-css)
7. [Box Model](#7-box-model)
8. [Border, Padding & Margin](#8-border-padding--margin)
9. [Display & Visibility](#9-display--visibility)
10. [Position](#10-position)
11. [Flexbox](#11-flexbox)
12. [Media Queries](#12-media-queries)
13. [Transitions](#13-transitions)
14. [Transform](#14-transform)
15. [Animation](#15-animation)

---

## 1. Introduction to CSS

**CSS** → describes the **style** of the document.

### Basic Syntax
```css
h1 { color: red; }
```

| Part | Meaning |
|------|---------|
| `h1` | **Selector** → selects the item to which the property is applied |
| `color` | **Property** |
| `red` | **Value** |

### ⚠️ Notes
- HTML should **not** be used for properties — it may create chaos.
- Max code should be written in **CSS form**.

---

## 2. Including Styles

There are **3 ways** to add CSS:

### a) Inline
```html
<h1 style="color:red">HTML</h1>
```

### b) Internal (`<style>` tag)
```html
<style>
  h1 { color: red; }
</style>
```

### c) External Stylesheet ⭐ (Maximum cases use this)
Write CSS in a **separate document** and link it with the HTML code.

---

## 3. Selectors

`&` → ampersand

### 🔹 Universal Selector
```css
* { }
```
Applies to **every element** of the document code.
> CSS always goes **line by line** — later code has priority over prior code (in the code itself).

### 🔹 Element Selector
```css
h1 { }
```

### 🔹 ID Selector
```css
#myid { }
```
We can assign a property using the **id** of the element.
> ⚠️ IDs are **unique** — cannot assign one property to multiple elements using id.

### 🔹 Class Selector
When we want to assign a property to **many elements at a time**, use **class**.

```html
class="stg"
```
```css
.stg { property }
```

---

## 4. Color & Background

### Color Property
Used to color the **foreground** — the part visible to us (front layer / layer 1).

> **Foreground contains:** colors • buttons • text, etc.

### Background Color Property
Used to set the **background color** of a particular term.

### 🎨 Color Systems

```
        COLOR SYSTEMS
        /            \
   RGB Systems     Hex Systems
   (Broadly / mainly used — can make any color using these)
```

**Primary Colors:** 🔴 Red • 🔵 Blue • 🟢 Green

#### RGB
```css
rgb(255, 0, 0)   /* red */
rgb(0, 255, 0)   /* green */
```
- `R G B` → determines the **quantity** of primary colors
- `255` → **max** quantity of a color

#### HEX (Hexadecimal)
Contains **6 numbers**. `#` is always used to initiate.

```css
#ff0000   /* red   */
#00ff00   /* green */
```
- Ranges from `00 → ff`
- Format: `XX YY ZZ` → represents `R G B`

### RGBA & Alpha Channel
```css
color: rgba(255, 0, 0, 0.5);
```
**Opacity range:** `0` (not visible) → `1` (fully visible) — more = more visible.

---

## 5. Text Properties

### text-align
```css
h1 { text-align: left | right | centre; }
```
Can also use:
| Keyword | Behaves as |
|---------|-----------|
| `start` | left |
| `end`   | right |

> Default (English) → **left aligned**

### text-decoration
```css
text-decoration: underline | overline | line-through;
```
- Can be set to `none` — mainly used to **remove underline** from anchor tags.
- Many decorations available: `wavy` / `dotted` / `double` underline (property to decorate).

### text-transform
```css
text-transform: uppercase | lowercase | capitalize;
```
| Value | Effect |
|-------|--------|
| `capitalize` | First letter of **all words** capital |
| `lowercase`  | All lowercase |
| *(uppercase)* | All capital |

### font-weight
```css
font-weight: normal | bold | bolder | lighter;
```

### font-family
Used to set the font of the paragraph/text — can list multiple fonts **in order of priority**.

---

## 6. Units in CSS

### 📏 Absolute Units
```
px (pixels)
96px = 1 inch
font-size: 2px
```

### 📐 Relative Units — *in percentage*

Mainly used → `%` , `em` , `rem`

> Any property according to parent can be changed using relative units.

**% (Percent)**
> parent size relative to an element's parent object.
```css
width: 33%;   /* 33% of the parent object */
```

**em**
> Font related or other — assumes parent's size = 100%

| Value | Result |
|-------|--------|
| 1em   | 100% of parent's |
| 2em   | 200% of parent's |
| 0.5em | 50% of parent's |

**rem (Root em)**
> Relative to the **outer/root level element's** font size. The main element **outside the div**.

### Other Units
| Unit | Meaning |
|------|---------|
| `vh` | According to total **screen height** → `1vh` = 1% of browser/window height |
| `vw` | According to total **screen width** → `1vw` = 1% of window's width |

---

## 7. Box Model

```
 ┌───────────────────────────┐
 │         margin            │
 │  ┌─────────────────────┐  │
 │  │       border         │ │
 │  │  ┌────────────────┐  │ │
 │  │  │    padding      │ │ │
 │  │  │  ┌───────────┐  │ │ │
 │  │  │  │  content  │  │ │ │
 │  │  │  │  (width x │  │ │ │
 │  │  │  │  height)  │  │ │ │
 │  │  │  └───────────┘  │ │ │
 │  │  └────────────────┘  │ │
 │  └─────────────────────┘  │
 └───────────────────────────┘
```

### Height
By default, sets the **content area height** of the element.
> Width represents the height of the element (analogous rule for width).

### Border
Used to set the element's **border**.

| Property | Value |
|----------|-------|
| `border-width` | width of border |
| `border-style` | solid / dotted / dashed |
| `border-color` | color of border |

**Shorthand:**
```css
border: 2px solid #bbb;
        ↑    ↑     ↑
      width style color
```

---

## 8. Border, Padding & Margin

### Border Radius
Used to **round the corners** of the element's outer border edge.
```css
border-radius: 10px;   /* according to the requirement */
```
```css
border-radius: 50%;   /* → makes a circle */
```
> 🟢 Easy way to create a circle from a square!

### Padding
> Area **between content & border**

```css
padding-left
padding-right
padding-top
padding-bottom
```
*(all given in `px`)*

**Shorthand:**
```css
padding: 50px;                 /* set in all directions */
padding: 1px 2px 3px 4px;      /* top right bottom left — clockwise ⟳ */
```

### Margin
```css
margin-left
margin-right
margin-top
margin-bottom
```

**Shorthand:**
```css
margin: 50px;
margin: 1px 2px 3px 4px;    /* top right bottom left */
```

---

## 9. Display & Visibility

### Display Property
```css
display: inline | block | inline-block | none;
```

| Value | Behavior |
|-------|----------|
| `inline` | Takes only the space **required** for the element |
| `block` | Takes **full space** available in the width |
| `inline-block` | Similar to inline, **but** we can set margin & padding |
| `none` | **Removes** element from document flow |

> ⚠️ When we change block elements to inline, margin at top & bottom **can't be set** — so we use `inline-block`.

### Visibility
```css
visibility: hidden;
```
Space is **reserved** for the element — no element will replace the space of the hidden element.

---

## 10. Position

### `position` property values:

| Value | Description |
|-------|-------------|
| **static** | Default position — has **no effect** for applying `z-index` / top-bottom-left-right |
| **relative** | Element positioned relative to **itself** |
| **absolute** | Positioned relative to **ancestor** — removed from flow (removed from browser's perspective) |
| **fixed** | Position relative to **browser** — (top, right, bottom, left; two axes) |
| **sticky** | Positioned **based on the user's scroll** position |

> If we use them, they don't change the position.

### z-index
Decides the **stack level** of elements.
- Overlapping elements with a **larger** z-index cover those with a **smaller** one.

```
z-index: -1 | 1 | -2 | ...
```

---

## 11. Flexbox

### Background Image
```css
background-size:  ← Background: cover/contain/auto
```
- Can be **repeated** ↔ or **stretched** (as it is)

### Flex Box
> A **one-dimensional layout method** for arranging items in **rows** or **columns**.

- Makes work easier in arranging items.

### The Flex Model
```
 ┌───────────────────────────────►  main axis
 │  ┌─────┐ ┌─────┐ ┌─────┐
 │  │item1│ │item2│ │item3│   ← Flex container
 │  └─────┘ └─────┘ └─────┘
 ▼
cross axis
```
- `display: flex;` → **initiates** the using of flexbox model.

### Flex Direction
```css
flex-direction: row | row-reverse | column | column-reverse;
```
- `flex-box` → sets in which direction the flex items are placed in the flex container, along **which axis** (row/column).

### Flex Props

**justify-content** → alignment along the **main axis**
```css
justify-content: flex-start | flex-end | center | space-around | space-evenly | space-between;
```

**align-items** → alignment along the **cross axis**
```css
align-items: flex-start | flex-end | center;
```

**align-content** → alignment of **space blw** (space between) content around the content
```css
align-content: ...
```

### For Item
**align-self** → alignment of individual flex item along the axis
```css
align-self: ...
```

**flex-grow** → how much a flex item will grow **relative to the rest** of flex items
```css
flex-grow: ...
```

**flex-shrink** → how flex items will shrink relative to the rest — space is **available**.

---

## 12. Media Queries

**Media Queries** → build **responsive** websites.

```css
@media screen and (min-width: 600px) {
  /* CSS rules */
}
```

- **Break points**: below `600` one color, after `600` another one.
- Colors: `≤ 3` or by color: `≤ 3`

---

## 13. Transitions

**Transitions** → basically determine **how an element** changes state to another.

- **Property** → font-size / color / etc. **(easing/in-out / 0.2s)**
- **Duration**
- **Timing function** / **delay**

### Transition Property
Enables us to define the **transition** between **two states** of an element.

- **Transition-property**: property we want to display transition.
  ```css
  transition-property: property; /* font-size, width, etc. */
  ```
- **Transition-duration**: `2s|ms`
  ```css
  transition-duration: 2s;
  ```
- **Transition-timing-function**: `ease-in-out / linear / linear...`
  ```css
  transition-timing-function: ease-in-out;
  ```
- **Transition-delay**: delay in **case-out / linear** — steps in relation to seem that the property present at the item.

---

## 14. Transform

```css
translate(x, y)
```
- Move object element in `x` and `y` axis.

```css
transform: translate(20px, 50px);
```

```css
transform: rotate(x, y, axis, 3deg);
```
- Elongate along sides, etc.

```css
transform: skew(angle);
```
- Skew (angle)

### CSS Transform (usage)
Used to apply **2D / 3D transformations** to an element.

```css
transform: rotate(45deg);
```

**We can use** `rotate X`, `rotate Y`, `rotate Z` axes.

To rotate along `x, y, z` axes:
```css
transform: rotateX(...) rotateY(...) rotateZ(...);
```

### Scale
```css
transform: scale(x, y);
```
- Scale for `x, y` axis

```css
scale(2)     → double scale
scale(0.5)   → half size
```
- `x` `y` axis scale etc.

```css
transform: scaleX(...) scaleY(...);
```

---

## 15. Animation

### CSS Transform Basics (recap)
```css
translate  → transform: translate(x px, y px)   /* Move object element in x and y axis */
transform  → transform: rotate(20deg)             /* elongate along sides etc. */
skew       → transform: skew(angle)
```

### Animation
> To **animate** any CSS element.

```css
@keyframes myName {
  from { font-size: 20px; }   /* starting state */
  to   { font-size: 40px; }   /* ending state */
}
```

> ⚠️ The **transition does not** apply any change (the animation applies properties to elements).

### Animation Direction

| Value | Meaning |
|-------|---------|
| `normal` | default |
| `reverse` | plays backward |
| `alternate` | normal ↔ reverse |
| `alternate-reverse` | reverse ↔ normal |

### Animation Shorthand
```css
animation: name duration timing-function delay
           iteration-count direction fill-mode;
```

- **name** — duration — function delay
- **iteration-count** ⟷ **no. of times**
- **direction**

### % in Animation
```css
@keyframes myName {
  0%   { font-size: 20px; }
  50%  { font-size: 36px; }
  100% { font-size: 56px; }
}
```

---

## ✅ Quick Summary Cheat-Sheet

| Topic | Key Property |
|-------|-------------|
| Colors | `color`, `background-color`, `rgb()`, `#hex`, `rgba()` |
| Text | `text-align`, `text-decoration`, `text-transform`, `font-weight`, `font-family` |
| Box Model | `width`, `height`, `padding`, `border`, `margin` |
| Layout | `display`, `visibility`, `position`, `z-index` |
| Flexbox | `display:flex`, `flex-direction`, `justify-content`, `align-items` |
| Responsive | `@media` |
| Motion | `transition`, `transform`, `@keyframes`, `animation` |

---
*Compiled from handwritten CSS course notes* ✍️
