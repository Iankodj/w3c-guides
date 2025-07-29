---
category: "grid_table"
category_description: "Static data tables with proper headings and captions."
---

### Overview

Present tabular data using the `<table>` element and associate header cells with data. Use captions and scopes so relationships are clear.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Associate headers and cells programmatically.
- **2.4.6 Headings and Labels** (Level AA) – Captions and column headings describe the data. ([WCAG 2.4.6 – Headings and Labels](https://www.w3.org/TR/WCAG21/#headings-and-labels))
- **1.4.3 Contrast (Minimum)** (Level AA) – Table text meets contrast requirements. ([WCAG 1.4.3 – Contrast (Minimum)](https://www.w3.org/TR/WCAG21/#contrast-minimum))

### Technical guidance

* Use `<caption>` to describe the table.  
* Place header cells in `<th>` elements within `<thead>` and set `scope="col"` or `scope="row"`.  
* Avoid using tables for layout purposes.

### Code example

#### Data table
```html
<table>
  <caption>Top Languages</caption>
  <thead>
    <tr>
      <th scope="col">Rank</th>
      <th scope="col">Language</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>JavaScript</td>
    </tr>
  </tbody>
</table>
```
