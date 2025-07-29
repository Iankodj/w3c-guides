---
category: "structure_semantics"
category_description: "Use semantic HTML to express structure and relationships."
---

### Overview

Semantic markup conveys information hierarchy and relationships to assistive technologies. Use headings, lists, regions and proper table markup to ensure content is presented logically.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Convey information and structure programmatically.【755185167370695†L659-L695】
- **1.3.2 Meaningful Sequence** (Level A) – Present content in logical reading order.【755185167370695†L659-L695】
- **1.3.3 Sensory Characteristics** (Level A) – Do not rely solely on colour or shape to convey information.【755185167370695†L659-L695】
- **4.1.2 Name, Role, Value** (Level A) – Expose name, role and state for UI components.【755185167370695†L1856-L1867】

### Technical guidance

* Use `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` and `<footer>` to delineate page regions.  
* Mark headings with `<h1>`–`<h6>` according to hierarchy and avoid skipping levels.  
* Use list elements (`<ul>`, `<ol>`, `<li>`) for groups and `<table>` with `<th scope>` for tabular data.  
* Add ARIA roles and properties to custom widgets to expose their purpose and state.

### Code example

#### Semantic sections
```html
<header>
  <h1>My Blog</h1>
</header>
<main>
  <section>
    <h2>Article 1</h2>
    <p>Content...</p>
  </section>
</main>
```

#### Accessible table
```html
<table>
  <caption>Monthly Budget</caption>
  <thead>
    <tr>
      <th scope="col">Category</th>
      <th scope="col">Amount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Rent</th>
      <td>€700</td>
    </tr>
  </tbody>
</table>
```
