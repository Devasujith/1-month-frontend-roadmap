# Day 2 Learning Notes: HTML Lists, Tables, and Forms

## 1. HTML Lists

Lists are used to group related pieces of information together in a structured format. HTML provides three main types of lists:

### Unordered List (`<ul>`)
* Used when the order of items does not matter.
* Rendered with bullet points by default.
* Direct children must always be `<li>` (List Item) elements.

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

### Ordered List (`<ol>`)
* Used when the sequence or step-by-step order is important.
* Rendered with numerical indicators by default.
* Direct children must always be `<li>` elements.

#### Key Attributes:
* `type`: Specifies the numbering style (`1`, `a`, `A`, `i`, `I`).
* `start`: Defines the starting index for the list (e.g., `start="3"` with `type="A"` begins at 'C').
* `reversed`: Reverses the numbering order (e.g., 3, 2, 1).

```html
<ol type="A" start="3">
  <li>Module C: JavaScript DOM</li>
  <li>Module D: Async JavaScript</li>
</ol>
```

### Description List (`<dl>`)
* Used for key-value pairs, glossaries, or term-definition structures.
* `<dl>`: Description List container.
* `<dt>`: Description Term (the key or heading).
* `<dd>`: Description Data (the value or explanation).

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language - used for structuring web content.</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets - used for styling and layout.</dd>
</dl>
```

---

## 2. HTML Tables

Tables structure data into structured rows and columns, similar to spreadsheet layouts.

### Basic Elements
* `<table>`: Container element for the table structure.
* `<tr>`: Table Row - defines a horizontal row of cells.
* `<th>`: Table Header - defines header cells; text is bold and centered by default.
* `<td>`: Table Data - defines standard data cells; text is normal and left-aligned by default.

### Semantic Table Structure
Using semantic sections improves accessibility, code maintainability, and styling control:
* `<caption>`: Specifies the table title/summary; must be placed directly under the `<table>` tag.
* `<thead>`: Encloses table header rows.
* `<tbody>`: Encloses the primary body data rows.
* `<tfoot>`: Encloses summary or total rows at the bottom.

### Merging Cells (`colspan` and `rowspan`)
* `colspan`: Merges multiple adjacent columns horizontally (expands width).
* `rowspan`: Merges multiple adjacent rows vertically (expands height).

### CSS Styling & Responsiveness
* `border-collapse: collapse;`: Merges default double borders into single crisp borders.
* `text-align: center;`: Aligns cell content horizontally in `<td>` elements.
* `overflow-x: auto;`: Placed on a wrapping `<div>` around the table to enable horizontal scrolling on small mobile viewports without breaking page layout.

### Practical Table Code Structure

```html
<div style="overflow-x: auto;">
  <table>
    <caption>Semester Exam Results 2026</caption>
    <thead>
      <tr>
        <th>Student Name</th>
        <th>Subject</th>
        <th>Marks</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td rowspan="2">Sujith</td>
        <td>HTML</td>
        <td>90</td>
      </tr>
      <tr>
        <td>CSS</td>
        <td>85</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td colspan="2">Total Average Marks</td>
        <td>87.5</td>
      </tr>
    </tfoot>
  </table>
</div>
```

---

## 3. HTML Forms

Forms provide interactive controls to collect user inputs and submit data to a web server or backend service.

### Form Wrapper (`<form>`)
* `action`: Specifies the destination URL/endpoint where submitted form data is processed.
* `method`: Specifies the HTTP method for sending data:
  * `GET`: Appends input data directly to the URL bar as query parameters; best suited for non-sensitive operations like searches.
  * `POST`: Encapsulates input data within the HTTP request payload; required for sensitive data like passwords and form submissions.

### Label and Input Binding (`<label>` and `<input>`)
* The `for` attribute of `<label>` must exactly match the `id` attribute of the corresponding `<input>`.
* Binding enables user interaction with the label text to trigger focus on the input box, enhancing accessibility.

### Input Types and Attributes
* `type="text"`: Standard single-line text input.
* `type="password"`: Masks characters for secure entry.
* `type="email"`: Validates email formatting automatically on submission.
* `type="number"`: Restricts input to numerical values; controlled using `min` and `max` attributes (note: `maxlength` does not apply to numerical inputs).
* `type="date"`: Invokes native calendar date picker; bound using `min` and `max` ranges.
* `type="radio"`: Choice selection where only one option can be selected per group; all related radio buttons must share an identical `name` attribute.
* `type="checkbox"`: Toggable choices allowing single or multiple selections.
* `type="file"`: Enables file upload controls.
* `name`: Crucial attribute identifying the key name sent to backend servers upon submission. Without a `name` attribute, input values are omitted from submission payloads.
* `required`: Enforces input validation before form submission is permitted.
* `placeholder`: Displays temporary contextual hint text inside the field.

### Additional Form Controls
* `<textarea>`: Multi-line text input field for longer text like addresses or feedback; sized using `rows` and `cols`.
* `<select>` & `<option>`: Dropdown menu selection. Each `<option>` requires a meaningful `value` attribute to pass data to the server.
* `<button type="submit">`: Triggers form submission.
* `<button type="reset">`: Resets all form fields to their default state.

### Comprehensive Form Code Structure

```html
<form action="signup.html" method="POST">
  <div>
    <label for="username">Username:</label>
    <input type="text" name="username" id="username" required placeholder="Enter username">
  </div>
  <div>
    <label for="password">Password:</label>
    <input type="password" name="password" id="password" required>
  </div>
  <div>
    <label for="yearofbirth">Year of Birth:</label>
    <input type="number" name="yearofbirth" id="yearofbirth" min="1900" max="2026">
  </div>
  <div>
    <label for="male">Male</label>
    <input type="radio" name="gender" id="male" value="male">
    <label for="female">Female</label>
    <input type="radio" name="gender" id="female" value="female">
  </div>
  <div>
    <label for="dateofbirth">Date of Birth:</label>
    <input type="date" name="dateofbirth" id="dateofbirth" min="1900-01-01">
  </div>
  <div>
    <label for="email">Email:</label>
    <input type="email" name="email" id="email" placeholder="example@mail.com">
  </div>
  <div>
    <label for="about">About:</label>
    <textarea name="about" id="about" rows="4" cols="30"></textarea>
  </div>
  <div>
    <label for="sms">SMS Alert:</label>
    <input type="checkbox" id="sms" name="sms">
  </div>
  <div>
    <label for="state">State:</label>
    <select name="state" id="state">
      <option value="tamilnadu">Tamil Nadu</option>
      <option value="andhra">Andhra Pradesh</option>
      <option value="karnataka">Karnataka</option>
    </select>
  </div>
  <div>
    <label for="file">Upload Resume:</label>
    <input type="file" id="file" name="resume">
  </div>
  
  <button type="submit">Sign Up</button>
  <button type="reset">Reset</button>
</form>
```
