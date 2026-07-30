# 🚀 Day 6 – CSS Grid, Responsive Design & Media Queries

**Track:** MERN Stack Frontend Specialization  
**Module:** Week 1 – HTML & CSS Foundation  
**Day:** 6  
**Status:** ✅ Completed

---

# 📌 Overview

Today I learned **CSS Grid**, one of the most powerful layout systems in CSS for creating **two-dimensional (rows + columns)** layouts. I also learned **Responsive Design** and **Media Queries**, which help websites automatically adjust to different screen sizes like desktops, tablets, and mobiles.

---

# 📖 1. CSS Grid Basics (2D Layout)

CSS Grid is a layout system that allows us to arrange elements in both **rows and columns simultaneously**.

Unlike **Flexbox**, which is mainly one-dimensional (either row or column), **Grid works in two dimensions**, making it ideal for dashboards, galleries, portfolios, product cards, and complete webpage layouts.

### Example

```css
.container{
    display: grid;
}
```

The moment we use:

```css
display: grid;
```

The element becomes a **Grid Container**, and all its direct children become **Grid Items**.

---

# 👨‍💼 Parent vs 👷 Child

## Parent (Grid Container)

The parent controls the overall layout.

It is responsible for:

- Number of columns
- Number of rows
- Gap between items
- Alignment
- Grid sizing

Example:

```css
.container{
    display:grid;
}
```

---

## Child (Grid Items)

Children live inside the grid.

They can:

- Span multiple columns
- Span multiple rows
- Override alignment individually

Example:

```html
<div class="container">
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>
```

---

# 📖 2. Parent Container Properties

## display: grid

Activates Grid Layout.

```css
.container{
    display:grid;
}
```

---

## grid-template-columns

Defines the number and width of columns.

Example:

```css
.container{
    grid-template-columns:200px 200px 200px;
}
```

Creates **3 columns**, each **200px** wide.

---

Using Fraction Units:

```css
.container{
    grid-template-columns:1fr 1fr 1fr;
}
```

Each column gets an equal amount of available space.

---

Using repeat()

Instead of writing:

```css
1fr 1fr 1fr 1fr
```

Use:

```css
grid-template-columns:repeat(4,1fr);
```

Meaning:

- Repeat 4 times
- Each column = 1 fraction

---

## grid-auto-rows

Automatically creates rows with a specified size.

Example:

```css
grid-auto-rows:150px;
```

Every new row becomes **150px** tall.

---

## minmax()

Defines a minimum and maximum size.

Example:

```css
grid-auto-rows:minmax(150px,auto);
```

Meaning:

- Minimum height = **150px**
- If content grows, the row also grows automatically.

---

## gap

Adds spacing between rows and columns.

Example:

```css
gap:20px;
```

Equivalent to:

```css
row-gap:20px;
column-gap:20px;
```

✅ **Gap is always applied to the Parent Container.**

---

## justify-items

Aligns items horizontally inside each grid cell.

Example:

```css
justify-items:center;
```

Other values:

- start
- center
- end
- stretch (default)

---

## align-items

Aligns items vertically.

Example:

```css
align-items:center;
```

Values:

- start
- center
- end
- stretch

---

# ⭐ Powerful Grid Functions

## repeat()

Instead of:

```css
grid-template-columns:1fr 1fr 1fr;
```

Use:

```css
grid-template-columns:repeat(3,1fr);
```

Cleaner and easier to maintain.

---

## minmax()

Example:

```css
grid-auto-rows:minmax(150px,auto);
```

Minimum height = **150px**

Maximum = grows automatically with content.

---

## auto-fit + minmax()

One of the most powerful Grid features.

Example:

```css
grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
```

Meaning:

- Create as many columns as possible.
- Each column is at least **200px** wide.
- If extra space exists, distribute it equally.

✅ Automatically creates responsive layouts without media queries.

---

# 📖 3. Child Properties

## grid-column

Makes an item span multiple columns.

Example:

```css
.card{
    grid-column:span 2;
}
```

The card occupies **2 columns**.

---

## grid-row

Makes an item span multiple rows.

Example:

```css
.card{
    grid-row:span 2;
}
```

The card occupies **2 rows**.

---

## align-self

Overrides vertical alignment for a single item.

Example:

```css
.card{
    align-self:end;
}
```

Other values:

- start
- center
- end
- stretch

---

# 📱 4. Responsive Design

Responsive Design ensures that websites look good on every device.

Devices include:

- 💻 Desktop
- 💻 Laptop
- 📱 Mobile
- 📲 Tablet

