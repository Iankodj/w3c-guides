---
category: "autocomplete"
category_description: "Autocomplete inputs providing suggestions while typing."
---

### Overview

Autocomplete fields show suggestions as the user types. Use the combobox pattern with status messages so screen readers announce available options.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Associate the input and suggestion list.
- **2.1.1 Keyboard** (Level A) – Provide keyboard navigation through suggestions. ([WCAG 2.1.1 – Keyboard](https://www.w3.org/TR/WCAG21/#keyboard))
- **3.3.2 Labels or Instructions** (Level A) – Label the field and instruct users about suggestions. ([WCAG 3.3.2 – Labels or Instructions](https://www.w3.org/TR/WCAG21/#labels-or-instructions))
- **4.1.3 Status Messages** (Level AA) – Announce when suggestions appear. ([WCAG 4.1.3 – Status Messages](https://www.w3.org/TR/WCAG21/#status-messages))

### Technical guidance

* Use `role="combobox"` on a wrapper with `aria-expanded` and `aria-haspopup="listbox"`.  
* Provide an input with `aria-autocomplete="list"` and `aria-controls` pointing to the listbox.  
* Populate a `<ul role="listbox">` with `<li role="option">` items as suggestions and update `aria-activedescendant`.  
* Use a live region to announce how many suggestions are available.

### Code example

#### Autocomplete
```html
<label id="city-label" for="city">City</label>
<div role="combobox" aria-expanded="false" aria-haspopup="listbox">
  <input id="city" aria-autocomplete="list" aria-controls="city-list" aria-labelledby="city-label">
</div>
<ul id="city-list" role="listbox" hidden></ul>
<span id="city-status" aria-live="polite" class="sr-only"></span>
```
