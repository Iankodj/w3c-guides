---
category: "keyboard_navigation"
category_description: "Ensure all functionality works via keyboard and provide logical focus order."
---

### Overview

Keyboard users need to operate every interactive control, move through content in a meaningful order and bypass repetitive blocks. Visible focus indicators help users track their position.

### Relevant WCAG 2.1 success criteria

- **2.1.1 Keyboard** (Level A) – All functions are available from keyboard. ([ ([WCAG 2.1.1 – Keyboard](https://www.w3.org/TR/WCAG21/#keyboard))
- **2.1.2 No Keyboard Trap** (Level A) – Keyboard focus is never trapped. ([WCAG 2.1.2 – No Keyboard Trap](https://www.w3.org/TR/WCAG21/#no-keyboard-trap))
- **2.4.1 Bypass Blocks** (Level A) – Provide skip links to skip repeated content. ([WCAG 2.4.1 – Bypass Blocks](https://www.w3.org/TR/WCAG21/#bypass-blocks))
- **2.4.3 Focus Order** (Level A) – Focus moves in a meaningful order. ([WCAG 2.4.3 – Focus Order](https://www.w3.org/TR/WCAG21/#focus-order))
- **2.4.7 Focus Visible** (Level AA) – Visible focus indicator is provided. ([WCAG 2.4.7 – Focus Visible](https://www.w3.org/TR/WCAG21/#focus-visible))

### Technical guidance

* Use native HTML controls for buttons and inputs, which are keyboard accessible by default.  
* Provide a skip link at the top of pages to jump to the main content.  
* Order elements in the DOM to match the visual flow; avoid messing with positive `tabindex` values.  
* Maintain highly visible focus outlines; do not remove them without replacement.

### Code example

#### Skip link
```html
<a href="#main" class="skip-link">Skip to main content</a>
<main id="main">Main content...</main>
<style>
  .skip-link { position:absolute; left:-10000px; }
  .skip-link:focus { left:1rem; background:#0057b8; color:#fff; padding:0.5rem; }
</style>
```

#### Custom button with keyboard support
```html
<div role="button" tabindex="0" aria-pressed="false">Toggle</div>
<script>
  const btn=document.querySelector('[role=button]');
  btn.addEventListener('click',()=>{
    const pressed = btn.getAttribute('aria-pressed')==='true';
    btn.setAttribute('aria-pressed',!pressed);
  });
  btn.addEventListener('keydown',(e)=>{
    if(e.key===' '||e.key==='Enter'){ e.preventDefault(); btn.click(); }
  });
</script>
```
