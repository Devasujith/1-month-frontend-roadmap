# Day 3: CSS Basics, Selectors & Typography

## 1. Introduction to CSS
CSS (**Cascading Style Sheets**) is used to style and lay out web pages—controlling color, font, alignment, and overall visual structure.

---

## 2. 3 Ways to Include CSS

### A. Inline CSS
Applied directly to an HTML element using the `style` attribute.
```html
<h1 style="color: blue; font-size: 24px;">Hello World</h1>
```
* **Pros:** Quick for testing.
* **Cons:** Hard to maintain, duplicates code, poor practice for full projects.

### B. Internal CSS
Written inside a `<style>` tag in the `<head>` section of the HTML file.
```html
<head>
  <style>
    h1 {
      color: blue;
      text-align: center;
    }
  </style>
</head>
```
* **Pros:** Single-page styling without extra files.
* **Cons:** Cannot be reused across multiple HTML pages.

### C. External CSS (Best Practice)
Written in a separate `.css` file and linked in the HTML `<head>`.
```html
<!-- index.html -->
<head>
  <link rel="stylesheet" href="style.css">
</head>
```
```css
/* style.css */
h1 {
  color: blue;
  text-align: center;
}
```
* **Pros:** Reusable across all HTML pages, clean separation of concern.

---

## 3. CSS Selectors

Selectors target specific HTML elements to apply styles.

| Selector Type | Syntax / Example | Scope / Description |
| :--- | :--- | :--- |
| **Universal Selector** | `* { margin: 0; }` | Targets every single element on the page. |
| **Element Selector** | `p { color: gray; }` | Targets all elements of that HTML tag name (`p`, `h1`, `div`). |
| **Class Selector** | `.btn { color: white; }` | Targets elements with `class="btn"`. (Reusable) |
| **ID Selector** | `#main-header { color: red; }` | Targets the unique element with `id="main-header"`. (Unique per page) |

---

## 4. CSS Specificity Rules

Specificity determines which CSS rule applies when multiple rules target the same element.

### Priority Order (Highest to Lowest):
1. **`!important`** *(Overrides everything—use sparingly)*
2. **Inline Styles** (`style="..."`)
3. **ID Selectors** (`#id`)
4. **Class Selectors, Attributes & Pseudo-classes** (`.class`, `[type="text"]`, `:hover`)
5. **Element Selectors & Pseudo-elements** (`h1`, `p`, `::before`)
6. **Universal Selector** (`*`)

---

## 5. Typography Properties

Typography properties control font styling, size, alignment, and spacing.

| Property | Description | Example Values |
| :--- | :--- | :--- |
| `font-family` | Sets the typeface / font stack | `'Poppins', Arial, sans-serif` |
| `font-size` | Controls text size | `16px`, `1.2rem`, `100%` |
| `font-weight` | Sets boldness | `normal`, `bold`, `400`, `600`, `700` |
| `line-height` | Controls line height / vertical spacing | `1.5`, `24px` |
| `text-align` | Horizontal alignment | `left`, `center`, `right`, `justify` |
| `text-transform` | Capitalization control | `uppercase`, `lowercase`, `capitalize` |
| `text-decoration` | Underline / line decorations | `none`, `underline`, `line-through` |

---

## 6. CSS Color Systems

CSS provides multiple ways to define color values:

### 1. Named Colors
Predefined color names in standard CSS.
```css
color: red;
color: navy;
```

### 2. HEX Codes (`#RRGGBB`)
Hexadecimal representation of Red, Green, and Blue values (00 to FF).
```css
color: #2563eb; /* Blue shade */
color: #ffffff; /* White */
```

### 3. RGB & RGBA
Red, Green, Blue values ranging from `0` to `255`. Alpha (`A`) sets opacity from `0.0` (transparent) to `1.0` (opaque).
```css
color: rgb(37, 99, 235);
background-color: rgba(37, 99, 235, 0.5); /* 50% transparent */
```

### 4. HSL & HSLA
Hue (`0–360°`), Saturation (`0–100%`), Lightness (`0–100%`), with optional Alpha opacity.
```css
color: hsl(217, 91%, 60%);
color: hsla(217, 91%, 60%, 0.8);
```

---

## 7. Day 3 Practice Template

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Day 3 CSS Basics & Typography</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <h1 class="heading">MERN Stack Roadmap</h1>
  <h2 id="subheading">Day 3: CSS Basics & Typography</h2>
  <p class="text-content">
    Innaiku CSS basics, selectors, specificity, fonts, and color systems padichirukkom.
  </p>

</body>
</html>
```

```css
/* style.css */

/* Universal Selector */
* {
  font-family: Arial, sans-serif;
}

/* Body styling using HEX color */
body {
  background-color: #f8fafc;
}

/* Class selector with typography & HEX */
.heading {
  color: #1e40af;
  font-size: 2rem;
  text-align: center;
  text-transform: uppercase;
}

/* ID selector with RGB color */
#subheading {
  color: rgb(30, 41, 59);
  font-size: 1.25rem;
  text-align: center;
  font-weight: 600;
}

/* Class selector with line-height & HSL color */
.text-content {
  color: hsl(215, 16%, 47%);
  font-size: 1rem;
  line-height: 1.6;
}
```
