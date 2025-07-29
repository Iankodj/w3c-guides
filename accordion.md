---
category: "accordion"
category_description: "Collapsible sections implemented as accordions."
---

### Overview

Accordions hide or reveal sections of content. Use buttons with `aria-expanded` and link them to regions via `aria-controls`; support keyboard toggling.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Tie accordion headers to panels via ARIA.
- **2.1.1 Keyboard** (Level A) – Users can toggle panels with Enter/Space. ([WCAG 2.1.1 – Keyboard](https://www.w3.org/TR/WCAG21/#keyboard))
- **2.4.3 Focus Order** (Level A) – Focus remains in logical sequence. ([WCAG 2.4.3 – Focus Order](https://www.w3.org/TR/WCAG21/#focus-order))
- **4.1.2 Name, Role, Value** (Level A) – Indicate expansion state via `aria-expanded`. ([WCAG 4.1.2 – Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value))

### Technical guidance

* Use a button for each accordion header; set `aria-expanded` to reflect state and `aria-controls` to point to the panel.  
* Give panels `role="region"` and `aria-labelledby` pointing back to the header.  
* Toggle `hidden` or CSS classes to show/hide panels when the header is activated; maintain focus on the header.  
* Support keyboard: Enter/Space toggles; Up/Down arrows move between headers; Home/End jump to first/last header.

### Code example

#### Accordion example
```html
<button aria-expanded="false" aria-controls="panelA" id="accA">Section A</button>
<div id="panelA" role="region" aria-labelledby="accA" hidden>
  <p>Panel A content.</p>
</div>
```
