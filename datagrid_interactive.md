---
category: "datagrid_interactive"
category_description: "Interactive tables or spreadsheets using ARIA grid patterns."
---

### Overview

An interactive data grid allows users to navigate, edit and sort data. Use roles `grid`, `row` and `gridcell` and implement keyboard navigation patterns.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Expose the grid structure via roles and properties.
- **2.1.1 Keyboard** (Level A) – Provide keyboard navigation for cells and editing. ([WCAG 2.1.1 – Keyboard](https://www.w3.org/TR/WCAG21/#keyboard))
- **2.4.3 Focus Order** (Level A) – Keep a logical focus order through cells. ([WCAG 2.4.3 – Focus Order](https://www.w3.org/TR/WCAG21/#focus-order))
- **4.1.2 Name, Role, Value** (Level A) – Announce names, roles and values of grid elements. ([WCAG 4.1.2 – Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value))

### Technical guidance

* Set `role="grid"` on the container and `role="row"` on each row.  
* Use `role="gridcell"` or `role="columnheader"` on cells; update `aria-selected` or `aria-activedescendant` as focus moves.  
* Implement keyboard commands for navigation (Arrow keys) and editing (Enter, Escape).

### Code example

#### Simple ARIA grid
```html
<div role="grid" aria-rowcount="2" aria-colcount="2">
  <div role="row" aria-rowindex="1">
    <div role="columnheader" aria-colindex="1">Item</div>
    <div role="columnheader" aria-colindex="2">Qty</div>
  </div>
  <div role="row" aria-rowindex="2">
    <div role="gridcell" aria-colindex="1" tabindex="0">Apples</div>
    <div role="gridcell" aria-colindex="2" tabindex="0">10</div>
  </div>
</div>
```