Instead of creating different websites, we create **one website** that adapts automatically.

---

# 📖 What is a Media Query?

Media Queries apply CSS only when a certain condition becomes true.

Example:

```css
@media(max-width:768px){
    ...
}
```

Meaning:

Apply the following CSS only when the screen width is **768px or smaller**.

---

# 📌 Desktop First Approach

Default CSS is written for desktops.

Then override styles for smaller devices.

Example:

```css
.dashboard{
    display:grid;
    grid-template-columns:repeat(4,1fr);
}
```

---

# 📌 Tablet Layout

```css
@media(max-width:768px){

.dashboard{
    grid-template-columns:repeat(2,1fr);
}

}
```

Now the layout changes from:

```
4 Columns
```

to

```
2 Columns
```

---

# 📌 Mobile Layout

```css
@media(max-width:480px){

.dashboard{
    grid-template-columns:1fr;
}

}
```

Now every card occupies one row.

```
1 Column
```

---

# 📌 Reset Grid Spans on Mobile

Suppose:

Desktop:

```css
.card1{
    grid-column:span 2;
}
```

On mobile, only one column exists.

So reset it:

```css
.card1,
.card2{

grid-column:span 1;
grid-row:span 1;

}
```

Otherwise, the layout may break.

---

# 📌 Why Place Media Queries at the Bottom?

CSS follows the **Cascade Rule**.

The CSS written later overrides previous styles if specificity is the same.

Example:

```css
.card{
    color:red;
}

.card{
    color:blue;
}
```

Output:

```
Blue
```

Because the second rule comes later.

Therefore:

✅ Always keep Media Queries at the **bottom of the CSS file**.

---

# 💻 Complete Example

```css
.dashboard{

display:grid;
grid-template-columns:repeat(4,1fr);
gap:20px;

}

.card1{

grid-column:span 2;

}

.card2{

grid-row:span 2;

}

/* Tablet */

@media(max-width:768px){

.dashboard{

grid-template-columns:repeat(2,1fr);

}

}

/* Mobile */

@media(max-width:480px){

.dashboard{

grid-template-columns:1fr;

}

.card1,
.card2{

grid-column:span 1;
grid-row:span 1;

}

}
```

---

# 📋 Cheat Sheet

| Property | Parent / Child | Purpose |
|-----------|----------------|---------|
| `display:grid` | Parent | Activates Grid Layout |
| `grid-template-columns` | Parent | Defines columns |
| `grid-auto-rows` | Parent | Creates automatic rows |
| `repeat()` | Parent | Repeats columns or rows |
| `minmax()` | Parent | Sets minimum and maximum size |
| `gap` | Parent | Adds spacing between grid items |
| `justify-items` | Parent | Horizontal alignment |
| `align-items` | Parent | Vertical alignment |
| `grid-column` | Child | Span multiple columns |
| `grid-row` | Child | Span multiple rows |
| `align-self` | Child | Individual vertical alignment |

---

# 🔥 Difference Between Flexbox and Grid

| Flexbox | Grid |
|----------|------|
| One-dimensional | Two-dimensional |
| Works in Row **or** Column | Works in Rows **and** Columns |
| Best for Components | Best for Page Layouts |
| Navigation Bars | Dashboards |
| Cards in One Row | Entire Website Structure |

---

# 🎯 Key Takeaways

- CSS Grid is a **2D Layout System**.
- `display:grid` activates Grid Layout.
- `grid-template-columns` defines the column structure.
- `repeat()` reduces repetitive code.
- `minmax()` creates flexible row or column sizes.
- `gap` adds spacing between grid items.
- `grid-column` and `grid-row` allow items to span multiple cells.
- Responsive Design ensures websites work across all devices.
- Media Queries apply CSS based on screen width.
- `max-width` targets smaller screens (Desktop First).
- Always place Media Queries at the **bottom** of the CSS file.

---

# ✅ Day 6 Completed

**Topics Covered:**

- ✅ CSS Grid Basics
- ✅ Parent vs Child Properties
- ✅ Grid Columns & Rows
- ✅ repeat()
- ✅ minmax()
- ✅ gap
- ✅ justify-items
- ✅ align-items
- ✅ grid-column
- ✅ grid-row
- ✅ align-self
- ✅ Responsive Design
- ✅ Media Queries
- ✅ Desktop First Approach
- ✅ Tablet Layout
- ✅ Mobile Layout
- ✅ Resetting Grid Spans
- ✅ Flexbox vs Grid
- ✅ CSS Grid Cheat Sheet

🎉 **Week 1 – HTML & CSS Foundation is now complete!**
