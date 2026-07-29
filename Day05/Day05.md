# Day 5: Master CSS Flexbox 🚀

A comprehensive summary of CSS Flexbox concepts, container vs child properties, and practical hands-on examples learned on Day 5 of the MERN Stack Frontend Roadmap.

---

## 📌 1. Introduction to Flexbox
Flexbox (Flexible Box Layout) is a one-dimensional layout model used to align and distribute space among items in a container, either horizontally (row) or vertically (column).

### Core Structure
* **Flex Container (Parent):** The outer wrapper that enables the flex context using `display: flex;`.
* **Flex Items (Children):** The direct child elements positioned inside the flex container.

---

## 🛠️ 2. Flex Container Properties (Parent)

Applied to the wrapper element to control overall arrangement and alignment along axes.

| Property | Values / Usage | Description |
| :--- | :--- | :--- |
| `display` | `flex` | Activates Flexbox layout context for direct children. |
| `flex-direction` | `row` *(default)* \| `column` | Defines the main axis direction. |
| `flex-wrap` | `nowrap` *(default)* \| `wrap` | Controls whether items wrap onto multiple lines when space is constrained. |
| `justify-content` | `flex-start` \| `center` \| `flex-end` \| `space-between` \| `space-around` \| `space-evenly` | Aligns items along the **Main Axis** (Horizontal by default). |
| `align-items` | `stretch` *(default)* \| `center` \| `flex-start` \| `flex-end` | Aligns items along the **Cross Axis** (Vertical by default). |
| `gap` | e.g., `20px` | Defines equal space between flex items without using margins. |

---

## 🧩 3. Flex Item Properties (Child)

Applied to individual child elements inside the flex container to dictate how they grow, shrink, or set their initial dimensions.

| Property | Description |
| :--- | :--- |
| `flex-grow` | Dictates how much an item expands relative to others when extra space is available (`0` = no growth, `1+` = dynamic growth). |
| `flex-shrink` | Dictates how much an item contracts when space is tight (`0` = strict fixed width/no shrink, `1` = standard shrink). |
| `flex-basis` | Defines the initial base size of an item before growing or shrinking (e.g., `200px`, `120px`). |

### Shorthand Syntax
$$\text{flex: <flex-grow> <flex-shrink> <flex-basis>;}$$

* **Fixed Box Example:** `flex: 0 0 120px;` *(Never grows, never shrinks, strictly 120px)*
* **Flexible Dynamic Box Example:** `flex: 1 1 200px;` or simply `flex: 1;`

---

## 🎯 4. Key Takeaway: Direction Swap Rule
When `flex-direction: column` is applied, the axes swap roles:
* **`justify-content`** controls the **Vertical Axis** (Y-Axis).
* **`align-items`** controls the **Horizontal Axis** (X-Axis).

---

## 💻 5. Practical Hands-on Project: Responsive Profile Header

Here is the single HTML file containing embedded internal CSS:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Profile Header</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Flex Container (Parent) */
        .profile-header {
            display: flex;
            height: 40vh;                  /* 40% of Viewport Height */
            justify-content: space-between; /* Spacing between edge items */
            align-items: center;            /* Vertical alignment */
            padding: 20px;
            gap: 20px;
            background-color: #f8fafc;
        }

        /* Fixed Avatar Item (Child 1) */
        .avatar {
            width: 120px;
            height: 120px;
            flex: 0 0 120px;               /* Fixed: No grow, no shrink, 120px basis */
            background-color: #6366f1;
            border-radius: 50%;
        }

        /* Dynamic User Info Item (Child 2) */
        .user-info {
            flex: 3;                       /* Takes 3 parts of available space */
            display: flex;
            flex-direction: column;         /* Stacks title & subtitle vertically */
            justify-content: center;        /* Vertical center */
            align-items: flex-start;        /* Left alignment */
        }

        .user-info h1 {
            font-size: 24px;
            color: #1e293b;
            margin-bottom: 4px;
        }

        .user-info p {
            font-size: 16px;
            color: #64748b;
        }

        /* Action Button Container (Child 3) */
        .action-btn {
            flex: 1;                       /* Takes 1 part of remaining space */
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .action-btn button {
            padding: 10px 20px;
            background-color: #2563eb;
            color: #ffffff;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="profile-header">
        <div class="avatar"></div>
        <div class="user-info">
            <h1>Devasujith</h1>
            <p>Frontend Developer</p>
        </div>
        <div class="action-btn">
            <button>Follow</button>
        </div>
    </div>

</body>
</html>
