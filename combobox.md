---
category: "combobox"
category_description: "Accessible combo boxes combining input and selection."
---

### Overview

A combobox is an input field with an attached list of options. Use the ARIA combobox pattern to associate the input with the listbox and provide keyboard navigation.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Associate input, button and listbox programmatically.
- **2.1.1 Keyboard** (Level A) – Keyboard opens list, navigates options and selects. ([WCAG 2.1.1 – Keyboard](https://www.w3.org/TR/WCAG21/#keyboard))
- **2.1.2 No Keyboard Trap** (Level A) – Focus can move into and out of the combobox. ([WCAG 2.1.2 – No Keyboard Trap](https://www.w3.org/TR/WCAG21/#no-keyboard-trap))
- **2.5.3 Label in Name** (Level A) – Accessible name includes visible label. ([WCAG 2.5.3 – Label in Name](https://www.w3.org/TR/WCAG21/#label-in-name))
- **4.1.2 Name, Role, Value** (Level A) – Expose combobox role and state via ARIA. ([WCAG 4.1.2 – Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value))

### Technical guidance

* Wrap the input and toggle button in a container with `role="combobox"` and set `aria-haspopup="listbox"`.  
* Set `aria-expanded` to reflect open/closed state and `aria-controls` to point to the listbox ID.  
* Provide a listbox (`<ul role="listbox">`) with options (`<li role="option">`).  
* Update `aria-activedescendant` on the input to the ID of the highlighted option.

### Code example

#### Combobox example
```html
<label id="combo-label" for="combo-input">Country</label>
<div role="combobox" aria-haspopup="listbox" aria-expanded="false">
  <input id="combo-input" aria-controls="combo-list" aria-labelledby="combo-label" aria-autocomplete="list">
  <button aria-label="Toggle list">▼</button>
</div>
<ul id="combo-list" role="listbox" hidden>
  <li role="option">Bulgaria</li>
  <li role="option">Germany</li>
</ul>
```
