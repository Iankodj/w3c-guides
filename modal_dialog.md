---
category: "modal_dialog"
category_description: "Accessible modal dialogs with proper focus management."
---

### Overview

Modal dialogs demand the user’s attention. They must be announced correctly, trap focus while open and return focus to the trigger when closed.

### Relevant WCAG 2.1 success criteria

- **2.4.3 Focus Order** (Level A) – Focus moves logically through the dialog and back. ([WCAG 2.4.3 – Focus Order](https://www.w3.org/TR/WCAG21/#focus-order))
- **3.2.1 On Focus** (Level A) – Dialogs do not cause unexpected context changes on focus. ([WCAG 3.2.1 – On Focus](https://www.w3.org/TR/WCAG21/#on-focus))
- **4.1.2 Name, Role, Value** (Level A) – Expose dialog roles and attributes. ([WCAG 4.1.2 – Name, Role, Value](https://www.w3.org/TR/WCAG21/#name-role-value))

### Technical guidance

* Wrap the dialog in an element with `role="dialog"` and `aria-modal="true"`.  
* Provide `aria-labelledby` referencing the dialog title and `aria-describedby` referencing its content.  
* When the dialog opens, move focus to the first element inside and trap focus until closed.  
* Support closing via Escape key and a visible close button; return focus to the triggering element after closing.

### Code example

#### Modal dialog
```html
<button id="open">Open dialog</button>
<div id="overlay" hidden></div>
<div id="dialog" role="dialog" aria-modal="true" aria-labelledby="dialog-title" aria-describedby="dialog-desc" hidden>
  <h2 id="dialog-title">Confirm</h2>
  <p id="dialog-desc">Delete this item?</p>
  <button id="confirm">Delete</button>
  <button id="cancel">Cancel</button>
</div>
<script>
const openBtn=document.getElementById('open');
const dialog=document.getElementById('dialog');
const overlay=document.getElementById('overlay');
let lastFocus;
openBtn.addEventListener('click',()=>{
  lastFocus=document.activeElement;
  overlay.hidden=false;
  dialog.hidden=false;
  dialog.querySelector('button').focus();
});
function close(){
  dialog.hidden=true;
  overlay.hidden=true;
  lastFocus.focus();
}
document.getElementById('cancel').addEventListener('click',close);
document.addEventListener('keydown',e=>{ if(!dialog.hidden && e.key==='Escape'){ close(); } });
</script>
```
