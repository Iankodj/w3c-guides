---
category: "tabs"
category_description: "Accessible tabbed interfaces with ARIA roles and keyboard navigation."
---

### Overview

Tabs organise content into panels with only one panel displayed at a time. Use roles `tablist`, `tab` and `tabpanel` and support arrow key navigation.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Associate tabs with their panels.
- **2.1.1 Keyboard** (Level A) – Arrow keys move between tabs; Enter/Space activates. ([WCAG 2.1.1 – Keyboard](https://www.w3.org/TR/WCAG21/#keyboard))
- **2.4.3 Focus Order** (Level A) – Focus flows through tabs then into the panel. ([WCAG 2.4.3 – Focus Order](https://www.w3.org/TR/WCAG21/#focus-order))
- **4.1.2 Name, Role, Value** (Level A) – Use proper roles and states for tabs. ([WCAG 4.1.2 – Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value))

### Technical guidance

* Wrap tab buttons in a container with `role="tablist"`. Use `role="tab"` on each and set `aria-selected`.  
* Associate each tab with a panel via `aria-controls` pointing to a `tabpanel` element.  
* Update `aria-selected` and visibility when tabs change; manage `tabindex` to ensure only the active tab is focusable.  
* Support arrow key navigation across tabs and optionally Home/End keys.

### Code example

#### Tabs example
```html
<div role="tablist">
  <button role="tab" aria-selected="true" aria-controls="panel1" id="tab1">Tab 1</button>
  <button role="tab" aria-selected="false" aria-controls="panel2" id="tab2" tabindex="-1">Tab 2</button>
</div>
<div id="panel1" role="tabpanel">Content 1</div>
<div id="panel2" role="tabpanel" hidden>Content 2</div>
```
