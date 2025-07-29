---
category: "input_assistance_forms"
category_description: "Label form fields, provide hints and handle errors gracefully."
---

### Overview

Forms must be easy to understand and complete. Provide labels and instructions, identify errors clearly and offer suggestions for corrections. Prevent irreversible mistakes by confirming critical actions.

### Relevant WCAG 2.1 success criteria

- **3.3.1 Error Identification** (Level A) – Explain errors in text. ([WCAG 3.3.1 – Error Identification](https://www.w3.org/TR/WCAG21/#error-identification))
- **3.3.2 Labels or Instructions** (Level A) – Provide labels and instructions for inputs. ([WCAG 3.3.2 – Labels or Instructions](https://www.w3.org/TR/WCAG21/#labels-or-instructions))
- **3.3.3 Error Suggestion** (Level AA) – Offer suggestions for correcting errors. ([WCAG 3.3.3 – Error Suggestion](https://www.w3.org/TR/WCAG21/#error-suggestion))
- **3.3.4 Error Prevention** (Level AA) – Provide review and confirmation steps for critical transactions.

### Technical guidance

* Use `<label for>` to associate each input with its label.  
* Provide helper text using `aria-describedby` and small print.  
* Validate inputs after user submission and display error messages near the field with `aria-invalid="true"`.  
* Offer a summary or confirmation page before completing actions with legal or financial consequences.

### Code example

#### Form with validation
```html
<form novalidate>
  <label for="name">Name</label>
  <input id="name" required aria-describedby="name-hint">
  <small id="name-hint">Enter your full name.</small>
  <span id="name-error" class="error" hidden></span>
  <button type="submit">Submit</button>
</form>
<script>
  const form=document.querySelector('form');
  form.addEventListener('submit',e=>{
    e.preventDefault();
    const input=document.getElementById('name');
    const error=document.getElementById('name-error');
    if(!input.value){
      input.setAttribute('aria-invalid','true');
      error.textContent='Name is required.';
      error.hidden=false;
    } else {
      error.hidden=true;
      input.removeAttribute('aria-invalid');
    }
  });
</script>
```
