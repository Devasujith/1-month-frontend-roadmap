# Day 1: HTML Structure and Semantic HTML

Date: July 23, 2026
Track: 1 Month MERN Stack Frontend Learning Challenge
Status: Completed

---

## 1. Summary of Today Learning

Today I built my foundational understanding of HTML syntax, proper document layout, meta tags, and semantic elements. Instead of just writing generic tags, I learned how to structure code professionally for better SEO, code readability, and web accessibility (a11y).

---

## 2. HTML Standard Structure and Core Mechanics

Every HTML document requires a standard skeleton to work properly across all browsers:

- <!DOCTYPE html>: Instructions to the browser that this page is written in modern HTML5.
- <html lang="en">: Root container for the page.
- <head>: Invisible configuration area containing metadata, titles, and links.
- <body>: Visible UI layer containing all content user sees on screen.

Key Meta Tags Learned:
- <meta charset="UTF-8">: Enables universal character encoding (supports Tamil text, special symbols, and emojis without getting corrupted).
- <meta name="viewport" content="width=device-width, initial-scale=1.0">: Critical for mobile responsiveness. Sets layout width equal to device screen width and defaults zoom to 100%.

---

## 3. Block vs Inline Elements

- Block Elements: Occupy 100% width of the screen by default and always break onto a new line (e.g., h1-h6, p, div, section).
- Inline Elements: Only occupy as much width as their content needs and do not force a new line (e.g., span, a, strong).

---

## 4. Semantic HTML (The Core Focus)

Semantic tags give meaning to web elements. Instead of creating a div soup using only div tags, semantic tags tell browsers, Google crawlers, and screen readers (a11y) what each part of the page actually is.

Key Tags Mastered:
- <header>: Site logo, branding, and top bar content.
- <nav>: Navigation bar containing links.
- <main>: Main unique content of the page (Rule: Only ONE main tag per page!).
- <section>: Grouping content by topic or theme (e.g., About section, Skills section).
- <article>: Self-contained independent content block that makes sense on its own (e.g., blog posts, project cards).
- <aside>: Secondary sidebar content indirectly related to main content.
- <footer>: Page bottom containing copyright, contact info, and social links.

---

## 5. Tags vs Attributes

- Tags: Structural markers defined with opening and closing syntax (e.g., <p>Content</p>).
- Self-Closing Tags: Tags without closing wrappers (e.g., <hr>, <img>, <meta>).
- Attributes: Extra settings placed inside the opening tag (name="value" pairs):
  - id: Unique identifier per page (e.g., id="about").
  - class: Reusable grouping identifier for CSS and JS.
  - src and alt: Image location and fallback description text for broken images/screen readers.
  - href and target="_blank": Link destination and opening in a new tab.
  - Action triggers: mailto: for direct email drafting and tel: for dialing phone numbers.

---

## 6. Hands-on Practice Project

Created my Personal Bio Page using 100% semantic HTML structure without any CSS styling.

Features Included:
- Standard HTML5 head with mobile viewport and charset.
- Top navigation with smooth section scrolling anchors (#about, #skills, #projects).
- Topic sections using section and article tags.
- Integrated mailto:, tel:, and external target="_blank" social links in footer.

---

## Next Step

Moving on to Day 2: Forms, Tables and Lists!
