---
category: "robustness_compatibility"
category_description: "Write code that can be parsed and understood by assistive tech."
---

### Overview

For accessibility APIs to work, your markup must be valid and UI components must expose names, roles and states. Inform users of dynamic updates via live regions without moving focus unexpectedly.

### Relevant WCAG 2.1 success criteria

- **4.1.1 Parsing** (Level A) – Code is well-formed and follows specifications. ([WCAG 4.1.1 – Parsing](https://www.w3.org/TR/WCAG21/#parsing))
- **4.1.2 Name, Role, Value** (Level A) – UI components expose accessible properties. ([WCAG 4.1.2 – Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value))
- **4.1.3 Status Messages** (Level AA) – Status messages are announced without moving focus. ([WCAG 4.1.3 – Status Messages](https://www.w3.org/TR/WCAG21/#status-messages))

### Technical guidance

* Validate your HTML; ensure tags are properly nested and IDs are unique.  
* For custom widgets, set ARIA roles (e.g. `role="switch"`) and properties (`aria-checked`, `aria-expanded`).  
* Announce dynamic updates with `aria-live="polite"` or `aria-live="assertive"`.  
* Test with screen readers and keyboards to ensure correct behaviour.

### Code example

#### Custom switch with ARIA
```html
<div role="switch" aria-checked="false" tabindex="0">Dark mode</div>
<script>
  const sw=document.querySelector('[role=switch]');
  sw.addEventListener('click',()=>{
    const on=sw.getAttribute('aria-checked')==='true';
    sw.setAttribute('aria-checked',!on);
  });
</script>
```

#### Live region status
```html
<ul id="list"></ul>
<div id="status" aria-live="polite"></div>
<script>
function addItem(text){
  const li=document.createElement('li');
  li.textContent=text;
  document.getElementById('list').appendChild(li);
  document.getElementById('status').textContent=`Added: ${text}`;
}
addItem('Hello');
</script>
```
