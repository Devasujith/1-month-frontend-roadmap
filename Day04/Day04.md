# 🚀 Day 4 - CSS Box Model, Display & Positioning Schemes (Complete Session Log)

**Track:** MERN Stack Frontend Specialization\
**Module:** Week 1 -- HTML & CSS Foundation\
**Day:** Day 4\
**Status:** ✅ Completed

------------------------------------------------------------------------

## 📌 Overview & Learning Journey

Today's session focused on bridging theory and practical implementation
for **CSS Box Model**, **Display Properties**, and **Positioning
Schemes**. Through step-by-step execution without pre-written solutions,
concepts were built from the ground up by analyzing real code,
inspecting layouts using browser DevTools (F12), and creating custom
components from scratch.

------------------------------------------------------------------------

## 🧠 Core Concepts & Theory Breakdown

### 1. CSS Box Model

Every HTML element is rendered as a rectangular box consisting of four
layers:

-   **Content** -- Area that contains text, images, or child elements.
-   **Padding** -- Space between content and border.
-   **Border** -- Visible outline around the element.
-   **Margin** -- Outer spacing separating neighboring elements.

#### Default Box Sizing (`content-box`)

``` text
Total Width =
width +
padding-left +
padding-right +
border-left +
border-right
```

#### Universal Reset (`border-box`)

``` css
*{
    box-sizing:border-box;
}
```

With `border-box`, padding and border are included inside the declared
width.

------------------------------------------------------------------------

### 2. CSS Display Properties

  Display          Behavior                                  Width / Height
  ---------------- ----------------------------------------- ----------------------
  `block`          Occupies full width, starts on new line   Supported
  `inline`         Occupies only content width               Width/height ignored
  `inline-block`   Inline layout with box dimensions         Supported

------------------------------------------------------------------------

### 3. CSS Positioning

-   `static`
-   `relative`
-   `absolute`
-   `fixed`
-   `sticky`

`relative` acts as the reference for absolutely positioned children.

------------------------------------------------------------------------

## 💻 Practical Code Log

### 1. Basic Box Model & Sizing Reset

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Box model</title>
    <style>
        .first-box {
            width: 250px;
            height: 150px;
            background-color: teal;
            color: white;
            text-align: center;
            padding: 20px;
            border: 3px solid black;
            margin: 40px;
            box-sizing: border-box;
        }
    </style>
</head>
<body>
    <div class="first-box">
        <h2>My First Box Model</h2>
    </div>
</body>
</html>
```

### 2. Profile Cards with Margin & Padding

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Card</title>
    <style>
        * {
            box-sizing: border-box;
            font-family: cursive;
        }
        .profile-card {
            width: 300px;
            background-color: #f4f4f4;
            border: 2px solid darkslateblue;
            padding: 25px 20px;
            margin-top: 50px;
            margin-left: 50px;
            margin-bottom: 50px;
            text-align: center;
            font-style: italic;
        }
        button {
            padding: 10px 20px;
            border: 1px solid;
            background-color: dodgerblue;
            color: white;
        }
        .second-card {
            margin-left: 50px;
            border: 2px dashed darkorchid;
            padding: 25px 20px;
            width: 300px;
            text-align: center;
            font-style: oblique;
            font-variant: small-caps;
        }
    </style>
</head>
<body>
    <div class="profile-card">
        <h2>Devasujithsingh.P</h2>
        <p>Frontend Developer</p>
        <button>Contact Me</button>
    </div>
    <div class="second-card">
        <h2>Devasujithsingh.P</h2>
        <p>Frontend Developer</p>
        <button>Contact Me</button>
    </div>
</body>
</html>
```

### 3. Notification Component

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Notification Component</title>
    <style>
        * {
            box-sizing: border-box;
        }
        .notification {
            width: 300px;
            padding: 15px 20px;
            margin: 50px;
            border-left: 8px solid black;
        }
        button {
            border: 1px solid darkblue;
            background-color: lightgreen;
            padding: 10px 20px;
        }
        button:hover {
            cursor: pointer;
            color: white;
            background-color: teal;
        }
    </style>
</head>
<body>
    <div class="notification">
        <h3>New Update</h3>
        <p>We Introduced New feature click below button to know more</p>
        <button>View Details</button>
        <button>Dismiss</button>
    </div>
</body>
</html>
```

### 4. Product Card with Floating NEW Badge

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Card</title>
    <style>
        * {
            box-sizing: border-box;
        }
        .product-card {
            border: 1px solid black;
            width: 250px;
            text-align: center;
            margin: 50px;
            padding: 15px;
            background-color: #f9f9f9;
            transition: 0.3s;
            border-radius: 10px;
            position: relative;
        }
        button {
            margin-right: 5px;
            padding: 8px 14px;
            background: #007bff;
            color: white;
            transition: 0.3s;
            border-radius: 10px;
            border: none;
        }
        button:hover {
            background: #0056b3;
            color: white;
        }
        .price {
            font-weight: bold;
        }
        .product-card:hover {
            box-shadow: 0 6px 15px rgba(0,0,0,0.2);
        }
        .badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: red;
            color: white;
            font-size: 12px;
            font-weight: bold;
            padding: 5px 10px;
            border: 2px solid #fff;   
            border-radius: 20px;      
        }
    </style>
</head>
<body>
    <div class="product-card">
        <h1>Iphone Mobiles</h1>
        <span class="badge">NEW</span>
        <img src="/Day4/Apple-iphone-17.webp" width="200px" alt="iPhone 17 Pro">
        <h2>Iphone 17Pro</h2>
        <p>Available in Silver, Cosmic Orange, and Deep Blue.</p>
        <p class="price">₹134,900</p>
        <button>Buy Now</button>
        <button>Add to Cart</button>
    </div>
</body>
</html>
```

### 5. Sticky Navigation Header

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sticky Header</title>
    <style>
        header {
            position: sticky;
            top: 0;
            background-color: black;
            color: white;
            padding: 15px;
        }
        a {
            display: inline-block;
            padding: 5px 10px;
            margin: 5px;
            color: white;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <header>
        <h3>My Portfolio</h3>
        <a href="#home">Home</a>
        <a href="#About">About</a>
        <a href="#contact">Contact</a>
    </header>
    <p>Sample long content paragraph for scrolling verification...</p>
</body>
</html>
```

------------------------------------------------------------------------

## 🎯 Key Takeaways

-   Always begin CSS with:

``` css
*{
    box-sizing:border-box;
}
```

-   Understand the difference between content-box and border-box.
-   Use the appropriate `display` value based on layout needs.
-   Use `position: relative` for parent containers when using
    `position: absolute`.
-   Use `sticky` for navigation bars.

------------------------------------------------------------------------

## ❌ Common Mistakes

-   Forgetting `box-sizing:border-box`
-   Using `absolute` without a relative parent
-   Expecting width/height to work on inline elements
-   Confusing padding with margin

------------------------------------------------------------------------

## 💼 Interview Questions

1.  Explain the CSS Box Model.
2.  Difference between `content-box` and `border-box`?
3.  Difference between `block`, `inline`, and `inline-block`.
4.  Difference between `relative` and `absolute`.
5.  Difference between `fixed` and `sticky`.

------------------------------------------------------------------------

## ✅ Summary

This session strengthened the fundamentals of CSS layouts by covering
the Box Model, Display properties, and Positioning Schemes through
theory and practical implementation.
