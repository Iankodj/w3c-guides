---
category: "input_field"
category_description: "Standard text input fields with labels, hints and validation."
---

### Overview

Basic text inputs are widely used. They require proper labels, input types, helper text and unobtrusive validation to guide users.

### Relevant WCAG 2.1 success criteria

- **1.3.1 Info & Relationships** (Level A) – Label and input are associated.
- **2.4.6 Headings and Labels** (Level AA) – Labels describe purpose. ([WCAG 2.4.6 – Headings and Labels](https://www.w3.org/TR/WCAG21/#headings-and-labels))
- **3.3.2 Labels or Instructions** (Level A) – Provide hints on expected format. ([WCAG 3.3.2 – Labels or Instructions](https://www.w3.org/TR/WCAG21/#labels-or-instructions))
- **3.3.3 Error Suggestion** (Level AA) – Offer suggestions when validation fails. ([WCAG 3.3.3 – Error Suggestion](https://www.w3.org/TR/WCAG21/#error-suggestion))

### Technical guidance

* Use `<label for="id">` on each input; do not rely on placeholder as the only label.  
* Choose appropriate `type` attributes (e.g. `email`, `tel`) to aid user input.  
* Provide helper text via `aria-describedby` and mark invalid fields with `aria-invalid`.  
* Validate inputs on submit and show error messages with suggestions near the field.

### Code example

#### Email input with error handling
```html
<form novalidate>
  <label for="email">Email</label>
  <input id="email" type="email" required aria-describedby="email-help">
  <small id="email-help">We will not share your email.</small>
  <span id="email-error" class="error" hidden></span>
  <button type="submit">Submit</button>
</form>
<script>
  const form=document.querySelector('form');
  form.addEventListener('submit',e=>{
    e.preventDefault();
    const input=document.getElementById('email');
    const error=document.getElementById('email-error');
    if(!input.validity.valid){
      input.setAttribute('aria-invalid','true');
      error.textContent='Please enter a valid email.';
      error.hidden=false;
    } else {
      input.removeAttribute('aria-invalid');
      error.hidden=true;
    }
  });
</script>
```
